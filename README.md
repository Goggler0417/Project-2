# Tagmark v3.02 — v3.01 UI merge rebuild

기준 코드는 v3.01입니다. v3.02~v3.03의 Main/Page 데이터 모델 변경은 가져오지 않았습니다.

## 이번 버전의 방향
구형 UI 편의기능과 v3.01의 Schema 기반 UI를 조합하되, 가능한 한 데이터 구조는 v3.01을 유지했습니다.

## 주요 UI 변경
- Bookmark 카드 체크박스 상시 표시
- 하나 이상 선택하면 Bulk Toolbar 자동 표시
- 현재 표시 결과 전체 선택 / 선택 해제
- 선택 Bookmark 태그 추가 / 새 폴더 생성 / 폴더에서 제외 / 복사된 Profile 붙여넣기
- Bookmark Tag Filter: Tag Head별 접이식 목록, 클릭 순환 `중립 → 포함 → 제외 → 중립`
- Tag Count: Bookmark 기준, 한 Bookmark 안의 중복은 1회
- Profile Input을 단순 chip 목록이 아니라 반복되는 독립 박스로 표시
- Profile Entry별 체크박스, 삭제, 선택 복사
- 복사한 Profile을 Bookmark Bulk Toolbar에서 여러 Bookmark에 붙여넣기
- v3.01의 Field/Input/조건부 Input/Tag routing/Profile 종류 설정 유지
- Tag/Profile/Category/Custom 탭의 공통 검색·정렬·목록/그리드 UI 유지
- Tag 탭에 Bookmark 기준 사용량 정렬/표시 추가
- Page breadcrumb를 UI로 추가

## 주의
Profile Input 내부의 완전한 Bookmark-local 하위 Field 데이터 구조는 이번 UI 통합에서 새로 만들지 않았습니다. v3.01의 Profile ID 배열 구조를 유지하면서 박스형 UI와 복사/붙여넣기 UX를 먼저 적용했습니다.

정적 JavaScript 문법 검사를 통과했습니다. 실제 브라우저/iPad 자동 상호작용 테스트는 수행하지 않았습니다.
