# Tagmark v2.46

## Import/Restore 관계 보존 수정
- 같은 Page ID의 Page 백업을 현재 Page 또는 Main에서 가져오면 개별 객체 병합을 하지 않고 Page 전체 스냅샷을 복원.
- 따라서 Bookmark `data[fieldId]`와 Tab `schema[field.id]`의 연결이 끊어지지 않음.
- 빈 동일 이름 Page에 Page 백업을 가져오는 경우도 전체 Page 구조를 복원.

## 다른 Page를 현재 Page에 추가하는 경우
- Tag Head, Tag, Category, Folder, Profile의 기존 항목을 먼저 중복 검사.
- 기존 항목과 연결되는 source ID → destination ID mapping 생성.
- 같은 종류/이름의 Tab은 기존 Tab에 연결하고 각 schema field를 `이름 + data type` 기준으로 대응.
- 없는 field는 destination schema에 추가.
- Bookmark data의 field ID key와 내부 참조 ID를 mapping 후 추가.
- Bookmark는 동일 URL을 우선 중복으로 판정.
- 동일 ID/Tag/프로필/카테고리/폴더 중복도 계속 검사.

이 버전은 v2.43~v2.45의 객체별 단순 병합으로 발생할 수 있던 `기록` 카드 문제를 수정합니다.
원본 백업 JSON에 정상 schema/data가 남아 있다면 해당 백업을 v2.46에서 다시 가져와 복원할 수 있습니다.
