# Tagmark v2.07

신형 로컬 DB/편집기 기반의 UI·Schema 개편 버전입니다. 구형 DB의 데이터를 읽거나 변환하지 않으며, 신형 IndexedDB 구조만 사용합니다.

## v2.07 핵심 방향
- Page 편집에서 Page 기본 필드 편집 기능 제거
- 새 Page는 사용자 필드를 자동 생성하지 않음
- 필드는 각 Tab의 필드 편집에서 직접 생성
- Field를 `데이터 타입 / 입력 방식 / 표시 방식`으로 분리
- 구형의 정보 입력·표시 방식을 신형 Schema 옵션으로 재구현
- 탭과 필드 순서를 화살표가 아닌 드래그로 변경
- Page/Tag Head도 드래그 정렬 지원
- 탭 추가는 탭 목록 마지막의 `＋` 버튼으로 통합
- 탭 편집 버튼은 Grid/List 및 정렬 컨트롤 라인의 오른쪽에 배치
- 태그 탭과 프로필 탭은 구형의 그룹/카드형 UI를 기반으로 유지하면서 신형 자유 Schema를 사용
- Folder는 별도 Folder Tab이 아니라 Bookmark/Profile 표시에서 같은 folderId를 가진 정보를 접고 펼치는 묶음으로 표시

## Field Schema
각 필드는 다음 정보를 별도로 가집니다.
- 데이터 타입: text, long_text, url, number, boolean, date, datetime, duration, image, color, rating, tag, profile, category, folder, relation, enum, markdown, json 등
- 입력 방식: 텍스트, 장문, 태그 검색, 프로필 검색, 프로필 추가, 토글, 라디오, 체크박스, 드롭다운, 숫자/날짜/기간/URL/색상/평점/JSON 등
- 표시 방식: 제목, 항목, 메모, 등장인물, 태그, 프로필, 이미지, 링크, 값, 배지, 숨김 등
- 선택형 입력은 필드별 선택지 목록을 직접 편집 가능
- 태그 입력 필드는 탭/필드별 Tag Head 제한을 사용 가능

## 구형 UI에서 반영한 표시 방식
- 제목: 등록된 URL이 있으면 제목을 하이퍼링크로 표시
- 항목: 제목 아래 중간 크기의 정보로 표시
- 메모: 작고 연한 회색 텍스트
- 등장인물: 큰 이름으로 표시하고 펼치기/접기 가능
- 프로필 태그: 프로필을 생성한 Profile Tab에서만 관리
- 일반 태그: Tag Tab에서 관리
- Folder: 같은 폴더에 속한 Bookmark/Profile을 하나의 접이식 묶음으로 표시

## 데이터 구조
- Database → Page → Tabs / Data
- Page: 독립적인 데이터 공간
- Tab: Page 데이터를 표시·편집하는 UI
- Page Data: Bookmark / Folder / Tag / Tag Head / Profile / Category
- Profile Tag: Profile이 생성하는 Tag의 한 종류
- Profile은 생성된 Profile Tab의 originTabId를 가짐
- Page 간 데이터는 기본적으로 공유하지 않음

## 백업
- 현재 신형 DB만 JSON으로 백업/복원
- 구형 DB를 읽거나 변환하지 않음
- 추출기용 Schema JSON 내보내기 지원

버전: v2.07
