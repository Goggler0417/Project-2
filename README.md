# Tagmark v3.05

기준: v3.04 UI 통합판 + 신형 v2.10의 Main Page → Page → Tab 시스템 복원.

## Main Page
- v2와 같은 Main 화면
- Page 카드
- Page 추가 / 열기 / 이름·설명 수정 / 삭제
- Main Page 그리드·목록 전환
- 이름 A→Z / Z→A / 수동 순서 모드
- 좌측 Page 목록과 Main 버튼

## Page
- 각 Page가 자신의 Tabs, Schema, Bookmark, Tag, Profile, Category, Folder 데이터를 독립적으로 보유
- Page 전환 시 현재 Page 상태를 저장하고 대상 Page 상태를 불러옴
- Page 설정에서 Page 이름과 Tab 구성/순서를 관리

## Tab
- 기존 v3 Bookmark / Tag / Profile / Category / Custom 탭 유지
- 탭 클릭 selector를 전용 data-v305-tab으로 분리하여 다른 UI의 data 속성과 충돌하지 않도록 함
- Page를 이동했다 돌아와도 마지막 활성 Tab을 Page별로 저장

## 검증
- 모든 inline JavaScript에 node --check 수행
- Chromium headless에서 실제 클릭 기반 상호작용 테스트 수행
- Main → Page → Tab 전환, 다른 Tab 왕복, Bookmark 수정 modal 열기, Page 전환/복귀를 검사
