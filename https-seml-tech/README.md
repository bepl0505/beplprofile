# 김창준 프로필 사이트

정적 HTML 프로필 페이지입니다. GitHub Pages로 배포할 수 있습니다.

## 배포 전 확인

`index.html`이 참조하는 이미지가 `source/심호령 Introduction_files/` 안에 있어야 합니다.

- `profile.jpg` — 프로필 사진
- `avatar.jpg` — 인스타그램
- `disprof.jpg` — 디스코드
- `f5296c62f34cf461fdb0410a0e7c39df662f83e13be050e18b6eb85eb5388bdc.png` — OW 기본 아바타(선택)
- `Rank_GoldTier-16d20c7128.png` — 랭크 기본 아이콘(선택)

이미지가 없으면 GitHub에 올려도 사진만 깨집니다. 로컬 PC에 있다면 같은 폴더에 넣은 뒤 커밋하세요.

## GitHub Pages 배포 (권장: Actions)

### 1. GitHub에 저장소 만들기

1. [github.com/new](https://github.com/new) 에서 새 저장소 생성 (예: `profile` 또는 `kimchangjun`)
2. Public 권장 (무료 Pages)

### 2. 파일 업로드

**방법 A — GitHub 웹**

1. 저장소 → **Add file** → **Upload files**
2. 이 폴더 전체(`index.html`, `source/`, `.github/`, `.nojekyll` 등) 업로드
3. 기본 브랜치 이름이 `main`인지 확인

**방법 B — Git (PC에 Git 설치된 경우)**

```bash
cd "프로젝트 폴더 경로"
git init
git add .
git commit -m "Add profile site for GitHub Pages"
git branch -M main
git remote add origin https://github.com/사용자이름/저장소이름.git
git push -u origin main
```

### 3. Pages 켜기

1. 저장소 → **Settings** → **Pages**
2. **Build and deployment** → **Source**: `GitHub Actions`
3. `main`에 push 하면 `.github/workflows/pages.yml` 이 자동 배포
4. Actions 탭에서 **Deploy to GitHub Pages** 워크플로가 초록색이면 완료

### 4. 접속 URL

| 저장소 이름 | 사이트 주소 |
|-------------|-------------|
| `사용자이름.github.io` (특수 저장소) | `https://사용자이름.github.io/` |
| 그 외 이름 (예: `profile`) | `https://사용자이름.github.io/profile/` |

첫 배포 후 1~3분 정도 걸릴 수 있습니다.

## Pages 없이 브랜치만 쓰는 방법 (간단)

Settings → Pages → Source: **Deploy from a branch** → Branch: `main` → Folder: `/ (root)` → Save.

이 경우 Actions 워크플로는 없어도 됩니다. 둘 중 하나만 사용하면 됩니다.

## 배포 후 동작

- **Overwatch / Discord 실시간 데이터**: `https://` 로 열어야 합니다. `file://` 로 열면 API가 막힐 수 있습니다.
- **Discord (Lanyard)**: [Lanyard Discord](https://discord.gg/lanyard) 참가 후 본인 계정에 Lanyard 봇 연동이 필요할 수 있습니다.
- **커스텀 도메인**: Pages 설정에서 Domain 추가 가능

## 로컬 미리보기

```bash
npx --yes serve .
```

브라우저에서 표시된 주소(예: `http://localhost:3000`)로 접속하세요.
