# Tagmark v2.52

## 긴급 수정: Character/Tag 검색 controller 복구
v2.51의 renderer 통합 과정에서 Character renderer를 교체하면서
`initBookmarkEditor`, `showSuggest`, `characterSuggest`, `entityTagSuggest`,
`tagPickerSuggest` 등 검색/이벤트 controller 블록이 함께 제거되는 회귀가 발생했다.

v2.52에서는 v2.51의 공통 `structuredInputControl()` renderer는 유지하면서
검색/이벤트 controller를 복구했다.

### Character 하위 Tag Search
- 입력칸 focus/input 이벤트가 다시 연결된다.
- 검색 결과 dropdown이 다시 열린다.
- 해당 하위 필드의 `allowedTagHeadIds`만 검색 범위로 사용한다.
- 하위 필드에 Tag Head 제한이 없으면 모든 일반 Tag를 검색한다.
- `tag.profileId`가 있는 Profile Tag는 일반 Tag 검색에서 제외한다.
- Character/Profile 검색과 일반 Tag 검색은 서로 분리된다.

### UI
- 기존 Character 행 shell은 유지.
- suggestion dropdown의 position/z-index/overflow를 보강해 modal/iPad 안에서 가려지지 않게 했다.
