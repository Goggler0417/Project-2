# Tagmark v2.47

- v2.45 이후 검색형 입력의 선택 UI가 과도하게 큰 이중 pill 형태로 보이던 CSS를 수정.
- 선택된 Tag/Profile/Category/Folder 값은 다시 작고 일정한 chip 형태로 표시.
- Profile Input(등장인물 입력기 포함)의 상단 Profile 선택을 고정 `<select>`에서 텍스트 검색형 입력으로 변경.
- 등장인물/프로필 이름을 입력하면 해당 Profile 탭과 연결된 Profile 후보가 아래 suggestion으로 표시.
- 후보 선택 시 `profileId`를 연결하고 해당 Profile의 필드 데이터를 Profile Input에 자동 로드.
- Enter 첫 후보 선택 / Escape 닫기 지원.
- Profile Input에 Profile Tag Head가 지정되어 있으면 해당 종류의 Profile만 후보로 검색.
- 검색 텍스트를 직접 수정하면 기존 profileId 연결은 해제되어 잘못된 Profile 연결이 저장되지 않음.
