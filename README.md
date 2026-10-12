# 🐶 Waggle - 개발자 협업 팀원 모집 플랫폼

> 서비스 URL: https://waggle.lol  
> 본 저장소는 팀 프로젝트 [Waggle Org Repo 링크]에서 남민기(Frontend)의 개인 기여와 기술적 문제 해결 과정을 정리한 Fork 저장소입니다.

---

## 📌 1. 프로젝트 소개
* **서비스 개요:** 개발자/디자이너가 팀원을 찾고 협업을 지속할 수 있는 플랫폼
* **운영 성과:** 출시 이후 활성 사용자 599명 / 조회수 12,000회 / 이벤트 19,000건 달성 (2026-10 기준)
* **팀 구성:** 7명 (기획 1, 마케터 1, 디자이너 2, 프론트엔드 2, 백엔드 1)
* **개발 기간:** 2024.12 ~

---

## 🛠 2. 기술 스택 (Tech Stack)
* **Frontend:** React, TypeScript, Tailwind CSS, TanStack Query, Zustand, React Hook Form, Axios
* **Infra / Analytics:** AWS (S3, CloudFront, Route53, ACM, Lambda@Edge), Google Analytics, Google Search Console

---

## 🏛 3. 아키텍처 & 배포 구조
* **배포 아키텍처:** User → Route53 → CloudFront (CDN) → S3 (Static Hosting)
* **SEO & Meta:** Lambda@Edge를 활용하여 CSR 구조에서 동적 OG 태그 및 메타데이터 생성

---

## ✨ 4. 담당 기능 & 주요 기여 (Key Contributions)

### 4.1 핵심 플로우 및 동적 UI / 폼 관리
* 모집글 작성, 팀 생성, 지원 및 승인 대기 플로우 개발
* `React Hook Form`을 활용한 입력값 검증 및 일관된 폼 구조 설계

### 4.2 서버 상태 관리 및 API 통신 최적화
* `TanStack Query` 도입으로 서버 데이터 캐싱 및 불필요한 API 요청 최소화
* `Axios` 공통 인스턴스 구축으로 인증 토큰 처리 및 예외 처리 로직 일관화

---

## 🔍 5. 기술적 문제 해결 (Troubleshooting & Optimization)

### 🚀 [SEO 개선] CSR 환경에서 동적 Open Graph(OG) 및 메타 태그 구현
* **문제:** React SPA의 CSR 특성상 검색 엔진 및 SNS 크롤러가 게시글별 메타데이터를 수집하지 못함.
* **대안 검토:** Next.js 전환, Prerender, CloudFront Function, Lambda@Edge 비교
* **해결:** 기존 React SPA 구조를 유지하면서 API 연동이 가능한 `Lambda@Edge` 방식을 도입해 게시글별 동적 OG 태그 생성.
* **성과:** SNS 공유 시 페이지별 맞춤 미리보기 제공, Google Search Console 색인 페이지 31개 확보.

### 📊 [UX 개선] GA 데이터 기반 반응형 UI 및 모바일 UX 최적화
* **인사이트:** Google Analytics 분석 결과, 전체 활성 사용자의 55%가 모바일 기기 사용.
* **해결:** 모바일 사용성 강화를 위해 반응형 레이아웃 및 뷰포트 최적화 진행 중.
