---
type: Sequence Diagram
title: 토큰 갱신 (Token Refresh)
description: ACCESS 토큰 만료(401 TOKEN_EXPIRED) 시 REFRESH 토큰으로 재인증하고, 갱신 중 발생한 요청을 큐에 보류했다가 재요청하는 과정.
tags: [auth, token, refresh, retry-queue]
timestamp: 2026-07-02T00:00:00+09:00
---

# Diagram

```mermaid
sequenceDiagram
    title 인증 만료시 Token Refresh 처리 과정
    participant App
    participant Backend

    App->>Backend: API 요청 (ACCESS)
    Backend-->>App: 401 TOKEN_EXPIRED

    Note over App: refreshInProgress = true

    App->>Backend: POST /api/auth/refresh (REFRESH)

    par Refresh 중 추가 요청/에러 발생
        App->>App: (추가된 401 에러난 요청들), (새로 추가된 요청들) =>  Promise resolve를 Queue에 저장
    end

    alt Refresh 성공
        Backend->>App: 새로운 ACCESS 토큰
        Note over App: refreshInProgress = false

        loop Queue에 쌓인 요청들
            App->>Backend: 보류된 API 재요청 (새 ACCESS)
            Backend->>App: 정상 응답
        end

    else Refresh 실패 (REFRESH 만료)
        Backend-->>App: 401 TOKEN_EXPIRED
        Note over App: Queue 비움, reject처리
        App->>App: Logout 처리
    end
```

# Notes

* `refreshInProgress` 플래그로 중복 refresh 요청을 방지하고, 그 사이 발생한 요청은 Promise Queue에 보류한다.
* REFRESH 토큰까지 만료되면 큐를 reject 처리하고 로그아웃한다. 최초 로그인 흐름은 [PKCE 구글 로그인](./google-login-pkce.md) 참고.
