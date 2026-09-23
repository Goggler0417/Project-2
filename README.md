# Tagmark v2.40

- Profile 실제 등록/수정 팝업을 미리보기/Bookmark와 동일한 `fieldInput()` renderer로 통합.
- checkbox, dropdown, toggle, 순환 선택 버튼, date/datetime, number, URL, tag/profile/category/folder 입력 등 Field Editor 설정이 실제 Profile 팝업에도 적용.
- Profile 저장 역시 `readGenericField()`를 사용하도록 통합.
- 탭 순서 변경을 Pointer Events 기반으로 재구현.
- iPad/Safari용 확실한 대체 조작으로 `탭 순서` 모드와 ←/→ 버튼 추가. 변경 즉시 DB에 저장.
