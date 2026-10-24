# DESIGN — 고깃집 · 식당 키오스크

> 공통 디자인 시스템은 core `DESIGN.md`. 이 문서는 식당 테마, 운영 방식별 화면 목록, 전용 컴포넌트입니다.
> 디자인 캔버스 원본은 `design/`(`canvas.json` + `*.dc.html`), 미리보기는 `screenshots/`.

## 1. 식당 테마 토큰

| 토큰 | 값 |
|---|---|
| `primary` | `#007A64` |
| `primary-strong` | `#00473A` |
| `primary-tint` | `#E3F7F2` |
| `accent` | `#00C9A7` |
| `ink` | `#12201D` |
| `ink-muted` | `#4A5B57` |
| `background` | `#F4F8F7` |
| `line` | `#D5E2DE` |
| `discount` | `#C81E3F` |

### 운영 방식 상태 색 (core 공통 토큰으로 승격 대상)

| 토큰 | 값 | 쓰임 |
|---|---|---|
| `status-dining` | `#E3F7F2` / 테두리 `#007A64` | 식사 중 테이블 |
| `status-call` | `#FEF3D7` / 테두리 `#F59E0B` / 글자 `#7A4A00` | 호출 중, `직원 호출` 버튼 |
| `status-bill` | `#E8EFFE` / 테두리 `#2563EB` / 글자 `#0B2F85` | 계산 요청, ③ 선불(간편결제) |
| `status-empty` | `#FFFFFF` / 점선 `#D5E2DE` | 빈 테이블 |

## 2. 식당 문구

| 항목 | 값 |
|---|---|
| ① 번호 이름 | 호출번호 (예: `A-017`), `A-001`부터 매일 다시 시작 |
| ② ③ 번호 이름 | 테이블 번호 (예: `12번 테이블`), 주문서 `테이블 12` |
| ② 결제 안내 | "결제는 나가실 때 카운터에서" (상단 고정) |
| ③ 결제 안내 | "주문할 때 휴대폰으로 결제" (상단 고정) |
| ① 완료 후 처음 화면 | 30초 뒤 |
| ② 주문 전송 후 메뉴 화면 | 10초 뒤 |
| ② 무입력 → 대기 화면 | 1분 (담은 주문 유지) |

## 3. 화면 목록

### 운영 방식 · 구조도 · 흐름도

| 화면 | 원본 | 미리보기 |
|---|---|---|
| 00 운영 방식 비교 (① 카운터 · ② 테이블 후불 · ③ 테이블 선불) | [`mode-compare`](design/mode-compare.dc.html) | [PNG](screenshots/mode-compare.png) |
| 01 시스템 구조도 (새 구조) | [`08-structure`](design/08-structure.dc.html) | [PNG](screenshots/08-structure.png) |
| 02 테이블 상태 흐름 | [`09-table-state`](design/09-table-state.dc.html) | [PNG](screenshots/09-table-state.png) |
| 03 운영 방식별 주문 · 결제 흐름도 | [`07-flow`](design/07-flow.dc.html) | [PNG](screenshots/07-flow.png) |

### ② 테이블오더 · 나갈 때 결제 — 테이블 태블릿 (가로 1280×800)

| 화면 | 원본 | 미리보기 |
|---|---|---|
| TO 00 대기 화면 (테이블 번호) | [`to-00-idle`](design/to-00-idle.dc.html) | [PNG](screenshots/to-00-idle.png) |
| TO 01 메뉴 · 이번 주문 | [`to-01-menu`](design/to-01-menu.dc.html) | [PNG](screenshots/to-01-menu.png) |
| TO 01-2 주류 · 음료 (19세) | [`to-01b-drinks`](design/to-01b-drinks.dc.html) | [PNG](screenshots/to-01b-drinks.png) |
| TO 02 주문 확인 (주방으로 보내기) | [`to-02-confirm`](design/to-02-confirm.dc.html) | [PNG](screenshots/to-02-confirm.png) |
| TO 03 주문 전송 완료 | [`to-03-sent`](design/to-03-sent.dc.html) | [PNG](screenshots/to-03-sent.png) |
| TO 04 우리 테이블 주문 내역 (누적) | [`to-04-history`](design/to-04-history.dc.html) | [PNG](screenshots/to-04-history.png) |
| TO 05 직원 호출 (불판 · 숯 · 물 …) | [`to-05-call`](design/to-05-call.dc.html) | [PNG](screenshots/to-05-call.png) |

### ③ 테이블오더 · 주문할 때 결제 + ① 나갈 때 결제 옵션

| 화면 | 원본 | 미리보기 |
|---|---|---|
| TP 03 휴대폰 간편결제 (QR) · 나갈 때 결제 | [`tp-03-pay`](design/tp-03-pay.dc.html) | [PNG](screenshots/tp-03-pay.png) |
| TP 04 결제 완료 · 주방 전송 | [`tp-04-done`](design/tp-04-done.dc.html) | [PNG](screenshots/tp-04-done.png) |
| ① 옵션 · 테이블 번호 입력 (나갈 때 결제 매장) | [`sw-02b-table`](design/sw-02b-table.dc.html) | [PNG](screenshots/sw-02b-table.png) |

