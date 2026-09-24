# Tagmark v2.49

## Character/Profile 검색 수정
- v2.44에서 modal stack을 도입하면서 modal id가 `modal-1`, `modal-2` 형태로 바뀌었지만,
  Bookmark/Character 초기화 코드는 계속 `#modal`만 찾고 있었음.
- 그 결과 Character 이름 입력칸에 `input`/`focus` 검색 이벤트가 실제로 연결되지 않았음.
- 현재 최상위 modal을 찾아 초기화하도록 수정.

## 기존/가져온 Profile 호환
- Profile 이름 검색을 `profile.name` 하나에 의존하지 않고 연결된 Profile 탭의
  `profile_title`/이름 필드에서 직접 읽음.
- 정식 관계 `Tag.profileId = Profile.id`와 Profile 탭의 `profileTagHeadId`를 우선 사용.
- 오래된/가져온 데이터에서 Profile Tag 또는 Tag Head 연결이 일부 누락된 경우에도,
  연결된 Profile 탭의 이름 필드가 존재하면 검색 후보에서 사라지지 않도록 fallback 추가.
- Character와 새 Profile Input 검색 양쪽에 동일하게 적용.

## Suggest UI
- iPad modal 내부에서도 Character/Profile suggestion이 행 밖으로 표시되도록
  overflow/z-index/absolute positioning을 보강.
