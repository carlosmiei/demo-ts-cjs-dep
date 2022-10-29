# Typescript: error using CJS dependency

As you can see, when using a CommonJS dependency tsc will generate an invalid cjs file, which breaks the entire code.

File with the error: **dist/dependency.cjs**

Error: esm style export inside cjs file: **export {};**


#### How to reproduce:
- npm run build
- node/index.js

Complete log after running: 

```
/Users/cjg/Git/ts-cjs/dist/dependency.cjs:5
export {};
^^^^^^

SyntaxError: Unexpected token 'export'
    at Object.compileFunction (node:vm:352:18)
    at wrapSafe (node:internal/modules/cjs/loader:1027:15)
    at Module._compile (node:internal/modules/cjs/loader:1063:27)
    at Object.Module._extensions..js (node:internal/modules/cjs/loader:1153:10)
    at Module.load (node:internal/modules/cjs/loader:975:32)
    at Function.Module._load (node:internal/modules/cjs/loader:822:12)
    at ModuleWrap.<anonymous> (node:internal/modules/esm/translators:170:29)
    at ModuleJob.run (node:internal/modules/esm/module_job:198:25)
    at async Promise.all (index 0)
    at async ESMLoader.import (node:internal/modules/esm/loader:409:24)
```