### 카운터 정산 태블릿 (가로 1280×800)

| 화면 | 원본 | 미리보기 |
|---|---|---|
| CT 01 테이블 현황판 · 호출 | [`ct-01-board`](design/ct-01-board.dc.html) | [PNG](screenshots/ct-01-board.png) |
| CT 02 테이블 계산서 · 결제 | [`ct-02-bill`](design/ct-02-bill.dc.html) | [PNG](screenshots/ct-02-bill.png) |
| CT 03 테이블 이동 · 합석 | [`ct-03-move`](design/ct-03-move.dc.html) | [PNG](screenshots/ct-03-move.png) |
| CT 04 주방 주문서 (첫 주문 · 추가 · 선불) | [`ct-04-slips`](design/ct-04-slips.dc.html) | [PNG](screenshots/ct-04-slips.png) |

### 사장님 세팅 — 갤럭시탭형

| 화면 | 원본 | 미리보기 |
|---|---|---|
| SW 세팅 1 사장님 시작 | [`set-01-start`](design/set-01-start.dc.html) | [PNG](screenshots/set-01-start.png) |
| SW 세팅 2 매장 정보 | [`set-02-store`](design/set-02-store.dc.html) | [PNG](screenshots/set-02-store.png) |
| SW 세팅 2-2 운영 방식 (①②③) | [`set-02b-mode`](design/set-02b-mode.dc.html) | [PNG](screenshots/set-02b-mode.png) |
| SW 세팅 3 메뉴 등록 | [`set-03-menu`](design/set-03-menu.dc.html) | [PNG](screenshots/set-03-menu.png) |
| SW 세팅 4 결제 단말 · 프린터 연결 | [`set-04-devices`](design/set-04-devices.dc.html) | [PNG](screenshots/set-04-devices.png) |
| SW 세팅 4-2 테이블 배치 · 태블릿 연결 | [`set-04b-tables`](design/set-04b-tables.dc.html) | [PNG](screenshots/set-04b-tables.png) |
| SW 세팅 4-3 태블릿 역할 지정 (테이블 태블릿에서) | [`set-04c-pair`](design/set-04c-pair.dc.html) | [PNG](screenshots/set-04c-pair.png) |
| SW 세팅 5 키오스크 모드 | [`set-05-kiosk`](design/set-05-kiosk.dc.html) | [PNG](screenshots/set-05-kiosk.png) |

### ① 카운터 키오스크 — 갤럭시탭형 (가로 1280×800)

| 화면 | 원본 | 미리보기 |
|---|---|---|
| SW 00 시작 화면 (매장/포장) | [`sw-00-start`](design/sw-00-start.dc.html) | [PNG](screenshots/sw-00-start.png) |
| SW 01 메뉴 선택 (갈비) | [`sw-01-menu`](design/sw-01-menu.dc.html) | [PNG](screenshots/sw-01-menu.png) |
| SW 01-2 주류 · 음료 | [`sw-01b-drinks`](design/sw-01b-drinks.dc.html) | [PNG](screenshots/sw-01b-drinks.png) |
| SW 02 주문 확인 | [`sw-02-cart`](design/sw-02-cart.dc.html) | [PNG](screenshots/sw-02-cart.png) |
| SW 03 결제 방법 선택 · 쿠폰 | [`sw-03-pay`](design/sw-03-pay.dc.html) | [PNG](screenshots/sw-03-pay.png) |
| SW 04 더치페이 (인분 · 메뉴별) | [`sw-04-dutch`](design/sw-04-dutch.dc.html) | [PNG](screenshots/sw-04-dutch.png) |
| SW 05 주문 완료 · 주방 주문서 | [`sw-05-done`](design/sw-05-done.dc.html) | [PNG](screenshots/sw-05-done.png) |

### ① 카운터 키오스크 — 스탠드형 (세로 800×1280)

| 화면 | 원본 | 미리보기 |
|---|---|---|
| HW 00 시작 화면 (매장/포장) | [`00-start`](design/00-start.dc.html) | [PNG](screenshots/00-start.png) |
| HW 01 메뉴 선택 (갈비) | [`Main`](design/Main.dc.html) | [PNG](screenshots/Main.png) |
| HW 01-2 주류 · 음료 | [`01b-drinks`](design/01b-drinks.dc.html) | [PNG](screenshots/01b-drinks.png) |
| HW 02 주문 확인 | [`02-cart`](design/02-cart.dc.html) | [PNG](screenshots/02-cart.png) |
| HW 03 결제 방법 선택 · 쿠폰 | [`03-pay-method`](design/03-pay-method.dc.html) | [PNG](screenshots/03-pay-method.png) |
| HW 04 더치페이 (메뉴별 · 인분) | [`04-dutch`](design/04-dutch.dc.html) | [PNG](screenshots/04-dutch.png) |
| HW 05 주문 완료 · 주방 주문서 | [`05-done`](design/05-done.dc.html) | [PNG](screenshots/05-done.png) |

