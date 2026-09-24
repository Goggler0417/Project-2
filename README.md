# Tagmark v2.50

## Tag Head 기반 자동 분배
- Bookmark 수정창을 열 때 일반 Tag 필드에 섞여 있는 Tag를 검사한다.
- Tag의 `tagHeadId`가 특정 Tag 입력 필드의 `allowedTagHeadIds`와 일치하면 해당 항목 필드로 자동 배치한다.
- 저장 시에도 같은 분배를 한 번 더 적용한다.
- 따라서 구형 DB처럼 Series/Artist/Language 등 '항목으로 표시되는 Tag'가 일반 Tag에 남아 있어도 해당 항목으로 복원된다.
- 엔진은 Series/Artist 같은 이름을 하드코딩하지 않고 Field의 Tag Head 설정만 사용한다.

## Character/Profile Tag 자동 분배
- Character Profile 선택 시 그 Profile이 가진 Tag들을 읽는다.
- Character 내부 각 `tag_search` 필드의 `allowedTagHeadIds`와 비교해 일치하는 필드에 자동 입력한다.
- 기존 Bookmark를 수정할 때 Character의 일반 `tags`에 섞여 있던 Tag도 같은 규칙으로 각 내부 항목에 재배치한다.

## Character 일반 Tag 검색 수정
- Character의 일반 Tag 검색은 이제 Character/Profile Tag Head를 상속하지 않는다.
- 실제 해당 Character 하위 Tag 필드에 지정된 Tag Head만 사용한다.
- Profile Tag(`tag.profileId`가 있는 Tag)는 일반 Tag 검색 후보에서 제외한다.
- 직접 입력으로 새 Tag를 만들 때도 해당 하위 필드에 지정된 첫 Tag Head로 생성한다.
- Character 하위 필드별 Tag 삭제도 서로 독립적으로 처리한다.
