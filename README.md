# voidbox-and-spacesync

CBAS 커뮤니티 발표 — **융합인재, 그리고 voidbox 이야기** (2026.05.23)

reveal.js 기반 단일 페이지 슬라이드. GitHub Pages 로 그대로 배포 가능.

## 로컬에서 미리 보기

브라우저로 `index.html` 을 그냥 열어도 보이지만, 폰트·CDN 캐시 안정성을 위해 간단한 로컬 서버 권장.

```bash
# Python 3
python3 -m http.server 8080
# 그리고 브라우저에서
# http://localhost:8080
```

발표자 노트(Speaker Notes) 창은 발표 화면에서 `S` 키를 눌러 띄울 수 있습니다.

## GitHub Pages 배포

1. 이 폴더를 GitHub 리포지토리(`voidbox-and-spacesync`)로 푸시합니다.

   ```bash
   git init
   git add .
   git commit -m "initial: lecture deck (Part 1)"
   git branch -M main
   git remote add origin git@github.com:<USER>/voidbox-and-spacesync.git
   git push -u origin main
   ```

2. GitHub 리포지토리의 **Settings → Pages** 로 이동.
3. **Source** 를 `Deploy from a branch` 로, **Branch** 를 `main` / `/(root)` 로 설정 후 저장.
4. 1~2분 뒤 `https://<USER>.github.io/voidbox-and-spacesync/` 에서 슬라이드가 보입니다.

## 파일 구조

```
voidbox-and-spacesync/
├── index.html        # reveal.js 슬라이드 본체
├── css/
│   └── custom.css    # 커스텀 테마 (Pretendard + 다크 + 액센트)
├── assets/           # 이미지 자료 (도면, 명함, 다이어그램 등)
└── README.md
```

## 키보드 단축키 (reveal.js)

| 키 | 동작 |
|---|---|
| `→` / `Space` | 다음 슬라이드 |
| `←` | 이전 슬라이드 |
| `S` | 발표자 노트 창 |
| `F` | 전체 화면 |
| `O` / `ESC` | 전체 슬라이드 오버뷰 |
| `B` / `.` | 화면 블랙 |
| `?` | 단축키 도움말 |
