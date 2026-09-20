# Tagmark v2.04

정보 저장 구조를 다시 정리한 신형 로컬 DB/편집기입니다. 구형 DB의 데이터를 읽거나 변환하지 않으며, 별도의 신형 IndexedDB에서 시작합니다.

## 핵심 데이터 구조
- Database → Page → (UI / Schema / Tabs / Data)
- Page: 독립적인 최상위 데이터 공간
- Tab: 데이터를 소유하지 않고 Page의 데이터를 표시·편집하는 UI
- Page Data: Bookmark / Folder / Tag / Tag Head / Profile / Category
- Profile Tag: Profile이 생성하는 Tag의 한 종류이며 일반 Tag와 동일하게 Tag Head를 가질 수 있음
- Custom Field: 실제 값과 필드 정의를 분리하고 ID로 연결

## Schema
- Page 기본 Schema: 새 탭의 기본 필드
- Tab Schema: 실제 탭에서 저장/표시할 필드. Page 기본 Schema와 독립적으로 수정 가능
- 필드 타입: 텍스트, 장문, URL, 숫자, 체크, 날짜, 날짜·시간, 시간/기간, 이미지 URL, 색상, 평점, 태그, 프로필, 카테고리, 폴더, 관계, 선택, Markdown, JSON
- 필드 이름과 고유 ID를 분리하여 이름 변경에 대비
- 필수/표시 여부를 필드별로 지정

## Tab 규칙
- 같은 유형의 Tab 여러 개 생성 가능
- Bookmark Tab만 Page당 1개로 제한
- Tag / Profile / Category / Folder / Custom Tab은 여러 개 생성 가능
- Tab 삭제는 실제 Page 데이터를 삭제하지 않음

## 데이터 편집
- Bookmark CRUD
- Folder CRUD
- Tag / Tag Head CRUD
- Profile CRUD 및 자동 Profile Tag 생성
- Category CRUD 및 상위 Category
- 선택 모드 / 일괄 Tag·Profile·Folder·삭제
- Grid/List, A→Z/Z→A, 검색
- Page 삭제
- JSON 백업/복원 및 초기화

## 안전 설계
- IndexedDB 연결 객체와 앱 데이터 객체를 분리
- 데이터는 Page 단위로 완전히 독립
- 탭을 삭제해도 Page의 실제 데이터는 삭제하지 않음
- Profile 삭제 시 Profile Tag와 해당 참조를 정리
- Tag Head 삭제 시 Tag는 유지하고 연결만 제거
- Folder/Category 삭제 시 연결 참조를 정리

버전: v2.04
