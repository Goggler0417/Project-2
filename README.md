# Tagmark v2.02

신형 데이터 구조를 기준으로 새로 작성한 로컬 북마크 데이터베이스/에디터입니다.

## 핵심 구조
- Main Page → Page → Tab
- Page별 독립 데이터 공간
- Tab별 독립 Schema / Records
- Page 공유 태그 머리·태그·카테고리·폴더·프로필·등장인물
- 외부 구형 DB를 읽거나 사용하는 기능 없음
- Supabase/로그인/클라우드 동기화 없음

## 주요 기능
- Main Page Grid/List 전환과 A→Z/Z→A 정렬
- Page 추가/편집/삭제
- Tab 추가/편집/삭제에 필요한 신형 구조
- Tab별 사용자 정의 Schema
- 북마크 Record CRUD 및 URL 링크
- 선택 모드와 일괄 태그/등장인물/폴더/삭제
- 자유로운 태그 머리 생성·이름 변경·색상 지정
- 태그 생성·편집·색상 지정
- 프로필/등장인물 CRUD와 상호 참조
- 폴더 CRUD와 Record 연결
- Page 기능 ON/OFF
- JSON 백업/복원
- 모바일 사이드바 및 반응형 UI

버전: v2.02
