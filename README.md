# Tagmark v2.48

- 모든 Tag 선택 표시를 기존 `.tb` Tag box로 통일. Tag Head + Tag 이름과 Tag Head 색상을 그대로 사용하고 입력기에서만 × 버튼을 추가.
- Character 입력기의 이름 검색을 일반 Tag 검색에서 실제 Profile 검색으로 변경.
- Profile ↔ Profile Tag 연결은 `Tag.profileId = Profile.id`를 정식 관계로 사용.
- Profile Input 검색도 잘못된 `Profile.profileTagId` 가정을 제거하고 `Tag.profileId` 역참조로 수정.
- Character field 설정에 `연결할 Profile 탭` 추가. 여러 Profile 탭이 있어도 명시적으로 데이터 소스를 고정 가능.
- 연결을 지정하지 않은 기존 DB는 Tag Head 관계 → Character/등장인물 이름의 Profile 탭 → 유일한 Profile 탭 순으로 자동 연결.
- Character 검색 결과 선택 시 `profileId`, Profile Tag, 이름, 성별을 연결/로드.
- Profile Input의 mirror/custom 모드는 source Profile Tab 관계를 바꾸지 않음.
