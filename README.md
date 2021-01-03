## 코로나 세계 현황판 만들기

## 자바스크립트 프로젝트에 타입스크립트 적용하기.

0. 자바스크립트 파일에 JSDoc으로 타입 시스템 입히기
    - [x] //@ts-check
    - [x] 타입스크립트 설정 파일 생성 및 기본 값 추가
1. 타입스크립에 기본환경 구성하기
    - [x] npm 초기화
    - [x] 타입스크립트 라이브러리 설치
    - [x] 타입스크립트 설정 파일 생성 및 기본 값 추가
    - [x] 자바스크립트 파일을 타입스크립트 파일로 변환하기
    - [x] `tsc` 명령어로 타입스크립트 컴파일 하기
3. typscript 명시적인 `any` 선언 하기
    - `tsconfig.json` 파일에 `noImplicitAby` 추가
    - 타입 구체화 작업 진행
4. 외부 라이브러리 모듈화 



## 개발환경 셋팅하기

1. 패키지 설치 하기
```bash
npm i -D typescript @babel/core @babel/preset-env @babel/preset-typescript @typescript-eslint/eslint-plugin @typescript-eslint/parser eslint prettier eslint-plugin-prettier
```
2. 설치 후 개발환경 셋팅

### ESLint
```js
// .eslintrc.js
module.exports = {
  root: true,
  env: {
    browser: true,
    node: true,
  },
  extends: [
    'eslint:recommended',
    'plugin:@typescript-eslint/eslint-recommended',
    'plugin:@typescript-eslint/recommended',
  ],
  plugins: ['prettier', '@typescript-eslint'],
  rules: {
    'prettier/prettier': [
      'error',
      {
        singleQuote: true,
        semi: true,
        useTabs: false,
        tabWidth: 2,
        printWidth: 80,
        bracketSpacing: true,
        arrowParens: 'avoid',
      },
    ],
  },
  parserOptions: {
    parser: '@typescript-eslint/parser',
  },
};
```
3. vscode 셋팅
setting.json // onsave 꺼주세요 충돌 나지 않도록
```json
// ... <-- 기존 내용을 꼭 유지한 상태에서 아래 내용을 추가하고 이 주석은 제거할 것
  "editor.codeActionsOnSave": {
      "source.fixAll.eslint": true
  },
  "eslint.alwaysShowStatus": true,
  "eslint.workingDirectories": [
      {"mode": "auto"}
  ],
  "eslint.validate": [
      "javascript",
      "typescript"
  ],
```
### Babel
- 최신의 자바스크립트를 모든 브라우져가 호환 할 수 없기 때문에 브라우져가 호환 할 수 있는 자바스크립트 문법으로 변환해주는 도구
- 플러그인 옵션 < 프리셋 (플러그인의 집합)

### prettier
- 코드 포멧에 사용된다.
- eslint plugin prettier를 설치했기 때문에 eslint에서 prittier설정을 할 수 있다.
- 같이 사용하면 팀 컨벤션을 맞추는게 더 좋다고 합니다.

## API 자료

- [존스 홉킨스 코로나 현황](https://www.arcgis.com/apps/opsdashboard/index.html#/bda7594740fd40299423467b48e9ecf6)
- [Postman API](https://documenter.getpostman.com/view/10808728/SzS8rjbc?version=latest#27454960-ea1c-4b91-a0b6-0468bb4e6712)
- [Type Vue without Typescript](https://blog.usejournal.com/type-vue-without-typescript-b2b49210f0b)