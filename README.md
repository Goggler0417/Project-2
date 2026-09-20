# Bookmark Database Editor v1.3

## 버전 규칙
- **버전:** v1.3
- **폴더:** `v1.3/`
- **메인 HTML:** `index.html`
- **README:** `README.md`

## 용어
- **신형:** 현재 개발 중인 범용 데이터베이스 모델
- **구형:** 이전 북마크 분류 모델
- **Main Page:** 실제 시작 화면이며 Page를 리스트/그리드로 보여줌
- **Page:** 하나의 독립적인 데이터 공간
- **Tab:** Page 내부의 기능/데이터 화면
- **팝업:** 추가·수정 작업창
- **태그 머리:** 이전에 '태그 카테고리'라고 부르던 상위 태그 그룹

## v1.3 구현 내용
- 실제 **Main Page** 추가
- Main Page의 **Grid/List 전환**
- 구형 모델의 정렬 버튼 방식에 맞춘 **A→Z / Z→A 오름차순·내림차순 전환**
- Page 상단의 중복 검색/편집/Tab 설정 UI 제거
- Page 제목 옆의 중복 `+ Tab` 제거: Tab 옆의 `＋`만 사용
- URL Field는 일반 Record 화면에 숨기고 **Record 수정 팝업에서만 표시**
- Tab 설정에서 URL Field를 선택하면 **Record 제목 자체가 하이퍼링크**가 됨
- **태그 Tab / 프로필 Tab / 카테고리 Tab / 커스텀 Tab** 구현
- Page마다 **태그 머리·태그·카테고리·프로필·등장인물**을 공유
- 태그 Tab에서 태그 머리와 태그를 추가/수정/삭제
- 프로필 Tab에서 프로필과 등장인물 관리
- 프로필과 등장인물의 연결 기능
- Bookmark Tab의 태그/카테고리/프로필 선택지를 Page 공유 데이터와 실시간 연동
- Page 설정에서 기능을 요소별로 켜고 끌 수 있음
- Tab 설정에서 **북마크/태그/프로필/카테고리/커스텀** 유형 선택
- 기존 상세 Field Schema 기능은 **고급 Schema**로 유지

## Page 기능 토글
- 북마크 기능
- 태그 기능
- 프로필 기능
- 카테고리 기능
- 등장인물 기능
- 프로필↔등장인물 연동

기능을 끄면 해당 기능의 기본 Tab이 화면에서 숨겨지며, 기존 데이터는 삭제하지 않습니다.

## 구조
```text
Main Page
├── Page A
│   ├── Bookmark Tab
│   ├── Tag Tab
│   ├── Profile Tab
│   └── Custom Tab ...
│
│   Shared Page Data
│   ├── 태그 머리
│   ├── 태그
│   ├── 카테고리
│   ├── 프로필
│   └── 등장인물
│
└── Page B
```

각 Page의 공유 데이터는 다른 Page와 분리됩니다.

## 구형과 신형의 관계
구형 모델을 그대로 복제하는 것이 아니라, 구형에서 사용하던 요소와 기능을 **Page별 선택 가능한 기능 모듈**로 분리하는 것이 신형의 방향입니다.

```text
RAW HYPERLINKS
↓
SITE-SPECIFIC EXTRACTOR
↓
PAGE / TAB DATA
↓
신형 BOOKMARK DATABASE
```

## 향후 확장
- Tab별 상세 화면/팝업 레이아웃 커스터마이징
- 태그 머리의 계층/규칙 확장
- 관계형 Relation UI
- Page 간 명시적 Relation
- 클라우드 업로드/다운로드 동기화
- 사이트별 Extractor
