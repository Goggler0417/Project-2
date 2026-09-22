# Tagmark v2.19

구형 Tagmark의 정보 입력 경험을 신형 범용 Schema DB 위에 컴포넌트로 재구축한 버전입니다.

## 핵심
- 신형 IndexedDB만 사용
- Bookmark Editor를 Title / URL / Category / Character / Artist / Series / Tag / Page-Duration / Note 컴포넌트로 분리
- 등장인물은 여러 행, 프로필 연결/직접 입력, 성별, 태그, 선택 복사/붙여넣기 지원
- Profile Editor도 구형 입력 흐름을 별도 컴포넌트로 구성
- Field마다 UI Component를 지정하여 같은 DB Schema를 페이지별 UI에 연결
- Tag Head 색상을 태그 칩에 자동 적용
- Page는 데이터 공간이며 필드는 Tab Schema에서 구성
- 구형 DB를 읽거나 변환하지 않음
