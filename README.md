
Related to https://github.com/bazelbuild/rules_nodejs/issues/325

### Steps
```
npm i
bazel test //etc/api/...
```


### Log files contents
```txt
exec ${PAGER:-/usr/bin/less} "$0" || exit 1
Executing tests from //etc/api:accept
-----------------------------------------------------------------------------
[ 'C:\\Users\\alag\\_bazel_alag\\qxvail6p\\external\\nodejs\\bin\\nodejs\\node.exe',
  'testing_guardian/etc/api/index.js',
  '--in',
  '--out',
  'C:/git/ts-api-guardian-windows-bazel/etc/api/test-package/core/index.d.ts' ]


```
