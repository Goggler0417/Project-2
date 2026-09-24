# Tagmark v3.00 Prototype

개발 모토:
> DB에는 사실만 저장하고, Schema에는 구성 방법을 저장하고, UI가 그것을 해석한다.

## 이 프로토타입에 포함된 것
- 완전히 새로 구성한 로컬 IndexedDB 기반 상태 저장
- Page / Tab / Schema / Data 분리
- Field = 표시 컨테이너, Input = 실제 데이터 단위
- 값 / 태그 / 프로필 / 카테고리 정보 유형
- 제목 / 항목 / 태그 / 메모 / 프로필 표시 유형
- 한 Field 안의 복수 Input
- 단순 조건부 Input
- Page 값과 Duration(초 단위 저장)
- Tag Head 및 공용 TagPicker
- 표시 가능할 태그 머리 / 분배받을 태그 머리
- 공용 Tag Router
- Profile이 일반 대표 Tag를 자동 생성하는 구조
- Character를 Profile의 한 종류로 처리
- 등장인물 선택 입력과 별개의 '등장인물 태그 검색/입력' 영역
- 구형 스타일의 Bookmark Card / Folder / Tag folder / Profile card
- 짧은 Base36 ID allocator 구조
- JSON 백업/가져오기

## 프로토타입 범위
v3.00은 새 아키텍처를 검증하기 위한 첫 프로토타입입니다. 구형의 모든 세부 기능을 완성한 버전은 아닙니다.
브라우저 자동 상호작용 테스트는 수행하지 않았습니다.
