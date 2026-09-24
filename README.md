# Tagmark v2.51

## 입력 Renderer 통합
- Character 내부 일반 필드와 Profile Input 내부 필드가 같은 `structuredInputControl()`을 사용한다.
- Text / Long Text / Tag Search / Radio / Checkbox / Dropdown / Cycle Button / Toggle / Number / Date / URL / Color가 동일한 규칙으로 렌더링된다.
- Character의 바깥 행 UI, 추가/복사/선택 구조는 유지했다.

## 필드 수정 반영
- Character 내부 필드의 Input Type 변경이 실제 입력 UI에 바로 반영된다.
- `태그 검색`으로 바꾸면 공통 Tag 검색 동작을 사용하고 해당 하위 필드의 `allowedTagHeadIds`만 참조한다.
- Dropdown/Checkbox/Radio/Cycle Button의 선택지를 Character 필드 설정에서 저장하도록 수정했다.
- 저장 시 각 Input Type에 맞는 값 읽기 로직도 통합했다.

## Tag 검색/표시 수정
- Character의 일반 Tag 검색은 Profile/Character Tag를 일반 태그 후보로 사용하지 않는다.
- 하위 필드별 Tag Head 설정을 독립적으로 사용한다.
- `.tb` 공통 Tag box의 × 삭제가 작동하지 않던 selector 오류를 수정했다.

## 자동 분배
- v2.50의 Tag Head 기반 Bookmark/Character 자동 분배는 유지한다.
- 일반 Tag에 섞인 항목형 Tag는 현재 Field의 `allowedTagHeadIds`에 따라 수정창에서 해당 필드로 복원된다.
- Profile 선택 시 Profile의 Tag도 Character 내부의 일치하는 Tag 필드로 분배된다.
