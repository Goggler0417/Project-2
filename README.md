# Tagmark v3.02

개발 모토: **DB에는 사실만 저장하고, Schema에는 구성 방법을 저장하고, UI가 그것을 해석한다.**

## v3.02 핵심 수정
- `메인 페이지 → 페이지 → 탭` 3단계 구조 추가
- 페이지 전환 UI 추가. Page마다 Tabs / Schema / Data가 독립
- 탭 이동 시 Bookmark가 Tag 탭으로 바뀌던 navigation selector 충돌 수정
- Page 설정에서 Field/Schema 설정 제거
- Main Page 설정: Page 생성/삭제/이름/순서
- Page 설정: Page 이름 및 Tab 생성/삭제/이름/순서
- Tab 설정: 현재 Tab의 Schema/Field 및 Tag Head 관리
- Tag Head 이름/색상 수정, 추가, 삭제, 순서 변경
- Bookmark의 등장인물 입력을 구형 구조에 가깝게 변경:
  - Character/Cast
  - 성별
  - 이름/기존 Profile 검색
  - 별도 등장인물 태그 검색/입력
  - Add Character/Cast 버튼
- 기존 공통 검색/정렬/오름·내림/목록·그리드/선택 구조 유지

## 검증
정적 JavaScript 문법 검사를 수행합니다. 실제 브라우저/iPad 자동 상호작용 테스트는 수행하지 않았습니다.
