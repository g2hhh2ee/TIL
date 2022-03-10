[TypeScript 설치 및 설정](https://velog.io/@ansrjsdn/TypeScript-%EC%84%A4%EC%B9%98-%EB%B0%8F-%EC%84%A4%EC%A0%95)

# 타입스크립트 설정

```bash
npm init -y
```

타입스크립트를 실행하기 위해서는 nodejs가 설치되어 있어야 한다. 그리고 원하는 폴더로 가서 설정을 시작한다.

```bash
npm i typescript
```

그리고 typescript를 설치해준다.

```bash
npm i -D ts-node
```

그리고 ts를 node에서 실행하게 해주는 ts-node를 설치한다.

엄밀히 말하면 **ts를 node에서 실행하는게 아니라 ts-node가 ts를 js파일로 컴파일하고 그 js 파일을 node에서 실행시켜주는 것이다.**

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/b7abb16e-e421-45d5-a6da-38509c9cc75d/Untitled.png)

`tsc main.ts` - 이 시점에서 js로 변환된다.

다시 ts에서 코드를 업데이트하면 js엔 업데잍트 내용이 반영되지 않는다. 다시 터미널에서 `tsc main.ts` 를 이용해서 매번 컴파일 해줘야 업데이트 내용이 반영된다.

⇒ 굉장히 성가심!

`tsc main.ts -watch`

`-watch` 모드 이용하면 ts 파일이 저장될 때마다 자동으로 컴파일된다. 

```bash
$ tsc -h
tsc: The TypeScript Compiler - Version 4.6.2                                           
                                                                                    TS 
COMMON COMMANDS

  tsc
  Compiles the current project (tsconfig.json in the working directory.)

  tsc app.ts util.ts
  Ignoring tsconfig.json, compiles the specified files with default compiler options.  

  tsc -b
  Build a composite project in the working directory.

  tsc --init
  Creates a tsconfig.json with the recommended settings in the working directory.      

  tsc -p ./path/to/tsconfig.json
  Compiles the TypeScript project located at the specified path.

  tsc --help --all
  An expanded version of this information, showing all possible compiler options       

  tsc --noEmit
  tsc --target esnext
  Compiles the current project, with additional settings.

COMMAND LINE FLAGS

     --help, -h  Print this message.

    --watch, -w  Watch input files.

          --all  Show all compiler options.

  --version, -v  Print the compiler's version.

         --init  Initializes a TypeScript project and creates a tsconfig.json file.    

  --project, -p  Compile the project given the path to its configuration file, or to a 
                 folder with a 'tsconfig.json'.

    --build, -b  Build one or more projects and their dependencies, if out of date     

   --showConfig  Print the final configuration instead of building.

COMMON COMPILER OPTIONS

               --pretty  Enable color and formatting in TypeScript's output to make com                         piler errors easier to read
                  type:  boolean
               default:  true

           --target, -t  Set the JavaScript language version for emitted JavaScript and                          include compatible library declarations.
                one of:  es3, es5, es6/es2015, es2016, es2017, es2018, es2019, es2020, 
                         es2021, es2022, esnext
               default:  es3

           --module, -m  Specify what module code is generated.
                one of:  none, commonjs, amd, umd, system, es6/es2015, es2020, es2022, 
                         esnext, node12, nodenext
               default:  undefined

                  --lib  Specify a set of bundled library declaration files that descri                         be the target runtime environment.
           one or more:  es5, es6/es2015, es7/es2016, es2017, es2018, es2019, es2020, e                         s2021, es2022, esnext, dom, dom.iterable, webworker, webworker                         .importscripts, webworker.iterable, scripthost, es2015.core, e                         s2015.collection, es2015.generator, es2015.iterable, es2015.pr                         omise, es2015.proxy, es2015.reflect, es2015.symbol, es2015.sym                         bol.wellknown, es2016.array.include, es2017.object, es2017.sha                         redmemory, es2017.string, es2017.intl, es2017.typedarrays, es2                         018.asyncgenerator, es2018.asynciterable/esnext.asynciterable,                          es2018.intl, es2018.promise, es2018.regexp, es2019.array, es2                         019.object, es2019.string, es2019.symbol/esnext.symbol, es2020                         .bigint/esnext.bigint, es2020.promise, es2020.sharedmemory, es                         2020.string, es2020.symbol.wellknown, es2020.intl, es2021.prom                         ise/esnext.promise, es2021.string, es2021.weakref/esnext.weakr                         ef, es2021.intl, es2022.array/esnext.array, es2022.error, es20                         22.object, es2022.string/esnext.string, esnext.intl
               default:  undefined

              --allowJs  Allow JavaScript files to be a part of your program. Use the `                         checkJS` option to get errors from these files.
                  type:  boolean
               default:  false

              --checkJs  Enable error reporting in type-checked JavaScript files.      
                  type:  boolean
               default:  false

                  --jsx  Specify what JSX code is generated.
                one of:  preserve, react, react-native, react-jsx, react-jsxdev        
               default:  undefined

      --declaration, -d  Generate .d.ts files from TypeScript and JavaScript files in y                         our project.
                  type:  boolean
               default:  `false`, unless `composite` is set

       --declarationMap  Create sourcemaps for d.ts files.
                  type:  boolean
               default:  false

  --emitDeclarationOnly  Only output d.ts files and not JavaScript files.
                  type:  boolean
               default:  false

            --sourceMap  Create source map files for emitted JavaScript files.
                  type:  boolean
               default:  false

              --outFile  Specify a file that bundles all outputs into one JavaScript fi                         le. If `declaration` is true, also designates a file that bund                         les all .d.ts output.

               --outDir  Specify an output folder for all emitted files.

       --removeComments  Disable emitting comments.
                  type:  boolean
               default:  false

               --noEmit  Disable emitting files from a compilation.
                  type:  boolean
               default:  false

               --strict  Enable all strict type-checking options.
                  type:  boolean
               default:  false

                --types  Specify type package names to be included without being refere                         nced in a source file.

      --esModuleInterop  Emit additional JavaScript to ease support for importing Commo                         nJS modules. This enables `allowSyntheticDefaultImports` for t                         ype compatibility.
                  type:  boolean
               default:  false

You can learn about all of the compiler options at https://aka.ms/tsconfig-reference
```

