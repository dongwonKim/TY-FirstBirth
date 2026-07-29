# 돌잔치 초대장 웹페이지

GitHub Pages로 바로 배포할 수 있는 1인용 돌잔치 초대장입니다.

## 폴더 구성
```
dol-invitation/
├── index.html              ← 초대장 본문 (이 파일 하나로 동작)
├── assets/
│   └── baby-photo-sample.svg   ← 샘플(예시) 이미지 — 실제 아기 사진으로 교체할 자리
└── README.md
```

## 1. 내 아기 사진으로 교체하기
1. `assets` 폴더에 원하는 사진 파일을 넣어주세요. (예: `baby-photo.jpg`)
2. `index.html`을 열어 아래 두 곳을 찾아 `src` 경로만 바꿔주세요.
   - 메인 직사각형 사진: `<img id="babyPhoto" src="assets/baby-photo-sample.svg" ...>`
   - 하단 갤러리 3장: `<div class="g-item"><img src="assets/baby-photo-sample.svg" ...>` (3곳)
   - 예: `src="assets/baby-photo-sample.svg"` → `src="assets/baby-photo.jpg"`
3. 메인 사진은 세로형 직사각형(가로:세로 = 4:5)에 가까울수록 프레임에 예쁘게 맞습니다.

## 2. 문구·날짜·장소 수정하기
`index.html` 맨 아래 `<script>` 안의 `config` 객체 값만 바꾸면 페이지 전체 텍스트가 자동으로 바뀝니다.

```js
const config = {
  babyName: "김태유",            // 아기 이름
  ribbonName: "🎀 태유",         // 사진 위 리본 태그에 들어갈 짧은 이름
  dateShort: "2026년 8월 2일 일요일",
  dateFull: "2026년 8월 2일 (일) 오전 11:00",
  greetingHtml: `...인사말...`,
  parentsLine: "김민수 · 박지현 의 딸, 김태유",
  venueName: "그랜드 컨벤션 웨딩홀",
  venueAddress: "서울특별시 강남구 테헤란로 123, 3층 그랜드홀",
  mapUrl: "https://map.naver.com",   // 네이버지도/카카오맵 공유 링크로 교체
  contact: "참석 여부나 궁금하신 점은 편하게 연락 주세요 · 010-1234-5678",
  doljabiSub: "태유가 무엇을 잡을지 함께 지켜봐 주세요",
  galleryTitle: "태유의 첫 1년",
  footerContact: "축하와 사랑으로 태유의 첫 생일을 빛내주세요"
};
```

## 3. GitHub Pages로 배포하기
1. GitHub에서 새 저장소(repository)를 만듭니다. (예: `our-baby-dol`)
2. 이 폴더 안의 `index.html`, `assets` 폴더, `README.md`를 저장소에 업로드(커밋)합니다.
   - GitHub 웹사이트에서 "Add file → Upload files"로 드래그해서 올려도 됩니다.
3. 저장소의 **Settings → Pages** 로 이동합니다.
4. **Branch**를 `main` (또는 `master`), 폴더는 `/ (root)`로 선택하고 저장합니다.
5. 1~2분 후 아래와 같은 주소로 접속하면 초대장이 공개됩니다.
   ```
   https://내깃허브아이디.github.io/저장소이름/
   ```
6. 이 주소를 카카오톡, 문자 등으로 공유하시면 됩니다.

## 참고
- 저장소는 비공개(private)로 두면 GitHub Pages도 유료 플랜이 필요한 경우가 있으니, 개인정보(연락처·주소)가 걱정되면 이름의 일부만 표기하거나 지도 링크만 남기는 방식을 추천합니다.
- 사진 용량이 크면 페이지 로딩이 느려질 수 있으니, 업로드 전 1~2MB 이하로 줄이는 것을 권장합니다.
