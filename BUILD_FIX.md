# 🚨 빌드 오류 수정 가이드

## 문제 분석

GitLab CI/CD 빌드에서 다음과 같은 오류가 발생했습니다:

### **주요 오류들**

1. **TypeScript 버전 불일치**
   - Angular 20은 TypeScript 5.8+ 필요
   - 현재 설치된 버전: 5.4.5

2. **tsconfig.app.json 파일 누락**
   - TypeScript 설정 파일이 없음

3. **polyfills.ts 파일 누락**
   - Angular polyfills 파일이 없음

4. **의존성 버전 충돌**
   - package.json과 package-lock.json 불일치

## 🔧 수정 방법

### **1단계: 필수 파일 생성**

#### **tsconfig.app.json 생성**
```json
{
  "extends": "./tsconfig.json",
  "compilerOptions": {
    "outDir": "./out-tsc/app",
    "types": []
  },
  "files": [
    "src/main.ts"
  ],
  "include": [
    "src/**/*.d.ts"
  ]
}
```

#### **src/polyfills.ts 생성**
```typescript
/**
 * Zone JS is required by default for Angular itself.
 */
import 'zone.js';  // Included with Angular CLI.
```

#### **src/zone-flags.ts 생성**
```typescript
/**
 * This file can be used to configure global behavior of Marble.js before the
 * application starts.
 *
 * Just import this file in your `main.ts` file.
 *
 * Example:
 * ```typescript
 * import './zone-flags';
 * ```
 */
```

### **2단계: package.json 수정**

#### **TypeScript 버전 업데이트**
```json
{
  "devDependencies": {
    "typescript": "~5.8.0"
  }
}
```

#### **zone.js 버전 업데이트**
```json
{
  "dependencies": {
    "zone.js": "~0.15.0"
  }
}
```

### **3단계: 의존성 재설치**

```bash
# package-lock.json 삭제
rm package-lock.json

# node_modules 삭제
rm -rf node_modules

# 의존성 재설치
npm install
```

### **4단계: 빌드 테스트**

```bash
# 웹 빌드 테스트
npm run build

# Ionic 빌드 테스트
ionic build
```

## 🚀 GitLab CI/CD 수정

### **.gitlab-ci.yml 예시**
```yaml
stages:
  - build
  - test

build:
  stage: build
  image: node:20.19
  script:
    - npm install
    - npm run build
  artifacts:
    paths:
      - www/
    expire_in: 1 week

test:
  stage: test
  image: node:20.19
  script:
    - npm install
    - npm test
```

## 📋 수정된 파일 목록

✅ `tsconfig.app.json` - TypeScript 앱 설정
✅ `src/polyfills.ts` - Angular polyfills
✅ `src/zone-flags.ts` - Zone.js 설정
✅ `package.json` - 의존성 버전 수정

## 🔍 추가 문제 해결

### **Node.js 버전 문제**
- **필요**: Node.js 20.19+ 또는 22.12+
- **현재**: Node.js 20.11.0
- **해결**: Node.js 업데이트 또는 Docker 사용

### **의존성 충돌**
```bash
# 강제 설치
npm install --force

# 또는 yarn 사용
yarn install
```

### **Angular CLI 문제**
```bash
# Angular CLI 재설치
npm uninstall -g @angular/cli
npm install -g @angular/cli@latest
```

## 🎯 최종 확인

수정 후 다음 명령어로 빌드가 성공하는지 확인:

```bash
npm run build
ionic build
```

## 📞 지원

문제가 지속되면:
1. **GitLab Issues** 생성
2. **빌드 로그** 첨부
3. **Node.js 버전** 확인
4. **의존성 충돌** 분석

---

**빌드 성공을 기원합니다! 🚀✨** 
