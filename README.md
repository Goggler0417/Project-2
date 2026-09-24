# Tagmark v2.43

## Page 기준 Import / Export
- Main에서 백업/복원: 모든 Page를 내보냄.
- 특정 Page에서 백업/복원: 현재 Page 하나만 내보냄.
- 특정 Page에서 가져오기: 가져온 Page 데이터들을 현재 Page 안에 병합.
- Main에서 가져오기: 백업의 Page들을 전체 DB에 추가/병합.
- 초기화도 현재 위치에 맞춰 Main=전체 DB, Page=현재 Page로 동작.

## 중복 검사
가져오기 전에 중복 검사를 수행.
- 모든 객체: 동일 ID 검사.
- Bookmark: 동일 URL을 우선 중복으로 판정하고, URL이 없으면 정규화된 내용 비교.
- Tag: 같은 Tag Head + 같은 이름.
- Profile / Category / Folder: 같은 이름.
- Tab: 같은 이름 + 같은 Tab type.
- 중복은 건너뛰고 완료 메시지에 추가/중복 건수를 표시.
