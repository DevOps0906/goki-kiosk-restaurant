# CLAUDE.md — goki-kiosk-restaurant (고깃집 · 식당 설계서)

## 1. 이 저장소는 설계서입니다 (코드 없음)

- 고깃집 · 식당 업종의 **기획 · 디자인 · 화면 명세**만 있습니다. 이전 `tablet-kiosk-restaurant`(카운터 키오스크만)를 대신합니다.
- 운영 방식 3가지를 모두 다룹니다: **① 카운터 키오스크(선불)** · **② 테이블오더 나갈 때 결제(고깃집 기본)** · **③ 테이블오더 주문할 때 결제(간편결제)**. (`docs/03-operation-modes.md`)
- 실제 코드는 `tablet-kiosk-core`에 작성합니다.
  - 식당 업종 코드: `tablet-kiosk-core/apps/kiosk/lib/verticals/restaurant/`
  - 운영 방식(테이블 · 계산서 · 호출 · 카운터 정산)은 업종이 아니라 **core 공통 기능**: `tablet-kiosk-core/apps/kiosk/lib/core/` (core `docs/12-operation-modes.md`)
- 이 저장소에 코드 파일을 만들지 않습니다.

## 2. 함께 여는 방법

- 이 저장소는 core **옆에** 클론합니다 (core 안에 클론하지 않음).
- 멀티에이전트 팀(`.claude/agents/`)은 core 에만 있습니다. 이 저장소에 에이전트 · 스킬을 만들지 않습니다.

```bash
cd kiosk/tablet-kiosk-core
claude --add-dir ../goki-kiosk-restaurant
```

core 저장소의 `CLAUDE.md` 규칙이 우선이고, 이 저장소 문서는 식당 기능의 **무엇을 · 어떻게 보이게**를 정합니다.

## 3. 문서 우선순위

1. `specs/` — 화면별 동작 명세 (가장 우선)
2. `docs/03-operation-modes.md` — 운영 방식 · 테이블 계산서 규칙
3. `docs/01-vertical-rules.md` — 식당 업무 규칙 · 데이터 키 · 확장 지점
4. `DESIGN.md` — 테마 · 화면 목록
5. `design/*.dc.html`, `screenshots/*.png` — 디자인 원본 (크기 · 여백 · 글자 크기 기준, px = dp)
6. `PRD.md` — 범위 · 우선순위

명세와 디자인 원본이 다르면 **명세가 우선**이고, 차이는 `DESIGN.md` "디자인과 명세 차이" 표에 적습니다.

## 4. 수정 규칙

- `design/`, `screenshots/`는 디자인 캔버스에서 만든 원본입니다. 직접 고치지 말고, 디자인을 고친 뒤 다시 내보냅니다.
- 명세를 바꾸면 core의 관련 작업(`tasks/README.md`에 적힌 작업)과 맞는지 확인하고, 필요하면 core `tasks/README.md` "발견한 문제"에 적습니다.
- 운영 방식 규칙(`docs/03`)을 바꾸면 core `docs/12-operation-modes.md`와 함께 고칩니다 (두 문서가 같은 내용을 말해야 함).
- 문서는 한국어로 씁니다.
