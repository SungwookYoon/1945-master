# 🚀 1945 슈팅 게임 - GitHub 빠른 시작 가이드

## 📋 5분 만에 GitHub에 업로드하기

### 1️⃣ GitHub에서 새 저장소 생성

1. **GitHub.com 접속** → 로그인
2. **우측 상단 "+" 버튼** → "New repository"
3. **저장소 정보 입력**:
   ```
   Repository name: 1945-shooting-game
   Description: 1945년대 스타일의 고전 슈팅 게임 - Ionic Capacitor 하이브리드 앱
   Public ✅ (중요!)
   ```
4. **"Create repository" 클릭**

### 2️⃣ 로컬에서 GitHub 연결

```bash
# GitHub에서 생성된 저장소 URL 복사 후 아래 명령어 실행
git remote add origin https://github.com/YOUR_USERNAME/1945-shooting-game.git

# 브랜치 이름을 main으로 변경
git branch -M main

# GitHub에 푸시
git push -u origin main
```

### 3️⃣ 완료! 🎉

이제 다음 링크로 프로젝트에 접근할 수 있습니다:
- **저장소**: `https://github.com/YOUR_USERNAME/1945-shooting-game`
- **GitHub Pages**: `https://YOUR_USERNAME.github.io/1945-shooting-game`

## 🎮 게임 실행 방법

### 웹에서 실행
```bash
npm install
npx ionic serve
```

### 데모 버전
`game-demo.html` 파일을 브라우저에서 직접 열기

## 🌟 프로젝트 특징

- ✅ **크로스 플랫폼**: 웹, 모바일, 데스크톱
- ✅ **모던 기술**: Angular 20 + Ionic 7 + Capacitor 6
- ✅ **완전한 게임**: 플레이어, 몬스터, 총알, 점수 시스템
- ✅ **반응형 UI**: 모든 디바이스에서 최적화
- ✅ **오픈소스**: MIT 라이선스로 자유롭게 사용

## 🔧 커스터마이징

- **새 몬스터 추가**: `src/app/models/monster.ts`
- **새 아이템 추가**: `src/app/models/` 폴더
- **UI 변경**: `src/app/pages/` 및 `src/app/components/`
- **게임 로직**: `src/app/services/game-manager.service.ts`

## 📱 모바일 앱 빌드

```bash
# Android
npx ionic capacitor add android
npx ionic capacitor build android

# iOS
npx ionic capacitor add ios
npx ionic capacitor build ios
```

## 🤝 기여하기

1. **Fork** 프로젝트
2. **Feature branch** 생성
3. **코드 작성** 및 테스트
4. **Pull Request** 생성

## 📞 지원

- **Issues**: 버그 리포트 및 기능 제안
- **Discussions**: 질문 및 토론
- **Wiki**: 상세한 개발 가이드

---

**즐거운 게임 개발 되세요! 🎮✨** 
