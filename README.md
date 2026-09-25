# Tagmark v3.05

기준: 사용자가 v3.04로 지정한 v3.01 기반 UI 통합판.

## 수정
- 탭 내비게이션을 `data-nav-tab` 전용 selector/controller로 분리.
- Bookmark → 다른 탭 → Bookmark 왕복 시 이전 탭 내용이 남는 치명적 렌더링 오류 수정.
- Bookmark 선택 Toolbar의 모든 버튼을 다시 연결.
- Page Settings에서 Field/Tag Head 설정 제거.
- Page Settings는 페이지 이름, 탭 순서/삭제, 가져오기, 내보내기, 페이지 DB 초기화만 제공.
- 각 탭에 `필드 설정` 버튼 추가. Field/Input 등록·수정·저장을 현재 탭에서 수행.
- 별도 `탭 설정` 추가. 현재 탭 이름/유형 설정 및 새 탭 추가. 유형은 북마크/프로필/태그/카테고리 4종.
- 별도 `태그 머리` 관리 팝업 추가. 추가/이름/색상/순서/삭제를 한 화면에서 관리.
- Tag Head 삭제 시 관련 Tag와 참조를 정리.

## 검증
- 모든 inline JavaScript `node --check`.
- Chromium headless + DevTools Protocol로 실제 클릭/입력 상호작용 테스트 수행.

## 실제 Chromium 상호작용 검사
통과:
- 북마크 → 태그/프로필/카테고리 → 북마크 반복 왕복
- 왕복 후 Bookmark 카드 재렌더링 및 수정 Modal 열기
- 체크박스 → 선택 Toolbar 자동 표시
- 현재 목록 전체 선택 / 선택 해제 / 태그 추가 / 폴더 생성 / 폴더에서 제외 / Profile 붙여넣기
- Page Settings 열기, Field/Tag Head 설정이 섞이지 않는지 확인, 페이지 이름 저장
- Tab Settings 열기, 4개 유형 확인, Profile 탭 실제 추가
- 탭별 Field Settings 열기, Field 편집 Modal 및 저장
- Tag Head Manager 열기, Head 추가 및 이름 변경 저장
