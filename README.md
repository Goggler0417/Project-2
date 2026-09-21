# Tagmark v2.05

신형 로컬 DB/편집기 기반의 정보 구조 및 편집 기능을 확장한 버전입니다. 구형 DB의 데이터를 읽거나 변환하지 않으며, 별도의 신형 IndexedDB에서 시작합니다.

## 핵심 데이터 구조
- Database → Page → (UI / Schema / Tabs / Data)
- Page: 독립적인 최상위 데이터 공간
- Tab: 데이터를 소유하지 않고 Page의 데이터를 표시·편집하는 UI
- Page Data: Bookmark / Folder / Tag / Tag Head / Profile / Category
- Profile Tag: Profile이 생성하는 Tag의 한 종류이며 Profile이 생성된 Profile Tab에서만 조회·편집
- Custom Field: 실제 값과 필드 정의를 분리하고 고유 ID로 연결

## Page / Tab
- 같은 유형의 Tab 여러 개 생성 가능
- Bookmark Tab만 Page당 1개로 제한
- Profile Tab에는 profileKind(series / group / custom)를 지정할 수 있음
- Profile은 자신을 생성한 Profile Tab의 originTabId를 저장
- Series Profile Tab에서는 해당 탭에서 생성된 Series 프로필과 프로필 태그만 표시
- Group Profile Tab도 동일한 방식으로 독립 표시
- Tag Tab에서는 일반 Tag만 표시·편집하며 Profile Tag는 표시하지 않음

## Schema
- Page 기본 Schema: 새 탭의 기본 필드
- Tab Schema: 실제 탭에서 저장/표시할 필드
- 필드의 순서를 위/아래 버튼으로 지정
- 필드 이름과 고유 ID를 분리
- 필수 / 표시 여부를 필드별로 지정
- 필드 타입: 텍스트, 장문, URL, 숫자, 체크, 날짜, 날짜·시간, 시간/기간, 이미지 URL, 색상, 평점, 태그, 프로필, 카테고리, 폴더, 관계, 선택, Markdown, JSON

## Tag
- Tag Head 순서를 위/아래 버튼으로 지정
- 구형 UI의 핵심 방식처럼 태그를 그룹별 접이식 영역으로 표시
- 검색어로 태그를 검색
- Tag Head별 태그 개수 표시
- 일반 Tag만 Tag Tab에서 CRUD
- Profile Tag는 해당 Profile Tab에서만 관리

## Tag 입력
- Bookmark/Profile 등의 Tag 입력은 HTML select 대신 검색형 Tag Picker 사용
- 텍스트 검색으로 태그를 찾을 수 있음
- Tag Head별로 접이식 그룹을 표시
- 다중 Tag 필드는 체크박스 방식으로 여러 개 선택
- 단일 Tag 필드는 단일 선택
- Tab 설정에서 태그 입력에 사용할 Tag Head를 체크박스로 제한 가능
- Tag Head를 하나도 선택하지 않으면 해당 Page의 일반 Tag 전체를 검색 가능
- 선택 모드의 일괄 Tag 추가도 동일한 검색형 Tag Picker 사용

## 순서 지정
- Page: Main Page에서 위/아래 버튼으로 순서 변경
- Tab: 탭 설정에서 위/아래 버튼으로 순서 변경
- Field: 필드 편집에서 위/아래 버튼으로 순서 변경
- Tag Head: 태그 머리 편집에서 위/아래 버튼으로 순서 변경
- Main Page에서 수동 순서를 선택하면 지정한 Page 순서대로 표시

## 추출기용 구조 내보내기
Page 편집 → `추출기용 DB 구조 내보내기`에서 현재 Page의 구조만 JSON으로 내보낼 수 있습니다.

내보내는 내용에는 다음이 포함됩니다.
- Page 정보
- Page 기본 Schema
- 모든 Tab의 유형 / 이름 / 순서 / UI / Profile 종류
- 각 Tab의 Schema
- Tab별 허용 Tag Head
- Tag Head 정의와 순서
- Category 정의
- 일반 Tag와 Profile Tag를 분리하는 정책 정보

실제 Bookmark/Profile 등의 데이터 레코드는 포함하지 않습니다. 따라서 이후 사이트별 추출기가 이 JSON을 입력으로 받아 어떤 정보를 어디에 넣을지 결정하는 구조로 사용할 수 있습니다.

## 데이터 편집
- Bookmark CRUD
- Folder CRUD
- 일반 Tag / Tag Head CRUD
- Profile CRUD 및 자동 Profile Tag 생성
- Profile Tag의 Tag Head / 색상 편집
- Category CRUD 및 상위 Category
- 선택 모드 / 일괄 Tag·Profile·Folder·삭제
- Grid/List, A→Z/Z→A, 수동 순서
- Page 삭제
- JSON 백업/복원 및 초기화

## 안전 설계
- IndexedDB 연결 객체와 앱 데이터 객체를 분리
- 데이터는 Page 단위로 완전히 독립
- 탭을 삭제해도 Page의 실제 데이터는 삭제하지 않음
- Profile 삭제 시 Profile Tag와 해당 참조를 정리
- Tag Head 삭제 시 Tag는 유지하고 연결만 제거
- Folder/Category 삭제 시 연결 참조를 정리

버전: v2.05
