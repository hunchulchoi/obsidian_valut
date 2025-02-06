---
created: 2024-01-24 21:26
last_modified: 2024-01-24 21:26
tags:
  - js
  - ts
---
# 환경설정
## 컴파일 설정
### tsconfig.json
- 컴파일러 설정 파일
- 프로젝트의 root 디디렉토리에 위치한다.
- #### tsconfig.json을 사용하는 경우
	- 인풋파일이 없는 tsc 명령일 경우 
		- tsconfig.json에 설정된 모든 디렉토리를 체인하여 컴파일
		- -p 옵션을 사용해 특정 디렉토리에 내에 있는 tsconfig.json혹은 유효한 json파일을 설정
- #### tsconfig.json을 사용하지 않는 경우
	- 인풋 파일일이 있는 `tsc <파일.ts>` 명령일 경우, tsconfig.json 파일은 무시
>[!note]
>tsconfig.json파일에 설정된 컴파일 옵션보다 명령어가 우선

### tsconfig.json 생성
- `tsc --init`
- 명령어를 통해 생성된 tsconfig.json 파일에는 `compilerOptions`만 추가되어 있다
```json
{
  "compilerOptions": {
  
    /* 기본 옵션
     * ------------------------------------------------------------------------------------------------------------------------------------------------ */
    // "incremental": true,                   /* 증분 컴파일 활성화 */ 
    "target": "es5",                          /* ECMAScript 목표 버전 설정: 'ES3'(기본), 'ES5', 'ES2015', 'ES2016', 'ES2017','ES2018', 'ES2019', 'ES2020', or 'ESNEXT'. */
    "module": "esnext",                       /* 생성될 모듈 코드 설정: 'none', 'commonjs', 'amd', 'system', 'umd', 'es2015', 'es2020', or 'ESNext'. */
    "lib": ["dom", "dom.iterable", "esnext"], /* 컴파일 과정에 사용될 라이브러리 파일 설정 */
    "allowJs": true,                          /* JavaScript 파일 컴파일 허용 */
    // "checkJs": true,                       /* .js 파일 오류 리포트 설정 */
    "jsx": "react",                           /* 생성될 JSX 코드 설정: 'preserve', 'react-native', or 'react'. */
    // "declaration": true,                   /* '.d.ts' 파일 생성 설정 */
    // "declarationMap": true,                /* 해당하는 각 '.d.ts'파일에 대한 소스 맵 생성 */
    // "sourceMap": true,                     /* 소스맵 '.map' 파일 생성 설정 */
    // "outFile": "./",                       /* 복수 파일을 묶어 하나의 파일로 출력 설정 */
    // "outDir": "./dist",                    /* 출력될 디렉토리 설정 */
    // "rootDir": "./",                       /* 입력 파일들의 루트 디렉토리 설정. --outDir 옵션을 사용해 출력 디렉토리 설정이 가능 */
    // "composite": true,                     /* 프로젝트 컴파일 활성화 */
    // "tsBuildInfoFile": "./",               /* 증분 컴파일 정보를 저장할 파일 지정 */
    // "removeComments": true,                /* 출력 시, 주석 제거 설정 */
    "noEmit": true,                           /* 출력 방출(emit) 유무 설정 */
    // "importHelpers": true,                 /* 'tslib'로부터 헬퍼를 호출할 지 설정 */
    // "downlevelIteration": true,            /* 'ES5' 혹은 'ES3' 타겟 설정 시 Iterables 'for-of', 'spread', 'destructuring' 완벽 지원 설정 */
    "isolatedModules": true,                  /* 각 파일을 별도 모듈로 변환 ('ts.transpileModule'과 유사) */

    /* 엄격한 유형 검사 옵션
     * ------------------------------------------------------------------------------------------------------------------------------------------------ */
    "strict": true,                           /* 모든 엄격한 유형 검사 옵션 활성화 */
    // "noImplicitAny": true,                 /* 명시적이지 않은 'any' 유형으로 표현식 및 선언 사용 시 오류 발생 */
    // "strictNullChecks": true,              /* 엄격한 null 검사 사용 */
    // "strictFunctionTypes": true,           /* 엄격한 함수 유형 검사 사용 */
    // "strictBindCallApply": true,           /* 엄격한 'bind', 'call', 'apply' 함수 메서드 사용 */
    // "strictPropertyInitialization": true,  /* 클래스에서 속성 초기화 엄격 검사 사용 */
    // "noImplicitThis": true,                /* 명시적이지 않은 'any'유형으로 'this' 표현식 사용 시 오류 발생 */
    // "alwaysStrict": true,                  /* 엄격모드에서 구문 분석 후, 각 소스 파일에 "use strict" 코드를 출력 */

    /* 추가 검사 옵션
     * ------------------------------------------------------------------------------------------------------------------------------------------------ */
    // "noUnusedLocals": true,                /* 사용되지 않은 로컬이 있을 경우, 오류로 보고 */
    // "noUnusedParameters": true,            /* 사용되지 않은 매개변수가 있을 경우, 오류로 보고 */
    // "noImplicitReturns": true,             /* 함수가 값을 반환하지 않을 경우, 오류로 보고 */
    "noFallthroughCasesInSwitch": true,       /* switch 문 오류 유형에 대한 오류 보고 */
    // "noUncheckedIndexedAccess": true,      /* 인덱스 시그니처 결과에 'undefined' 포함 */

    /* 모듈 분석 옵션
     * ------------------------------------------------------------------------------------------------------------------------------------------------ */
    "moduleResolution": "node",               /* 모듈 분석 방법 설정: 'node' (Node.js) 또는 'classic' (TypeScript pre-1.6). */
    // "baseUrl": "./",                       /* 절대 경로 모듈이 아닌, 모듈이 기본적으로 위치한 디렉토리 설정 (예: './modules-name') */
    // "paths": {},                           /* 'baseUrl'을 기준으로 상대 위치로 가져오기를 다시 매핑하는 항목 설정 */
    // "rootDirs": [],                        /* 런타임 시 프로젝트 구조를 나타내는 로트 디렉토리 목록 */
    // "typeRoots": [],                       /* 유형 정의를 포함할 디렉토리 목록 */
    // "types": [],                           /* 컴파일 시 포함될 유형 선언 파일 입력 */
    "allowSyntheticDefaultImports": true,     /* 기본 출력(default export)이 없는 모듈로부터 기본 호출을 허용 (이 코드는 단지 유형 검사만 수행) */
    "esModuleInterop": true                   /* 모든 가져오기에 대한 네임스페이스 객체 생성을 통해 CommonJS와 ES 모듈 간의 상호 운용성을 제공. 'allowSyntheticDefaultImports' 암시 */
    // "preserveSymlinks": true,              /* symlinks 실제 경로로 결정하지 않음 */
    // "allowUmdGlobalAccess": true,          /* 모듈에서 UMD 글로벌에 접근 허용 */

    /* 소스맵 옵션
     * ------------------------------------------------------------------------------------------------------------------------------------------------ */
    // "sourceRoot": "./",                    /* 디버거(debugger)가 소스 위치 대신 TypeScript 파일을 찾을 위치 설정 */
    // "mapRoot": "./",                       /* 디버거가 생성된 위치 대신 맵 파일을 찾을 위치 설정 */
    // "inlineSourceMap": true,               /* 하나의 인라인 소스맵을 내보내도록 설정 */
    // "inlineSources": true,                 /* 하나의 파일 안에 소스와 소스 코드를 함께 내보내도록 설정. '--inlineSourceMap' 또는 '--sourceMap' 설정이 필요 */

    /* 실험적인 기능 옵션
     * ------------------------------------------------------------------------------------------------------------------------------------------------ */
    // "experimentalDecorators": true,        /* ES7 데코레이터(decorators) 실험 기능 지원 설정 */
    // "emitDecoratorMetadata": true,         /* 데코레이터를 위한 유형 메타데이터 방출 실험 기능 지원 설정 */
    
    /* 고급 옵션
     * ------------------------------------------------------------------------------------------------------------------------------------------------ */
    "skipLibCheck": true,                     /* 선언 파일 유형 검사 스킵 */
    "forceConsistentCasingInFileNames": true  /* 동일한 파일에 대한 일관되지 않은 케이스 참조를 허용하지 않음 */
    
  }
}
```
### include/exclude 설정
- 컴파일러에 포함할 디렉토리/파일 경로를 설정하거나 제외한다.
- 제외될 각 항목에는 grob패턴을 사용하여 표기할 수 있다.
	- `*` 0 이상의 모든 문자와 일치 (디렉토리 분리 기호 제외)
	- `?` 1개 문자와 일치 (디렉토리 분리 기호 제외)
	- `**/` 모든 하위 디렉토리까지 포함
