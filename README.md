# Bookmark Database Editor v1.5

구형의 최상위 카테고리를 신형의 Main Page → Page로 매핑하고, Page 내부는 신형 Tab 구조를 사용하면서 구형의 로컬 기능을 유지합니다.

- Main Page: Grid/List, 스크롤, A→Z/Z→A, Page 추가/이름 변경/삭제
- Page: 구형 최상위 카테고리
- Tab: 메인 / 태그 관리 / 프로필
- 구형 하위 카테고리는 Page 내부 데이터로 유지
- Page별 북마크/태그/프로필/카테고리/등장인물/프로필↔등장인물 기능 ON/OFF
- 기존 Tagmark IndexedDB 사용
- Supabase 로그인/업로드/다운로드/Realtime 동기화 제거
- 로컬 백업/가져오기 유지

ZIP 내부 구조:
```text
v1.5/
├── index.html
└── README.md
```
