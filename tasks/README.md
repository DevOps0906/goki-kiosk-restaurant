# 고깃집 · 식당 관련 작업

> 작업 파일은 core 저장소 `tasks/`에 있습니다. 이 표는 이 설계서가 쓰이는 작업만 모은 것입니다.
> 운영 방식(테이블오더) 작업은 core **Phase 6b (task-028 ~ 034)** 입니다. 고깃집 트랙의 진행 순서 · 마일스톤은 [`docs/04-dev-plan.md`](../docs/04-dev-plan.md) 5장입니다.

## 운영 방식 (core 공통 · 이 저장소가 기준 설계)

| core 작업 | 내용 | 이 저장소에서 볼 문서 |
|---|---|---|
| task-028 | 운영 방식 · 테이블 · 열린 계산서 · 호출 스키마 | `docs/03-operation-modes.md` 2 · 6장, `docs/02-menu-seed.md` 테이블 |
| task-029 | ② 테이블 태블릿 화면 (대기 · 메뉴 · 확인 · 완료 · 내역) | `specs/table-order.md` 1~6장 |
| task-030 | 카운터 정산 (현황판 · 계산서 · 결제 · 이동 · 합석) | `specs/counter.md` |
| task-031 | 직원 호출 · 서빙 알림 | `specs/table-order.md` 7장, `docs/03` 6장 |
| task-032 | 운영 방식 세팅 · 테이블 배치 · 태블릿 역할 지정 | `specs/owner-setup.md` 2-2 · 4-2 · 4-3 |
| task-033 | ① 카운터 키오스크 나갈 때 결제 옵션 (테이블 번호 입력) | `specs/counter-kiosk.md` 4-2 |
| task-034 | ③ 테이블 선불 간편결제 (PG) — D9 결정 후 | `specs/table-prepay.md` |

## 식당 업종

| core 작업 | 이 저장소에서 볼 문서 |
|---|---|
| task-023 식당 모듈 (주 작업) | `specs/counter-kiosk.md` · `docs/01-vertical-rules.md` |
| task-018 더치페이 (인분 분할 확장 지점) | `docs/01-vertical-rules.md` 4장 |
| task-012 출력 (분류별 주방 주문서) | `docs/01-vertical-rules.md` 5장 |
| task-005 DB 시드 | `docs/02-menu-seed.md` |
| task-014 사장님 세팅 | `specs/owner-setup.md` |
| task-021 쿠폰 키오스크 | `specs/coupon.md` |
| task-025 스탠드형 세로 | `screenshots/` 번호만 있는 파일 |

## 완료 체크리스트

- [ ] `specs/table-order.md` 수용 시나리오 전부 통과
- [ ] `specs/counter.md` 수용 시나리오 전부 통과
- [ ] `specs/owner-setup.md` 수용 시나리오 전부 통과
- [ ] `specs/counter-kiosk.md` 수용 시나리오 전부 통과
- [ ] `specs/coupon.md` 수용 시나리오 전부 통과
- [ ] (D9 결정 후) `specs/table-prepay.md` 수용 시나리오 전부 통과
- [ ] core `/sync-design restaurant` 결과 차이 없음 (또는 `DESIGN.md` 5장에 기록)