```json
{
	// 컴파일 포함
	"include": [
		"src/**/*.tsx?"
	],
	
	// 컴파일 제외
	"exclude": [
		"node_modules",
		"build",
		"**/*.(spec|test).ts"
	],
	
	// 컴파일 옵션
	"compilerOptions": { ... }
}
```
# type

#### 원시타입
##### string
##### number
##### boolean
#### 배열
- `number[]`
- `Array<number>`
- `T<U>`
- 복합적으로 어떠한 데이터 타입도 설정할수 있는 배열 선언
	- `let member:any[]`
- 특정 데이터 타입 배열
	- `let select:(number|string)[] = [0, 'abc']`
#### tuple
- *터플로 읽어라 ㅋㅋ*
- 배열타입을 보다 특수한 형태로 사용
- tuple에 명시적으로 지정된 형식에 따라 아이템 순서를 설정해야 된다.
	- index별로 type을 선언할 때
- let b:[string, number]
#### any
- 특정 값으로 인하여 타입 검사 오류가 발생하는 것을 원하지 않을때 사용할수 있다.
- 변수 선언과 초기화 과정에서 값을 할당하지 않으면 암시적(Implicit)으로 any타입이 지정된다.
- 컴파일러 플래그 `noImplicitAny`를 사용하면 암묵적으로 any로 간주하는 모든 경우에 오류를 발생
```js
let product_id; //any type 지정

product_id = 193840;
product_id = 'asdfsd'
```
#### enum
- 열거형 데이터 타입
	- 멤버라 불리는 명명된 값의 집합을 이루는 자료형
	- `type Job = 'police' | 'teacher' | 'worker'`
