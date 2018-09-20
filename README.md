### Steps
```
npm i
bazel test //etc/api/...
```

### Error in console
```cmd
bazel test //etc/api/...
INFO: Analysed 3 targets (2 packages loaded).
INFO: Found 2 targets and 1 test target...
INFO: From Compiling TypeScript (devmode) //packages/test-package/core:core:

WARNING: your tsconfig.json file specifies options which are overridden by Bazel:
 - compilerOptions.target and compilerOptions.module are controlled by downstream dependencies, such as ts_devserver


INFO: From Compiling TypeScript (devmode) @angular//tools/ts-api-guardian:lib:

WARNING: your tsconfig.json file specifies options which are overridden by Bazel:
 - compilerOptions.target and compilerOptions.module are controlled by downstream dependencies, such as ts_devserver
 - compilerOptions.declaration is always true, as it's needed for dependent libraries to type-check
 - compilerOptions.paths is determined by the module_name attribute in transitive deps[]
 - compilerOptions.rootDir and compilerOptions.baseUrl are always the workspace root directory



TIMEOUT: //etc/api:test-package_core_api (Summary)
      C:/users/alag/_bazel_alag/5ecsjjjn/execroot/testing_guardian/bazel-out/x64_windows-fastbuild/testlogs/etc/api/test-package_core_api/test.log
INFO: Elapsed time: 338.619s, Critical Path: 311.03s
INFO: 5 processes: 3 local, 2 worker.
INFO: Build completed, 1 test FAILED, 10 total actions
//etc/api:test-package_core_api                                         TIMEOUT in 300.1s
  C:/users/alag/_bazel_alag/5ecsjjjn/execroot/testing_guardian/bazel-out/x64_windows-fastbuild/testlogs/etc/api/test-package_core_api/test.log

INFO: Build completed, 1 test FAILED, 10 total actions
```

### Log files contents
```txt
exec ${PAGER:-/usr/bin/less} "$0" || exit 1
Executing tests from //etc/api:test-package_core_api
-----------------------------------------------------------------------------
WARNING: source-map-support module not installed.
    Stack traces from languages like TypeScript will point to generated .js files.
    Set install_source_map_support = False in //etc/api:test-package_core_api_bin to turn off this warning.
    
failed to load main  Error: Source file "packages/test-package/core/npm_package/index.d.ts" not found
    at ResolvedDeclarationEmitter.emit (C:\users\alag\_bazel_alag\5ecsjjjn\execroot\testing_guardian\bazel-out\x64_windows-fastbuild\bin\external\angular\tools\ts-api-guardian\lib\serializer.js:67:23)
    at publicApiInternal (C:\users\alag\_bazel_alag\5ecsjjjn\execroot\testing_guardian\bazel-out\x64_windows-fastbuild\bin\external\angular\tools\ts-api-guardian\lib\serializer.js:51:77)
    at Object.publicApi (C:\users\alag\_bazel_alag\5ecsjjjn\execroot\testing_guardian\bazel-out\x64_windows-fastbuild\bin\external\angular\tools\ts-api-guardian\lib\serializer.js:39:16)
    at Object.verifyAgainstGoldenFile (C:\users\alag\_bazel_alag\5ecsjjjn\execroot\testing_guardian\bazel-out\x64_windows-fastbuild\bin\external\angular\tools\ts-api-guardian\lib\main.js:34:35)
    at Object.startCli (C:\users\alag\_bazel_alag\5ecsjjjn\execroot\testing_guardian\bazel-out\x64_windows-fastbuild\bin\external\angular\tools\ts-api-guardian\lib\cli.js:82:43)
    at Object.<anonymous> (C:\users\alag\_bazel_alag\5ecsjjjn\external\angular\tools\ts-api-guardian\bin\ts-api-guardian:3:23)
    at Module._compile (internal/modules/cjs/loader.js:702:30)
    at Object.Module._extensions..js (internal/modules/cjs/loader.js:713:10)
    at Module.load (internal/modules/cjs/loader.js:612:32)
    at tryModuleLoad (internal/modules/cjs/loader.js:551:12)

```