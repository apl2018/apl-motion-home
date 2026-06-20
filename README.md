# APL-Motion.com 홈페이지 — 작업 / 배포 가이드

회사 홈페이지(apl-motion.com)의 **원본 작업 폴더**입니다.
새 대화에서 이어서 작업할 때: **"APL-Motion홈페이지 README 읽고 이어서 작업해줘"** 라고 하면 됩니다.

---

## ✅ 한눈에 보기 — 현재 상태 (2026-06-19 기준, 전부 완료·라이브)
- **사이트 라이브**: https://apl-motion.com (= https://www.apl-motion.com) — 정상 작동 중.
  - GitHub Pages 백업 주소: https://apl2018.github.io/apl-motion-home/
- **가비아 DNS 연결 완료** (A레코드 4개 + www CNAME + 메일용 MX/TXT).
- **회사 이메일 완료**: `apl@apl-motion.com` → ImprovMX 무료 포워딩 → `aplspl2018@gmail.com` 수신.
- **Apple 개발자 조직 등록 신청 완료** — 등록 ID **J5SXHL7GT2** (심사 결과 메일 대기 중).

## ⏳ 남은 일 (자잘함)
1. **Apple 심사 대기** — 며칠 내 `apl@apl-motion.com`(→gmail)으로 다음 단계 안내가 옴 → 결제(연 $99) 후 가입 완료.
2. **Enforce HTTPS** — GitHub 저장소 Settings → Pages 에서 인증서 발급 후 체크박스 활성화되면 켜기(안 켜도 작동엔 무방).

---

