# 1945 슈팅 게임 - Ionic Capacitor 하이브리드 앱

1945년대 스타일의 고전 슈팅 게임을 Ionic과 Capacitor를 사용하여 구현한 하이브리드 웹앱입니다.

## 🎮 게임 특징

- **다양한 몬스터 타입**: 직선 이동, 회전 이동, 보스 몬스터
- **파워업 시스템**: 체력 회복, 폭탄 획득
- **실시간 점수 시스템**: 몬스터 처치 시 점수 획득
- **반응형 컨트롤**: 키보드 입력 지원
- **아름다운 UI**: 현대적인 디자인과 애니메이션

## 🚀 기술 스택

- **Frontend**: Ionic 7 + Angular 20
- **Mobile**: Capacitor 6
- **Game Engine**: Canvas API + TypeScript
- **Styling**: SCSS + Ionic Components

## 📱 플랫폼 지원

- ✅ 웹 브라우저
- ✅ Android (Capacitor)
- ✅ iOS (Capacitor)
- ✅ PWA (Progressive Web App)

## 🎯 게임 플레이

### 조작법
- **방향키**: 플레이어 이동
- **스페이스바**: 총알 발사
- **B키**: 폭탄 사용

### 게임 목표
- 몬스터들을 처치하여 점수 획득
- 생존하며 최대한 오래 플레이
- 보스 몬스터 처치 시 보너스 점수

## 🛠️ 설치 및 실행

### 필수 요구사항
- Node.js 20.19+ 또는 22.12+
- npm 6.11+ 또는 7.5.6+ 또는 8.0+
- Ionic CLI

### 설치
```bash
# 의존성 설치
npm install

# Ionic CLI 설치 (전역)
npm install -g @ionic/cli
```

### 개발 서버 실행
```bash
# 개발 서버 시작
ionic serve

# 브라우저에서 http://localhost:8100 접속
```

### 빌드
```bash
# 웹 빌드
ionic build

# Android 빌드
ionic capacitor add android
ionic capacitor build android

# iOS 빌드
ionic capacitor add ios
ionic capacitor build ios
```

## 📁 프로젝트 구조

```
src/
├── app/
│   ├── components/
│   │   └── game-canvas.component.ts    # 게임 캔버스 컴포넌트
│   ├── models/
│   │   ├── game-object.ts              # 게임 오브젝트 기본 클래스
│   │   ├── player.ts                   # 플레이어 클래스
│   │   ├── bullet.ts                   # 총알 클래스들
│   │   └── monster.ts                  # 몬스터 클래스들
│   ├── pages/
│   │   ├── home.page.ts                # 홈 페이지
│   │   └── game.page.ts                # 게임 페이지
│   ├── services/
│   │   └── game-manager.service.ts     # 게임 매니저 서비스
│   └── app.component.ts                # 메인 앱 컴포넌트
├── assets/                              # 이미지, 사운드 등 리소스
└── theme/                               # 테마 및 스타일
```

## 🎨 게임 아키텍처

### 객체지향 설계
- **GameObject**: 모든 게임 오브젝트의 기본 클래스
- **Player**: 플레이어 비행기 (이동, 총알 발사, 폭탄)
- **Monster**: 다양한 몬스터 타입 (Linear, Rotate, Boss)
- **Bullet**: 플레이어 및 몬스터 총알

### 게임 루프
1. **Input**: 키보드 입력 처리
2. **Update**: 게임 오브젝트 상태 업데이트
3. **Collision**: 충돌 감지 및 처리
4. **Render**: Canvas에 게임 화면 렌더링

### 이벤트 시스템
- CustomEvent를 사용한 게임 오브젝트 간 통신
- 게임 오버, 몬스터 처치, 아이템 드롭 등

## 🔧 커스터마이징

### 새로운 몬스터 추가
```typescript
export class NewMonster extends Monster {
  updateMovement(deltaTime: number): void {
    // 커스텀 이동 패턴 구현
  }
  
  render(ctx: CanvasRenderingContext2D): void {
    // 커스텀 렌더링 구현
  }
}
```

### 새로운 아이템 추가
```typescript
export class NewItem extends BaseGameObject {
  // 아이템 로직 구현
}
```

## 📊 성능 최적화

- **Object Pooling**: 게임 오브젝트 재사용
- **Spatial Partitioning**: 충돌 감지 최적화
- **RequestAnimationFrame**: 부드러운 애니메이션
- **Canvas 최적화**: 불필요한 렌더링 방지

## 🐛 문제 해결

### 빌드 오류
- Node.js 버전 확인 (20.19+ 또는 22.12+)
- npm 캐시 클리어: `npm cache clean --force`
- node_modules 삭제 후 재설치

### 게임 성능 문제
- 브라우저 개발자 도구에서 FPS 확인
- 게임 오브젝트 수 제한
- Canvas 크기 최적화

## 📝 라이선스

이 프로젝트는 MIT 라이선스 하에 배포됩니다.

## 🤝 기여하기

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📞 문의

프로젝트에 대한 질문이나 제안사항이 있으시면 이슈를 생성해주세요.

---

**즐거운 게임 되세요! 🎮✨** 
