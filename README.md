# voidbox-and-spacesync

CBAS 커뮤니티 발표 — **융합인재, 그리고 voidbox 이야기** (2026.05.23)

reveal.js 기반 단일 페이지 슬라이드. GitHub Pages 로 그대로 배포 가능.

---

## 로컬에서 미리 보기

```bash
cd ~/Documents/GitHub/voidbox-and-spacesync
python3 -m http.server 8080
```

브라우저로 `http://localhost:8080` 접속.

- `→` / `Space` — 다음 슬라이드
- `←` — 이전 슬라이드
- `S` — 발표자 노트 창
- `F` — 전체 화면
- `O` / `Esc` — 전체 슬라이드 오버뷰
- `B` / `.` — 화면 블랙 (Q&A 중 잠시 청중 집중용)
- `?` — 단축키 도움말

---

## GitHub 에 push + GitHub Pages 배포 (5분)

### 1) 로컬에서 git 초기화 + 커밋

```bash
cd ~/Documents/GitHub/voidbox-and-spacesync
git init
git add .
git commit -m "initial: voidbox lecture deck"
git branch -M main
```

### 2) GitHub 에 빈 리포지토리 생성

[github.com/new](https://github.com/new) 로 가서:

- Repository name: `voidbox-and-spacesync`
- Visibility: **Public** (무료 GitHub Pages 사용을 위해)
- README / .gitignore / license **체크 모두 해제** (이미 로컬에 있음)
- **Create repository** 버튼

### 3) 로컬 ↔ GitHub 연결 후 push

리포가 만들어지면 GitHub 가 다음과 같은 안내를 보여줍니다 — 그 중 "push an existing repository" 블록을 사용:

```bash
# <USERNAME> 자리에 본인 GitHub username 채우기
git remote add origin git@github.com:<USERNAME>/voidbox-and-spacesync.git
# (SSH 키 미설정 시: git remote add origin https://github.com/<USERNAME>/voidbox-and-spacesync.git)

git push -u origin main
```

### 4) GitHub Pages 활성화

리포 페이지에서:

1. **Settings** 탭
2. 왼쪽 사이드바 **Pages**
3. **Source** → `Deploy from a branch`
4. **Branch** → `main` · `/(root)` → **Save**
5. 1~2분 뒤 페이지 상단에 ✅ "Your site is live at ..." 메시지

배포 URL: `https://<USERNAME>.github.io/voidbox-and-spacesync/`

---

## gh CLI 가 설치되어 있다면 (한 줄)

```bash
cd ~/Documents/GitHub/voidbox-and-spacesync
git init && git add . && git commit -m "initial: voidbox lecture deck" && git branch -M main
gh repo create voidbox-and-spacesync --public --source=. --push
gh api -X POST repos/:owner/voidbox-and-spacesync/pages \
  -f "source[branch]=main" -f "source[path]=/"
```

---

## 발표 당일 권장 워크플로우

1. **현장 도착 직후** — 발표용 노트북에서 `https://<USERNAME>.github.io/voidbox-and-spacesync/` 열어 두기 (오프라인 백업으로 로컬 `index.html` 도 별도로 열어 둠).
2. **`F` 키로 전체 화면**, 두 번째 모니터/프로젝터 연결 시 `S` 키로 발표자 노트 창 분리.
3. **`?` 키** 로 단축키 잊었을 때 다시 확인.

---

## 파일 구조

```
voidbox-and-spacesync/
├── index.html             # reveal.js 슬라이드 본체 (28 슬라이드)
├── css/
│   └── custom.css         # 커스텀 테마 — Pretendard / 16:9 / 다크
├── assets/                # 슬라이드에 실제 삽입할 이미지가 들어갈 자리
├── .gitignore
└── README.md
```

`assets/hongdae_pptx/` 와 `assets/seminar_pdf/` 는 디테일 보강 작업용으로 PPTX·PDF에서 추출한 참고 이미지들. `.gitignore` 로 제외되어 있으므로 GitHub 에는 올라가지 않습니다. 슬라이드에 실제로 넣고 싶은 이미지가 정해지면 `assets/` 직속에 옮겨두고 `index.html` 의 `[이미지 자리]` 부분을 `<img>` 태그로 교체하세요.
