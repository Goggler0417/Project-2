# Tagmark v2.38

- Field Editor 레이아웃 재정렬: 좁은 화면에서도 필드 행과 미리보기가 서로 침범하지 않도록 수정.
- Bookmark/Profile Field Editor에 `＋ 등장인물 입력` 전용 버튼 추가.
- Character Field 내부 Schema는 해당 탭에 독립 저장되며 각 내부 Tag 입력마다 허용 Tag Head를 별도 지정.
- 여러 Profile 탭이 항상 첫 번째 Profile 탭 Schema를 사용하던 오류 수정. 등록/수정/프로필 태그 생성이 현재 Profile 탭을 사용.
- Profile 탭별 `표시할 프로필 종류` 설정 추가. 연결된 Profile Tag의 Tag Head를 기준으로 서로 다른 Profile 집합 표시 가능.
- Tag 추가 UI를 구형의 `사전 등록 태그` UI처럼 Tag 탭 안에 상시 표시: Tag Head 체크박스 → 태그 이름 → 등록.
- 탭에 터치/펜용 드래그 손잡이(≡) 복구. 마우스 HTML drag도 유지.
- 입력 방식에 `토글 버튼` 추가. 현재 Grid/List 버튼처럼 누를 때 상태와 표시 문구가 전환되며 Boolean 값으로 저장.
