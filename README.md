# Tagmark v3.03

개발 모토: **DB에는 사실만 저장하고, Schema에는 구성 방법을 저장하고, UI가 그것을 해석한다.**

## v3.03
- 기존 데이터에서 Profile/등장인물 입력 필드가 사라졌다면 Schema를 자동 복구
- 북마크 편집기의 구형식 Character/Cast 반복 입력 복구
  - Character/Cast
  - 성별
  - 기존 Profile 검색 / 새 등장인물 생성
  - 등장인물 전용 일반 태그 검색
  - 여러 등장인물 추가/삭제
- Profile 탭에서 Profile 수정/삭제 및 일반 태그 편집 복구
- Profile 이름과 연결된 일반 태그는 자동 생성/갱신
- Profile 표시 색상 규칙을 Schema 설정으로 추가
  - 색상 기준 Tag Head 선택
  - 해당 Tag Head의 각 Tag 값마다 색상 선택
  - Profile/등장인물 이름 표시 시 적용
- Tag 사용량은 Bookmark 단위로 계산
  - 같은 Bookmark 안에서 동일 Tag가 여러 경로/여러 번 등장해도 1회
  - Profile을 통해 들어온 Tag도 해당 Bookmark에 존재하는 Tag로 계산
- Tag 탭 TagChip에 Bookmark 기준 사용량 표시

## 검증
JavaScript 정적 문법 검사를 수행했습니다.
실제 브라우저/iPad 자동 상호작용 테스트는 수행하지 않았습니다.
