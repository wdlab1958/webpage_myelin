# MYELIN 상세 화면 (ISMA3SC003M10)

**Nov. 25, 2026**

프로젝트에서 얻은 경험을 노트로 적고, 사람이 확인한 것만 검증된 노트로 올려 다음 일에 다시 쓰는 개인 지식 운영체계을 소개하는 화면입니다.
에이쓰리시큐리티 「One Cycle Dev. Framework」 화면의 **06 지식 자산화** 단계 카드에서 「자세히 보기」로 연결됩니다.

- Live: https://wdlab1958.github.io/webpage_myelin/
- One Cycle Dev. Framework: https://wdlab1958.github.io/a3sc/ ([저장소](https://github.com/wdlab1958/a3sc))
- 연동 대상 사이트: https://www.a3sc.co.kr/a3sc/ISMA3SC003M4.do (AI 플랫폼)

## 화면 구성

AI·보안 전문가가 아닌 독자도 읽을 수 있게, 비유 한 문장과 용어 풀이·자주 묻는 질문을 두었습니다.

| 구역 | 내용 |
|---|---|
| 히어로 | 노트는 내 PC에 저장 · 작업 명령(Skill) 7종 · 미엘린 강도 3단계 · 재사용 지표 9종 |
| 개요 | 배운 것이 흩어져 다시 헤매는 문제 — 산길 비유, 필요한 상황 4가지 |
| 동작 방식 | 메모에서 검증된 노트까지 6단계 |
| 주요 기능 | 다섯 묶음, 작업 명령 7종 |
| 승격과 강도 | verified 승격 조건 4가지, 강도 3단계 |
| 결과물 | 검증된 노트·Domain Pack 등 7가지와 한계 주석 |
| One Cycle 연결 | 앞뒤 단계와 주고받는 것, 이전·다음 플랫폼 이동 |
| 용어·FAQ | 용어 12개, 질문 7개 |
| 도입 문의 | 기존 화면과 같은 연락처 부품 |

## One Cycle 화면과 연결되는 구조

- 디자인은 기존 사이트의 `b.css` 를 그대로 쓰고, 그 위에 공통 확장 `onecycle_product.css` 만 더합니다. 선택자는 모두 `.pd-` 로 시작하며 다섯 플랫폼 화면이 같은 파일을 씁니다.
- 머리글·바닥글은 기존 화면(003M4)의 것을 그대로 가져옵니다.
- 화면 안에서 One Cycle 로 돌아가는 길이 세 곳 있습니다: 히어로의 현재 위치 표시, 여섯 단계 띠(`.pd-loop`), 아래쪽 이전·전체·다음 이동(`.pd-nav`).

| 단계 | 플랫폼 | 운영 주소(제안값) | 검토용 공개 주소 |
|---|---|---|---|
| 전체 | One Cycle Dev. Framework | `/a3sc/ISMA3SC003M5.do` | https://wdlab1958.github.io/a3sc/ |
| 02 품질 진단 | WDLAB-LLMOps | `/a3sc/ISMA3SC003M6.do` | https://wdlab1958.github.io/WDLAB-LLMOps-Webpage/ |
| 03 보안 분석·수정 | SSC | `/a3sc/ISMA3SC003M7.do` | https://wdlab1958.github.io/SSC-Platform-Webpage/ |
| 04 형식 검증 | WDLAB-Proof-Skills | `/a3sc/ISMA3SC003M8.do` | https://wdlab1958.github.io/webpage_proof_skills/ |
| 05 운영 감시 | ARGUS | `/a3sc/ISMA3SC003M9.do` | https://wdlab1958.github.io/ARGUS-Webpage/ |
| 06 지식 자산화 | MYELIN | `/a3sc/ISMA3SC003M10.do` | https://wdlab1958.github.io/webpage_myelin/ |

본문의 링크는 운영 주소로 적혀 있고, `build_preview.py` 가 `index.html` 을 만들 때만 `ROUTES` 표에 따라 공개 주소로 바꿉니다.

## 파일

```
.
├── fragment/ISMA3SC003M10_main.html   # 본문 (운영 화면의 <main> 안에 넣는 부분, 페이지 전용 스크립트 포함)
├── resources/css/A3/renewal/
│   ├── onecycle_product.css              # 플랫폼 상세 화면 공통 확장 (.pd-*)  ← 운영 서버에 올릴 파일
│   └── b.css                             # 기존 사이트 사본 (미리보기용, 올리지 않음)
├── resources/font, resources/images      # 기존 사이트 사본 (미리보기용, 올리지 않음)
├── reference/ISMA3SC003M4.html           # 머리글·바닥글을 가져오는 기존 화면 사본
├── build_preview.py                      # 미리보기·공개용 페이지 생성
├── ISMA3SC003M10.html                 # 미리보기 (운영과 같은 절대 경로)
└── index.html                            # GitHub Pages 용 (상대 경로, noindex)
```

## 운영 사이트에 붙이는 방법

1. 003M4 화면의 JSP를 복사해 새 화면(`ISMA3SC003M10`)을 만들고, `<main>` 안쪽을 `fragment/ISMA3SC003M10_main.html` 로 바꿉니다.
2. `<head>` 의 `b.css` 다음 줄에 추가합니다. (다섯 화면 공통, 한 번만 올리면 됩니다)
   `<link rel="stylesheet" href="/resources/css/A3/renewal/onecycle_product.css">`
3. `<title>`, description, canonical, og 값을 바꿉니다. (값은 `build_preview.py` 상단)
4. 상단 메뉴는 「AI 플랫폼」에 `class="on"` 을 둡니다. (003M4·003M5와 같음)

화면 번호는 제안값입니다. 다른 번호를 쓰면 본문의 `/a3sc/ISMA3SC003M…` 링크와 `build_preview.py` 의 `PAGE`·`ROUTES` 를 함께 바꿉니다.

## 미리보기

    python3 build_preview.py            # 본문을 고친 뒤 다시 만들기
    python3 -m http.server 8765         # http://127.0.0.1:8765/ISMA3SC003M10.html

## 내용 출처와 확인할 점

프로젝트 폴더 `MYELIN/` 의 `docs/guides/user-guide-v2.0/MYELIN_사용자가이드_v2.0.docx`, `docs/guides/user-guide.md`, `README.md`, `PHASE_STATE.md` 를 기준으로 썼습니다.
공개 화면이므로 가격·일정·내부 주소·고객 이름은 싣지 않았습니다.

- 일반 노트를 Claude에 맡기면 그 내용은 Claude로 전달됩니다. 기밀 노트는 로컬 LLM 세션 전용이라는 점과 함께 FAQ에 적었습니다.
- 앞 단계 산출물을 자동으로 받아들이는 연동은 문서에서 확인되지 않아 「사람이 자료를 넣거나 메모로 적는다」고 썼습니다.
- 제품 이름 MYELIN은 대외용으로 그대로 쓰기로 확정했습니다(2026-11-25).
- 현재 구성의 한계(1인·내 컴퓨터 전용, 명령줄 설치)를 주석으로 적었습니다.

---

© 2026 A3 Security. All rights reserved.
