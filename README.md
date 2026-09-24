# Tagmark v2.41

- 탭 순서 변경을 상단 탭 바에서 제거하고 Page 편집 안의 `탭 순서` 영역으로 이동.
- Page 편집에서 ≡ 드래그 또는 ↑/↓ 버튼으로 탭을 재정렬하고 Page 저장 시 `Page.tabs` 순서로 영구 저장.
- Tag 탭의 사전 등록 Tag Head 후보를 그 탭의 `표시할 태그 머리` 설정으로 제한.
- 사전 등록에서 선택한 Tag Head 체크 상태를 탭별로 저장해 태그 등록 후에도 유지.
- Bookmark/Profile Field Editor 행의 grid 폭/overflow를 다시 정리해 iPad 폭에서 겹침을 방지.
- Tag/Entity/Profile suggestion dropdown lifecycle을 통합: 새 목록을 열 때 이전 목록의 DOM 내용을 비우고 닫으며, 외부 클릭 시 모두 정리.
- Suggest 목록 버튼은 한 컨테이너 안에서만 렌더되도록 CSS를 고정해 이전 결과가 뭉쳐 보이는 현상을 방지.