## 📂 폴더 2개 + 동기화 규칙 (중요)
홈페이지 파일은 **두 곳**에 있고, 항상 **같은 내용으로 맞춰야** 합니다:
1. **작업 원본(이 폴더)**: `C:\Users\user\Desktop\claude 전용파일\APL-Motion홈페이지\`
2. **배포 저장소(git)**: `C:\Users\user\Documents\GitHub\apl-motion-home\`  ← GitHub Desktop이 연결된 폴더, 실제 배포는 여기서 함.

> 배포는 **반드시 저장소 폴더(2번)에서 GitHub Desktop으로 Commit → Push** 해야 사이트에 반영됩니다.
> 두 폴더의 `index.html`이 다르면 혼란이 생기니, 수정 후 항상 양쪽을 똑같이 맞춥니다.

## 🔁 차후 홈페이지 수정 재개 방법 (단계별)
1. 이 README와 `index.html`을 읽는다.
2. `index.html`을 수정한다. → **양쪽 폴더 둘 다 동일하게** 반영(한쪽 수정 후 다른 쪽으로 복사).
3. **GitHub Desktop 앱** 열기 → Current repository = **apl-motion-home**.
4. 왼쪽 **Changes**에 index.html이 뜸 → Summary 입력 → **Commit to main** → **Push origin**.
   - Push 버튼이 `Pull origin`으로 보이면 먼저 Pull 후 다시 Push.
   - ⚠️ "보는 곳=웹(github.com), 올리는 곳=앱(GitHub Desktop)". 웹에선 커밋만 보이고 업로드는 앱에서 함.
5. 1~2분 뒤 apl-motion.com 에서 **Ctrl+Shift+R**(강력 새로고침)로 확인.


## ⚠️ index.html 편집 주의 (중요)
- 이 파일은 한때 로고 base64 내장으로 200KB·초장문 라인이었고, 그 상태에서 편집 도구가 **파일 끝(스크립트·닫는태그)을 반복적으로 잘랐음**. 그 결과 JS가 깨져 모든 .reveal 섹션이 안 보이는(모바일 검은화면) 사고가 두 번 발생.
- 현재는 **로고를 assets/ 외부파일로 환원해 ~30KB로 경량화**했고 `.reveal`도 JS 없이 보이게 안전화함.
- 향후 편집 후 **반드시 검증**: `grep -c "</html>" index.html`(=1), `grep -c "</script>"`(=1), JS 문법검사. 끝이 잘렸으면 스크립트 꼬리를 다시 붙일 것.
- 큰 편집은 한 번에 전체 재작성(bash/python)으로 처리하는 게 안전.

## 🛠 파일 구성
- `index.html` — 홈페이지 본체(단일 파일). **로고가 base64로 내장**되어 어디서 열어도 보임. 별도 폴더 불필요.
- `assets/` — 원본 로고 PNG(APL 마크/워드마크/스타, 흰색·검정) 보관용. index.html은 여기에 의존하지 않음(편집·재가공 시 사용).
- `CNAME`(저장소 폴더에만) — 커스텀 도메인 `apl-motion.com` 지정 파일. 지우지 말 것.

## ✏️ 링크 교체 위치 (가장 자주 바꾸는 곳)
`index.html` 맨 아래 `<script>`의 `CONFIG`:
- `appUrl` = https://apl2018.github.io/APL-Motion/  (APL Motion 앱)
- `storeUrl` = https://smartstore.naver.com/apl-motion
- `cafe` = https://cafe.naver.com/motionspecialist
- `instagram` = { mokdong, academy, hsq, da } (아래 계정 참고)
- `email` = aplspl2018@gmail.com

## 📇 콘텐츠 메모
- **인스타그램(함께하기 섹션, 5개)**: @apl_mokdong_ / @apl_academy / @n1_tr_hsq_ / @da_specialist_ / @runhaus_offcial
  (apl_academy·runhaus_offcial은 끝에 `_` 없음. 나머지 3개는 끝에 `_` 있음. runhaus는 철자 offcial 그대로)
- **회사 이메일(연락처·CONFIG)**: apl@apl-motion.com (→ ImprovMX → aplspl2018@gmail.com 수신)
- **RUNHAUS**: 경기 용인 기흥(어정로 134-24) 국내 최대 규모 러닝센터 — 러닝 레슨·HYROX·리커버리·스포츠뉴트리션. 사업영역(6번째)·센터(7번째)에 추가됨.
- **설립자(섹션 제목 "설립자")**: 함상규(㈜GPL 대표·Co-founder) / 김양수(㈜APL 대표·Co-founder).
  약력 원본 = 업로드한 「2025 APL 회사소개서.pdf」.
- **센터 6곳**(개별 나열): 목동(서울)·용인·용인2호·청라(인천)·울산·베이징.
- **사업영역 5개**: 엘리트 트레이닝 / APL Academy / APL Store / APL Motion / APV.
- 주소(서울 양천구 목동)는 사용자 요청으로 **삭제됨**(연락처엔 이메일만, 푸터엔 회사명만).

## ⚖️ 폰트·디자인 라이선스 (법적 안전)
- 본문 폰트 = **Inter** (SIL Open Font License, 상업적 사용 무료).
- 로고 = APL 자체 브랜드 자산. 네이버 등 외부 상표/로고는 사용 안 함(스토어는 텍스트 명칭으로만 안내).

---

## 🔧 핵심 레퍼런스 (배포·DNS·이메일)
**가비아 DNS** (apl-motion.com): A레코드 4개 + www CNAME + 메일용 MX/TXT
```
A     @     185.199.108.153        (GitHub Pages 고정 IP)
A     @     185.199.109.153
A     @     185.199.110.153
A     @     185.199.111.153
CNAME www   apl2018.github.io.
MX    @     mx1.improvmx.com.      우선순위 10   ← 끝에 점(.) 필수
MX    @     mx2.improvmx.com.      우선순위 20   ← 끝에 점(.) 필수
TXT   @     v=spf1 include:spf.improvmx.com ~all
```
**이메일(ImprovMX 무료)**: improvmx.com 로그인(aplspl2018@gmail.com) → 도메인 apl-motion.com →
별칭 `apl*` → aplspl2018@gmail.com 전달. (Apple엔 `apl@apl-motion.com` 사용)

**GitHub Pages**: 저장소 apl2018/apl-motion-home → Settings → Pages → Deploy from branch(main /root) → Custom domain = apl-motion.com.

---

## 📝 변경 이력
- 2026-06-18 (1차): 회사소개서 반영(Total Care & Solution, 사업영역, 공동대표 약력, 센터 개별 6곳), 실제 APL 로고 적용·base64 내장, 인스타 지표 삭제, 스토어 설명 '프로그램' 삭제, 함께하기 네이버 블로그 삭제, 네이버 'N' 로고 모방 요소 제거(상표 안전).
- 2026-06-18 (2차): 히어로 상단 'APL Motion 앱 열기' 버튼 제거→'사업영역/센터 보기'로 교체. '교육 콘텐츠' 카드 삭제. 대표자 이력 회사소개서 전체로 확장(김양수 8건/함상규 10건). 인스타 4계정·카페·스토어 실제 URL 연결. 주소 동 단위로 간소화. 히어로 별 오버레이 우측 이동.
- 2026-06-18 (3차·배포): GitHub 저장소 생성·Pages 배포, 가비아 DNS 연결, 커스텀 도메인 apl-motion.com 연결, ImprovMX 무료 이메일 포워딩 구성, Apple 조직 등록 신청 완료. (※ 배포 중 index.html 끝부분이 잘렸던 것 복구함 — 스크립트 누락 시 .reveal 섹션이 안 보이니 주의.)
- 2026-06-19 (4차): 섹션 제목 '대표 트레이너'→'설립자', 소제목 '두 공동대표가'→'두 설립자가'. 인스타 3개 끝에 `_` 추가(apl_mokdong_/n1_tr_hsq_/da_specialist_). 주소(서울 양천구 목동) 연락처·푸터에서 완전 삭제.
- 2026-06-19 (5차): RUNHAUS 추가 — 사업영역 카드(6번째, 🏃 러닝센터)·센터 카드(7번째, 경기 용인 기흥)·인스타 칩 @runhaus_offcial. 연락처/CONFIG 이메일을 apl@apl-motion.com 으로 변경.
- 2026-06-19 (6차): 로고를 base64 내장 → **assets/ 외부파일 방식으로 환원**(파일 30KB로 경량화, 잘림 근본원인 제거). `.reveal`을 기본 표시+`html.js` 게이트로 변경(JS 실패해도 검은화면 방지). 사업영역 카드에 링크 추가(엘리트→인스타2, Academy→인스타, Store→네이버스토어, Motion→앱실행, RUNHAUS→인스타). 브랜드↔APL Motion 사이에 **APV 섹션** 추가(pptx 반영). 이메일 표시 apl@apl-motion.com.
