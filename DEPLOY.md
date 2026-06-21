# GitHub Pages 배포 가이드 (교수님용)

학생들에게 URL 하나 공유하면 끝나는 가장 간단한 방법.
GitHub Actions가 마크다운 푸시 → 자동 빌드 → Pages 배포까지 다 해줍니다.

> **Repo = `interns/` 폴더 통째로**. 매년 `2026_summer/`, `2027_summer/`...
> 같은 식으로 누적되는 인턴 아카이브입니다.

---

## :material-numeric-1-circle: GitHub repo 만들기 (5분)

브라우저에서:

1. <https://github.com/new> 접속
2. **Repository name**: `hydroai-interns`
3. **Public** 선택 (Pages 무료 사용 위해)
4. **Add a README** 체크는 **하지 마세요** (이미 있음)
5. "Create repository" 클릭
6. 다음 화면에서 표시되는 repo URL 복사 (예: `git@github.com:yourname/hydroai-interns.git`)

---

## :material-numeric-2-circle: 로컬에서 git 초기화 + 푸시 (5분)

터미널에서:

```bash
cd "/Users/hyunglokkim/Insync/hkim@geol.sc.edu/Google_Drive/Lab/interns"

# git 저장소로 만들기
git init -b main

# 처음 한 번만 — git 사용자 정보 (이미 설정돼 있으면 생략)
git config user.name  "Hyunglok Kim"
git config user.email "hyunglokkim@gmail.com"

# 무엇이 올라갈지 미리 확인 (.gitignore가 raw 데이터 폴더는 제외해 줌)
git status

# 모든 파일 스테이징
git add .

# 첫 커밋
git commit -m "Initial intern archive site"

# 위에서 복사한 GitHub repo 주소로 연결
git remote add origin git@github.com:yourname/hydroai-interns.git
# (SSH 키 안 만들어뒀으면 HTTPS 주소 써도 됨: https://github.com/yourname/hydroai-interns.git)

# 푸시
git push -u origin main
```

!!! tip ".gitignore가 자동으로 제외하는 것"
    - `2026_summer/brown_ocean_effect/` — 파이프라인 노트 (로컬에만)
    - `2026_summer/soil_moisture_data_intercomparison/` — (로컬에만)
    - `2026_summer/hydroai.png` — 로고 원본 (사이트에는 `docs/assets/hydroai.png`로 복사돼 있음)
    - `site/` — mkdocs 빌드 결과물
    - `.DS_Store`, `__pycache__/` 등

---

## :material-numeric-3-circle: GitHub Pages 활성화 (1분)

브라우저에서:

1. GitHub에서 방금 만든 repo 페이지 열기
2. 상단 **Settings** 탭 클릭
3. 왼쪽 메뉴에서 **Pages** 클릭
4. **Source** 항목에서 **GitHub Actions** 선택 (Branch가 아님 — 드롭다운 잘 보세요)
5. 저장 (자동 저장됨)

---

## :material-numeric-4-circle: 자동 빌드 확인 (2분)

1. repo 페이지 상단 **Actions** 탭 클릭
2. "Deploy site to GitHub Pages" 워크플로우가 실행 중인지 확인
3. 1~2분 후 초록 체크 ✅가 뜨면 성공
4. 다시 **Settings → Pages**로 가면 상단에
   `Your site is live at https://yourname.github.io/hydroai-interns/`
   이런 URL이 표시됨

**이 URL을 학생들에게 공유하면 끝.**

학생들이 처음 보게 될 페이지는 인턴 아카이브 랜딩이고, 거기서
**"Summer 2026"** 카드를 클릭하면 박창익·이도원용 시작 페이지로 들어갑니다.
바로 시작 페이지로 보내고 싶으면 직접 링크:
`https://yourname.github.io/hydroai-interns/2026-summer/`

---

## :material-numeric-5-circle: 이후 내용 수정하기

방법 두 가지:

### 옵션 A — 로컬에서 마크다운 편집 후 푸시

```bash
cd "/Users/hyunglokkim/Insync/hkim@geol.sc.edu/Google_Drive/Lab/interns"

# docs/2026-summer/index.md 등을 수정한 후
git add docs/2026-summer/index.md
git commit -m "Update Wednesday meeting agenda"
git push
```

푸시 후 1~2분 안에 사이트 자동 업데이트.

### 옵션 B — GitHub 웹에서 직접 편집

GitHub repo 페이지에서 → `docs/2026-summer/index.md` 파일 클릭 → 연필
아이콘 → 편집 → "Commit changes" → 자동 빌드 + 배포.

→ 노트북 없이도 어디서든 수정 가능.

---

## :material-folder-plus: 새 인턴 코호트 추가하기 (예: 2027 여름)

1. `docs/2027-summer/index.md` 만들기 (`docs/2026-summer/index.md` 복사해서 시작)
2. `mkdocs.yml`의 `nav`에 한 줄 추가:
   ```yaml
   nav:
     - Home: index.md
     - Summer 2026: 2026-summer/index.md
     - Summer 2027: 2027-summer/index.md   # ← 추가
   ```
3. 최상위 랜딩 `docs/index.md`의 Cohorts 그리드에 카드 한 장 추가
4. push — 끝

---

## :material-help-circle-outline: 트러블슈팅

| 증상 | 원인 / 해결 |
|------|------------|
| Actions 탭에서 빨간 X | 워크플로우 클릭 → 로그 확인. 대부분 strict 모드의 markdown 링크 오류. 로컬에서 `mkdocs build --strict`로 재현 가능 |
| Pages URL이 404 | Source가 "GitHub Actions"로 돼 있는지 다시 확인 (Branch로 돼 있으면 동작 안 함) |
| 사이트 업데이트 안 됨 | Actions 탭에서 최신 워크플로우 성공했는지 확인 + 브라우저 강력 새로고침 (Cmd+Shift+R) |
| 학생이 접근 못 함 | repo가 Public인지 확인 (Settings 맨 아래 Danger Zone에서) |
| Insync가 `.git/` 동기화로 느려짐 | Insync 설정 → 선택적 동기화에서 `.git/` 폴더 제외 |

---

## :material-shield-account: 보안 메모

- 학생 이름·연구 주제 정도는 Public이어도 큰 문제 없음
- **올리면 안 되는 것**: 미발표 데이터, API 키, 비밀번호, 학생 개인정보 (학번/이메일/연락처)
- `.gitignore`에 `site/`, raw 데이터 폴더, `.DS_Store` 등 이미 등록됨
- 나중에 민감 자료 다룰 단계가 되면 → Google Drive 링크로 빼고 사이트엔
  요약·캡션만 두기

---

## :material-rocket: 학생에게 보낼 안내 메시지 (템플릿)

> 박창익·이도원 두 분께,
>
> G-SURF 2026 시작 페이지를 만들었습니다. 수요일 오후 첫 미팅 전까지
> 무엇을 준비하면 되는지 정리해 두었으니 한번 읽어봐 주세요.
>
> https://yourname.github.io/hydroai-interns/2026-summer/
>
> 궁금한 점은 Slack으로 편하게 물어봐 주세요.
>
> — Hyunglok
