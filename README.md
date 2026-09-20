# Bookmark Database Editor v1.8

- 구형 기능을 신형 Main Page → Page → Tab 구조로 통합
- Supabase 기능 제거
- IndexedDB 초기화 경로를 안정화하고 Page/하위 카테고리 생성 시 DB 준비를 명시적으로 대기
- IndexedDB 초기화 실패/blocked 상태의 원인을 사용자에게 표시
- 기존 로컬 데이터 보존을 우선하며 스키마 생성은 기존 object store가 없을 때만 수행