### 선언
##### 변수 
- 변수:타입
- const 변수:string = "hello"
##### 함수
- `function 이름(변수:타입) : 반환타입{}`
- `const 함수명 = (변수명:타입) :반환타입 => ....`
- this
	- `function 이름(this:타입[, 변수:타입])`
- over load
```ts
interface User {
  name: string;
  age: number;
}

function join(name: string, age: number): User;
function join(name: string, age: string): string;
function join(name: string, age: number | string): User | string {
  if (typeof age === 'number') {
    return {name, age};
  } else {
    return '나이는 숫자로 입력해주세요';
  }
}

```
# interface
- 선언
```js
interface User{
	name: string;
	age: number;
	gender?: 'F' | 'M'; // optional property
	readonly birthYear: number; // readonly property
	[grage:number]: string; // index signature
	 
}

let user:User = {
	name: 최훈철,
	age: 47,
	birthYear: 1978,
	1: 'A',
	3: 'A'	
}
```
- 함수 선언
```ts
interface Add{
	(num1: number, num2: number): number;
}

const add: Add = (x, y)=> x+y;

```
- class
```ts
interface Car {
  color: string;
  company: string;
  name: string;
  displacement: number;
  start(): void;
}

const bmw530d: Car = {
  color: 'red',
  company: 'bmw',
  name: '520d',
  displacement: 2000,
  start() {
    console.log('start....');
  },
}

// implements
class Benz implements Car {

  readonly company: string = 'Benz';
  color: string;
  name: string;
  displacement: number;

  start() {
    console.log(`${this.name} started....`);
  }

  constructor(color: string, name: string, displacement: number) {
    this.color = color;
    this.name = name;
    this.displacement = displacement;
  }
};

const benzE300 = new Benz('white', 'E300', 1599);

// extends
interface ElectricCar extends Car {
  weight: number;
  battery: string;
}

const kona: ElectricCar = {
  battery: '500',
  color: 'blue',
  company: 'Hyundai',
  displacement: 0,
  name: 'Kona(OS)',
  weight: 2000,
  start() {
    console.log('에에에엘');
  },
}
```
# class
### 접근제한자
- public
	- default
