# Mockly‑Company 프로젝트

Mockly‑Company 공식 프로젝트 랜딩 페이지에 오신 것을 환영합니다.  
여기서는 주요 레포지토리와 각 레포가 Mockly 생태계에서 어떤 역할을 하는지 소개합니다.

---

## 🚀 서비스 소개

**Mockly**는 AI 면접 연습과 온라인 실전 면접 연습을 모두 제공하는 **AI 기반 면접 플랫폼**입니다.  
사용자는 AI와 함께 면접을 연습하며 피드백을 받고, 실제 면접 상황을 미리 경험할 수 있습니다.  
AI 기술을 통해 면접 질문 생성, 답변 분석, 코드 리뷰 등 다양한 기능이 자동화되어 있습니다.

---

## 📄 문서 바로가기
- [**서비스 기획서**](https://mockly.atlassian.net/wiki/external/Mzg4NzZjZTcxNmM5NGM4MGI2ZjY3OWQ5MGRiZWM4YzQ)
- [**MVP 기능정의서**](https://mockly.atlassian.net/wiki/external/ZjA4NjMxY2FiMzhlNDc5OWIyMzM2NzY1OTkyNmRlOTQ)
- [**개인정보 처리방침**](https://mockly.atlassian.net/wiki/external/NDVjYTAwN2U2MDViNDZjOGEyYzdhMTYwYjY5OGY3OGU)
- [**이용약관**](https://mockly.atlassian.net/wiki/external/MTAxMWQ4NjNjMDgyNDJkZGE4YWJkMmE3YTdhMWM3NWY)
- [**디자인 시스템**](https://69324aeddcbd1324310464e9-giibikyaod.chromatic.com/)
---
## 도메인별 자료 바로가기
- [**인증 설계**](./Auth/README.md)
- [**결제 설계**](./Payment/README.md)

## 📂 레포지토리

### 1. [`AI_TEMPLATE`](https://github.com/Mockly-Company/AI_TEMPLATE)  
**목적**: Mockly 생태계에서 AI 기능을 정형화하여 빠르게 개발할 수 있는 템플릿  
**주요 특징**:
- AI 기반 기능을 표준화된 구조로 쉽게 구현 가능  
- PR 시 자동으로 AI가 코드 리뷰 수행  
- **Claude Skills와 Command**를 사용하여 AI 기능 확장 가능  
- 모바일, 서버 등 다른 레포지토리에서도 재사용 가능  

### 2. [`mockly-mobile`](https://github.com/Mockly-Company/mockly-mobile)  
**목적**: Mockly 모바일 앱 프론트엔드  
**주요 특징**:
- AI 면접 연습과 온라인 면접 연습 기능 제공  
- AI_TEMPLATE 기반으로 AI 기능(면접 질문 생성, 답변 분석 등) 적용  
- 사용자 경험과 인터랙션 최적화  

### 3. [`mockly-server`](https://github.com/Mockly-Company/mockly-server)  
**목적**: Mockly 플랫폼 백엔드 서비스  
**주요 특징**:
- REST/GraphQL API 제공, 사용자 및 세션 관리  
- AI_TEMPLATE 기반 AI 기능 처리(코드 리뷰, 답변 분석, 면접 시뮬레이션 등)  
- 모바일 앱과 연동하여 실시간 데이터와 피드백 제공  

---

## 🎯 Mockly 프로젝트의 강점

- **AI 기반 면접 자동화**: 질문 생성, 답변 분석, 코드 리뷰까지 AI가 지원  
- **정형화된 AI 개발 템플릿**: AI_TEMPLATE과 Claude Skills/Command를 활용하여 빠른 기능 구현과 일관성 유지  
- **모바일 + 서버 통합 플랫폼**: 앱과 백엔드가 유기적으로 연동되어 실전과 유사한 환경 제공  
- **개발자 친화적 환경**: 코드 리뷰 자동화와 표준화된 구조로 개발 효율 극대화  

---

## 📌 시작 가이드

1. 필요한 레포지토리(모바일/서버)를 클론하고 README를 참고하여 설정  
2. AI 기능은 AI_TEMPLATE 기반으로 통합 및 구현 (Claude Skills/Command 사용 가능)  
3. 모바일 ↔ 서버 ↔ AI 간 연동 구조 참고  
4. 기여: 포크 → 기능 브랜치 → 풀 리퀘스트. AI 코드 리뷰가 자동으로 진행됨  

---

## ✨ 향후 계획

- AI 면접 기능 고도화 (답변 피드백, 모의 면접 시나리오 확장)  
- 모바일/웹 사용자 경험 개선  
- AI_TEMPLATE 기능 확장: 새로운 AI 모듈 추가 (추천 질문, 평가 분석 등)  
- 관측성 및 대시보드 강화  

---

<table>
  <tr>
      <td>라이트</td>
    <td>다크</td>
        <td>모바일 스토리북</td>
        <td>웹 스토리북</td>
  </tr>
  <tr>
    <td><image src="https://github.com/user-attachments/assets/5f3a634e-6d5f-4544-8bc6-b225bf8e3f30" style="width:300;"></image></td>
    <td><image src="https://github.com/user-attachments/assets/e9408cb8-872a-45e4-ba31-6883f859233a" style="width:300;"></image></td>
        <td><image src="https://github.com/user-attachments/assets/c11f1b8b-686e-435d-b64f-4a7a3818ee20" style="width:300;"></image></td>
        <td><image src="https://github.com/user-attachments/assets/0f9f4d8a-56dc-4727-b6d5-c7bf5bd3c12e" style="width:300;">
          <a href="https://69324aeddcbd1324310464e9-giibikyaod.chromatic.com/">디자인 시스템 보러가기</a>
        </image></td>
  </tr>
</table>

**Mockly**와 함께 AI 면접 연습의 새로운 경험을 만들어 나가요. 🎉