### 기획 참고

| 화면 | 원본 | 미리보기 |
|---|---|---|
| 06 반응형 구간 · 폰트 기준 | [`06-responsive`](design/06-responsive.dc.html) | [PNG](screenshots/06-responsive.png) |
| 설치 방식 비교 (HW vs SW) | [`install-compare`](design/install-compare.dc.html) | [PNG](screenshots/install-compare.png) |

### 쿠폰

| 화면 | 원본 | 미리보기 |
|---|---|---|
| 쿠폰 1 사장님 쿠폰 관리 대시보드 (반응형) | [`coupon-dashboard`](design/coupon-dashboard.dc.html) | [PNG](screenshots/coupon-dashboard.png) |
| 쿠폰 2 사장님 쿠폰 발행 (반응형) | [`coupon-create`](design/coupon-create.dc.html) | [PNG](screenshots/coupon-create.png) |
| 쿠폰 3 손님 · 스탠드형 시리얼 입력 | [`hw-coupon-serial`](design/hw-coupon-serial.dc.html) | [PNG](screenshots/hw-coupon-serial.png) |
| 쿠폰 4 손님 · 스탠드형 바코드 스캔 | [`hw-coupon-scan`](design/hw-coupon-scan.dc.html) | [PNG](screenshots/hw-coupon-scan.png) |
| 쿠폰 5 손님 · 갤럭시탭 시리얼 입력 | [`sw-coupon-serial`](design/sw-coupon-serial.dc.html) | [PNG](screenshots/sw-coupon-serial.png) |
| 쿠폰 6 손님 · 갤럭시탭 바코드 스캔 | [`sw-coupon-scan`](design/sw-coupon-scan.dc.html) | [PNG](screenshots/sw-coupon-scan.png) |

## 4. 식당 · 운영 방식 컴포넌트

| 컴포넌트 | 구분 | 설명 | 디자인 |
|---|---|---|---|
| `AlcoholBanner` | 식당 | 주류 · 음료 분류 상단 19세 안내 | `01b-drinks`, `to-01b-drinks` |
| `AdultBadge` | 식당 | 메뉴 카드 `19` 배지 | `01b-drinks`, `to-01b-drinks` |
| `PortionStepper` | 식당 | 인분 − + (첫 주문 최소 인분) | `Main`, `to-01-menu` |
| `PortionSplitList` | 식당 | 더치페이 메뉴별 인분 배정 | `04-dutch` |
| `TableBadge` | core 운영 방식 | 상단 테이블 번호 배지 (② 초록 · ③ 파랑) | `to-*`, `tp-*` |
| `RoundCartPanel` | core 운영 방식 | 이번 주문(N차) 패널 + 결제 안내 | `to-01-menu` |
| `RoundHistoryCard` | core 운영 방식 | 차수별 주문 카드 + 주방 상태 칩 | `to-04-history` |
| `StaffCallGrid` | core 운영 방식 | 호출 항목 버튼 (항목은 업종 `labels`) | `to-05-call` |
| `TableTile` | core 운영 방식 | 현황판 테이블 카드 (상태 색) | `ct-01-board` |
| `BillSheet` | core 운영 방식 | 계산서 줄 목록 + 받을 금액 + 결제 버튼 | `ct-02-bill` |
| `TablePicker` | core 운영 방식 | 이동 · 합석 테이블 선택 | `ct-03-move` |
| `PayQr` | core 운영 방식 (③) | 간편결제 QR + 남은 시간 | `tp-03-pay` |
| `NumberPad` | core 공통 | 테이블 번호 · PIN 입력 | `sw-02b-table`, `set-04c-pair` |

공통 컴포넌트는 core `DESIGN.md` 6장.

## 5. 디자인과 명세 차이

| 화면 | 디자인 원본 | 구현 기준 |
|---|---|---|
| `set-03-menu` 메뉴 등록 | 분류 칩 `찌개·탕` | `찌개 · 탕` 표기 통일 |
| 시작 화면 | `한국어 · English`, `큰 글씨 · 낮은 화면` 버튼 | MVP에서는 숨김 (core D8, task-026) |
| `to-*` 상단 `주문 내역 66,000` | 고정 예시 값 | 실제 계산서 합계 (3차 전송 후 104,000원) |
| `set-02-store` 업종 칩 | 식당 · 카페 · 버거 · 분식 · 기타 | 운영 방식은 다음 화면 `set-02b-mode`에서 고름 |
| `to-04-history` 주방 상태 `조리 중` · `나감` | 표시됨 | MVP는 `접수`만 (KDS 연동 후) — `specs/table-order.md` 6장 |
