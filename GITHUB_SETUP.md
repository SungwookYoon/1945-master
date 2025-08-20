# GitHub 저장소 설정 가이드

## 🚀 GitHub에 1945 슈팅 게임 프로젝트 업로드하기

### 1단계: GitHub에서 새 저장소 생성

1. **GitHub.com에 로그인**
2. **우측 상단의 "+" 버튼 클릭** → "New repository" 선택
3. **저장소 정보 입력**:
   - Repository name: `1945-shooting-game`
   - Description: `1945년대 스타일의 고전 슈팅 게임 - Ionic Capacitor 하이브리드 앱`
   - **Public 선택** (중요!)
   - README, .gitignore, license는 체크하지 않음
4. **"Create repository" 클릭**

### 2단계: 로컬 저장소에 원격 저장소 추가

```bash
# GitHub에서 생성된 저장소 URL을 복사 (예: https://github.com/username/1945-shooting-game.git)
git remote add origin https://github.com/username/1945-shooting-game.git
```

### 3단계: GitHub에 코드 푸시

```bash
# 메인 브랜치를 main으로 설정 (GitHub 기본값)
git branch -M main

# GitHub에 푸시
git push -u origin main
```

### 4단계: GitHub Pages 설정 (선택사항)

1. **저장소 설정** → "Pages" 메뉴
2. **Source**: "Deploy from a branch" 선택
3. **Branch**: "main" 선택, "/ (root)" 폴더
4. **"Save" 클릭**

### 5단계: README 업데이트

GitHub에서 README.md 파일을 편집하여 프로젝트 설명을 추가할 수 있습니다.

## 📋 완성된 명령어 시퀀스

```bash
# 1. 원격 저장소 추가 (URL을 실제 GitHub 저장소 URL로 변경)
git remote add origin https://github.com/username/1945-shooting-game.git

# 2. 브랜치 이름을 main으로 변경
git branch -M main

# 3. GitHub에 푸시
git push -u origin main

# 4. 이후 변경사항이 있을 때
git add .
git commit -m "Update: 변경사항 설명"
git push
```

## 🌟 GitHub 저장소 특징

- **Public 저장소**: 누구나 코드를 볼 수 있음
- **MIT 라이선스**: 자유롭게 사용, 수정, 배포 가능
- **Issues**: 버그 리포트 및 기능 제안
- **Pull Requests**: 코드 기여
- **Releases**: 버전별 릴리즈 관리

## 🔗 저장소 링크 예시

프로젝트가 업로드되면 다음과 같은 링크로 접근할 수 있습니다:

- **저장소**: `https://github.com/username/1945-shooting-game`
- **GitHub Pages**: `https://username.github.io/1945-shooting-game`
- **Clone URL**: `https://github.com/username/1945-shooting-game.git`

## 📱 모바일 앱 빌드

GitHub Actions를 사용하여 자동 빌드도 설정할 수 있습니다:

```yaml
# .github/workflows/build.yml
name: Build and Deploy
on:
  push:
    branches: [ main ]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v2
    - name: Setup Node.js
      uses: actions/setup-node@v2
      with:
        node-version: '20'
    - name: Install dependencies
      run: npm install
    - name: Build
      run: npm run build
```

## 🎯 다음 단계

1. **GitHub 저장소 생성**
2. **원격 저장소 추가**
3. **코드 푸시**
4. **GitHub Pages 설정** (선택사항)
5. **프로젝트 공유 및 협업**

---

**즐거운 오픈소스 개발 되세요! 🚀✨** 
