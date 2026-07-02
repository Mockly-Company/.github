---
type: Sequence Diagram
title: 세션 복원 (앱 재시작 시 인증)
description: 앱 재시작 시 저장된 ACCESS/REFRESH 토큰을 로드해 인증 상태를 복원하고, 만료 시 Refresh를 거쳐 프로필을 다시 조회하는 과정.
tags: [auth, session, restore, token]
timestamp: 2026-07-02T00:00:00+09:00
---

# Diagram

```mermaid
sequenceDiagram
    title 앱 다시 시작시 인증 과정
    participant App
    participant Backend

    App->>App: 저장된 ACCESS / REFRESH 로드
    App->>Backend: GET /api/auth/me (ACCESS)

    alt ACCESS 유효
        Backend->>App: 사용자 프로필
    else ACCESS 만료
        Backend-->>App: 401 TOKEN_EXPIRED
        App->>Backend: POST /api/auth/refresh (REFRESH)

        alt Refresh 성공
            Backend->>App: 새로운 ACCESS 토큰
            App->>Backend: GET /api/auth/me 재요청
            Backend->>App: 사용자 프로필
        else Refresh 실패
            Backend-->>App: 401 TOKEN_EXPIRED
            App->>App: Logout 처리
        end
    end
```

# Notes

* 런타임 중 토큰 만료 처리(요청 큐 포함)는 [토큰 갱신](./token-refresh.md) 참고.
