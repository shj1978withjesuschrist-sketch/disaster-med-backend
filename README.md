# 재난의학 서바이벌 RPG — 데이터 추적 백엔드

교육생들의 게임 데이터를 수집하고 관리하는 FastAPI 백엔드 서버입니다.

## 원클릭 배포

[![Deploy to Render](https://render.com/images/deploy-to-render-button.svg)](https://render.com/deploy?repo=https://github.com/shj1978withjesuschrist-sketch/disaster-med-backend)

## 기능

- 교육생 세션 추적 (닉네임, 점수, 레벨, 연속정답)
- 모드별 성과 기록 (퀴즈, 시나리오, 트리아지, 팀미션, EMERGO)
- 개별 문제 응답 기록 (정답률, 소요시간)
- 관리자 대시보드 (/admin)
- CSV 내보내기
- 문제 난이도 분석

## 기술 스택

- FastAPI + Uvicorn
- SQLite (WAL 모드)
- Pydantic v2

## 관리자 접속

- URL: `https://<your-backend-url>/admin`
- 비밀번호: `disaster2026!`

## API 엔드포인트

### 교육생 데이터
- `POST /api/session/start` — 세션 시작
- `POST /api/session/end` — 세션 종료
- `POST /api/mode/result` — 모드 결과 저장
- `POST /api/question/response` — 문제 응답 저장

### 관리자
- `POST /api/admin/login` — 관리자 로그인
- `GET /api/admin/dashboard` — 대시보드 데이터
- `GET /api/admin/sessions` — 세션 목록
- `GET /api/admin/session/{id}` — 세션 상세
- `GET /api/admin/analytics/questions` — 문제 분석
- `GET /api/admin/export/csv` — CSV 내보내기
- `DELETE /api/admin/sessions/clear` — 전체 삭제

## 환경 변수

- `ADMIN_PASS` — 관리자 비밀번호 (기본: disaster2026!)
- `ADMIN_SECRET` — 토큰 비밀키
- `PORT` — 서버 포트 (Render에서 자동 설정)