- private
	- 해당 class 내부에서만 사용 가능
	- 상속 x
	- `#이름` 으로 선언가능
- protected
	- 자식 class 에서 접근 가능
	- class 인스턴스로는 접근 불가 x  e.g.) `z4.name`
### readonly
- `readonly 이름:타입 = 값;`
- readonly property는 변경 할수 없음x
- constructor에서만 설정 가능
### static
- `static 이름:타입 = 값;`
- 클래스명.이름 으로 접근
### 추상 클래스
- `abstract class 클래스명{}`
- `abstract 함수명(): 반환타입`
- 추상 class는 new로 생성할 수 없고 extends 를 통해 사용
- extends에서 추상 함수는 반드시 구현해야함
# union type
- 여러 타입 중에 하나가 올 수 있다는 의미
- `|`로 타입을 구분
- `string | number | boolean`
```ts
interface CelPhone {
  name: 'mobile';
  call(): void;
}

interface Ring {
  name: 'ring';
  show(): void;
  price: number;
}

const getGift = (gift: CelPhone | Ring): void => {
  if (gift.name === 'mobile') {
    gift.call();
  } else {
    gift.show();
  }
};

```
### 공통 필드를 갖는 union
- union 타입의 값이 있으면 유니언에 있는 모든 타입에 공통인 멤버들에만 접근 가능
- 특정 타입에 접근 하기 위해서는 if나 switch문으로 type 검사가 필요하다.
# 교차 타입 Intersection Types
- 여러 타입을 하나로 결합한다.
- 기존 타입을 합쳐 필요한 기능을 모두 가진 단일 타입을 얻을 수 있다.
```ts
interface Car {
  name: string;
  start(): void;
}

interface Toy {
  name: string;
  price: number;
}

const toyCar: Car & Toy = {
  name: '타요',
  start: () => console.log('삐요'),
  price: 3500,
};
```
# Generic
- 함수 `function 함수명<T>(파라미터: T)`
- `const 함수명 = <T>(파라미터: T): 반환타입 => ...`
- interface `interface 인터페이스명<T>`
- `<T extends {name: string}>
# Utility type
### keyof
- 
### Partial
- property를 모두 optional로 변경해줌
- `const user: Partial<User> = ...`
### Required
- 모든 property가 필수로 바뀐다.
- `Required<T>`
### Readonly
- `Readonly<T>`
### Record
- `Record<K, T>`
- 키가 K타입이고 값이 T타입인 객체타입
- index signature와 비슷하지만 key로 문자열 리터럴을 지정할 수 있음
### Pick
- `Pick<T, K>`
- T타입 객체에서 K프로퍼티만 고름
``` const admin:Pick<User, 'id' | 'name'> = ...```
### Omit
- `Omit<T, K>`
- T타입 객체에서 K프로퍼티만 제외
### Exclude
- `Exclude<T1, T2>`
- T1타입에서 T2타입과 겹치는 프로퍼티를 제외
```ts
type T1 = string | number | boolean;
type T2 = Exclude<T1, string | boolean> // -> number
```
### Nonullable
- `Nonnullable<Type>`
- null과 undefined를 제외