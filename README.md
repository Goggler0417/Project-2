# Bookmark Database Editor v2.31

구형 UI의 동작을 범용 컴포넌트 구조로 정리한 첫 통합 버전입니다.

- 코드/클래스/함수명에서 `legacy` 계열 명칭 제거
- Bookmark/Profile 표시 컴포넌트 정리
- TagPicker / EntityInput 명칭과 역할 정리
- EntityInput에서 Profile 선택 시 성별 연동 유지
- Character 필드 설정에 성별별 추가 Tag Head 규칙 추가
- Entity의 성별 변경 시 검색 가능한 Tag Head 즉시 재계산
- Folder와 단독 Bookmark를 하나의 결과 스트림에서 정렬/표시
- 비어 있는 Duration을 `00:00:00`으로 저장/표시하지 않도록 수정
- 누락되어 있던 일반 Tag 삭제 동작 복구

DB는 기존 v2 계열 로컬 DB 구조와 호환됩니다.
