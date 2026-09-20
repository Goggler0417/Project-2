# Bookmark DB Editor v1

현재 요청한 1~6번 구조를 구현한 독립 실행형 프로토타입입니다.

구현:
- Main Page
- Main 직속 Site / Category Page
- 페이지마다 독립된 데이터 공간
- 페이지별 독립 Data Schema
- 페이지별 Record / Category / Tag / Profile 저장 공간
- 페이지별 UI 진입점
- 페이지별 서로 다른 필드 구조
- 텍스트/URL/날짜/숫자/태그/프로필/카테고리 등 필드 타입
- 페이지 생성/삭제/수정
- Schema 필드 추가/삭제
- Record CRUD
- 페이지별 검색
- JSON Export
- localStorage 기반 로컬 저장

아직 의도적으로 넣지 않은 것:
- 자동 수집/추출기
- 사이트별 실제 extractor
- Cloud DB / 로그인 / 동기화
- Cross-page relation의 실제 연결 로직
- 고급 UI schema editor