```json
{
    "compilerOptions": {
        "strict": true,
        "module": "commonjs",
        "moduleResolution": "node",
        "lib": ["es2015","es2016","es2017","es2018","es2019","es2020"],
        "target": "ES5",
        "outDir": "./dist",
        "esModuleInterop": true
    },
    "exclude": ["node_modules"],
    "include": ["src/**/*"]
}
```

그리고 tsconfig.json 파일을 설정해준다.

### strict

모든 엄격한 타입 검사 옵션을 활성화한다. 이것을 false로 해놓으면 TypeScript를 사용하는 의미가 퇴색된다. 그러므로 true로 하는게 좋다!

### module

타입스크립트 소스코드가 컴파일되어 만들어진 ES5 자바스크립트는 코드는 웹 브라우저와 Node 양쪽에서 모두 동작해야한다. 그런데 웹 브라우저와 노드제이에스는 물리적으로 동작하는 방식이 달라서 여러 개의 파일로 분할된 자바스크립트 코드 또한 웹 브라우저와 Node 양쪽에서 각각 다르게 동작한다.

웹브라우저에서 동작: amdNode에서 동작: commonjs

### moduleResolution

module 키의 값이 commonjs면 node로 설정하고 amd이면 classic으로 설정한다.

### lib

lib에는 몇버전까지의 자바스크립트를 사용할 수 있게 할지 적는다.

### target

target키에는 트랜스파일할 대상 자바스크립트의 버전을 설정한다. 타입스크립트의 코드가 해당 버전으로 트랜스파일 된다. 대부분 ES5로 설정한다.

### outDir

outDir 키는 baseUrl 설정값을 기준으로 했을 때 하위 디렉터리의 이름이다. ./dist로 설정했음으로 dist 디렉터리에 빌드된 결과가 들어간다.

### esModuleInterop

true로 설정 해놓으면 export default가 없는 라이브러리도 * as 를 사용하지 않고 불러올 수 있다.

예를 들어 react는 export default가 없어서

```
import * as React from 'react;
```

으로 사용해야한다. 하지만 exModuleInterop을 true로 하면

```
import React from 'react;
```

로 사용할 수 있다.

### include exclude

include는 src/**/*은 src 디렉터리는 물론 src의 하위 디렉터리에 있는 모든 파일을 컴파일 대상으로 포함한다는 의미이다.exclude는 컴파일 대상에서 제외한다는 것이다.

이제 src파일을 생성하고 test.ts를 만든다.

### test.ts

```
console.log("테스트입니다.");
```

```
npx tsc
```

를 하게 되면 dist 폴더에 test.js가 생기게 된다. npx는 global로 typescript를 설치하지 않아도 npx tsc로 명령어를 실행할 수 있게 해준다.

![https://media.vlpt.us/images/ansrjsdn/post/c24fb572-ea4c-4032-b6b8-e6e8cf9f277d/image.png](https://media.vlpt.us/images/ansrjsdn/post/c24fb572-ea4c-4032-b6b8-e6e8cf9f277d/image.png)

그러면 이런식으로 폴더 구조가 된다. 타입스크립트 설정이 끝났으니 다음엔 타입스크립트의 타입들에 대해서 알아볼 것이다.
