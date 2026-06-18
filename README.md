# APL-Motion.com 홈페이지 (작업 폴더)

이 폴더가 **APL-Motion.com 회사 홈페이지의 원본 작업 폴더**입니다.
앞으로 수정은 이 폴더의 `index.html`을 기준으로 진행합니다.

## 파일 구성
- `index.html` — 홈페이지 본체. **로고가 파일 안에 내장(base64)** 되어 있어 단독으로 열어도/배포해도 로고가 항상 보입니다. (별도 폴더 없이 이 파일 하나로 동작)
- `assets/` — 원본 로고 PNG 보관용 (APL 마크/워드마크/스타, 흰색·검정). 편집·재가공할 때 사용. index.html은 이 폴더에 의존하지 않습니다.

## 링크 교체 (가장 자주 바꾸는 곳)
`index.html` 맨 아래 `<script>` 안의 `CONFIG`에서 아래만 실제 주소로 교체:
- `storeUrl` — 네이버 스마트스토어
- `instagram` — 인스타그램
- `cafe` — 네이버 카페
- `appUrl` — APL Motion 앱 (이미 연결됨: https://apl2018.github.io/APL-Motion/)
- `email` — 대표 이메일 (기본: aplspl2018@gmail.com)

## 폰트·디자인 라이선스 (법적 안전)
- 본문 폰트 = **Inter** (SIL Open Font License, 상업적 사용 무료).
- 로고 = APL 자체 브랜드 자산.
- 네이버 로고/색상 등 외부 상표는 사용하지 않음(스토어는 텍스트 명칭으로만 안내).

## 배포 (APL-Motion.com 연결)
1. GitHub에 새 저장소 생성 → 이 `index.html` 업로드
2. Settings → Pages 활성화
3. Custom domain = `apl-motion.com` 입력 → 도메인 등록사 DNS에 GitHub 안내 레코드 추가 → Enforce HTTPS 체크

## 인스타그램 계정 (함께하기 섹션)
- @apl_mokdong / @apl_academy / @n1_tr_hsq / @da_specialist (4개)
- 네이버 카페: https://cafe.naver.com/motionspecialist
- 네이버 스토어: https://smartstore.naver.com/apl-motion

## 변경 이력
- 2026-06-18 (1차): 회사소개서 반영(Total Care & Solution, 사업영역, 공동대표 약력, 센터 개별 6곳), 실제 APL 로고 적용·base64 내장, 인스타 지표 삭제, 스토어 설명 '프로그램' 삭제, 함께하기 네이버 블로그 삭제, 네이버 'N' 로고 모방 요소 제거(상표 안전).
- 2026-06-18 (2차): 히어로 상단 'APL Motion 앱 열기' 버튼 제거(앱 섹션과 중복)→'사업영역/센터 보기'로 교체. 사업영역에서 '교육 콘텐츠' 카드 삭제. 대표자 이력 회사소개서 전체로 확장(김양수 8건/함상규 10건). 인스타 4계정·카페·스토어 실제 URL 연결. 주소는 동 단위(서울 양천구 목동)로 간소화. 히어로 별 오버레이를 우측으로 이동(글자 1/3만 겹침).
