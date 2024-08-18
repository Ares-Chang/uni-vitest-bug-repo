# Uni App 搭配 Vitest 错误问题仓库

此仓库拉取自官方模板 [dcloudio/uni-preset-vue#vite-ts](https://github.com/dcloudio/uni-preset-vue/tree/vite-ts)，并添加 vitest 库, 为一个最小可复现仓库。

## Use

1. 下载依赖

```sh
npm install
```

2. 运行测试

```sh
npm run test
```

目标应该测试运行成功，但现在支持报错

```sh
> uni-preset-vue@0.0.0 test D:\project\uni-vitest-bug-repo
> vitest

The CJS build of Vite's Node API is deprecated. See https://vitejs.dev/guide/troubleshooting.html#vite-cjs-node-api-deprecated for more details.
编译器版本：4.24（vue3）
正在编译中...

⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯ Startup Error ⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯⎯
Error: Cannot find module 'vuex/package.json'
Require stack:
- D:\project\uni-vitest-bug-repo\node_modules\.pnpm\@dcloudio+uni-cli-shared@3.0.0-4020420240722002_postcss@8.4.41_rollup@4.21.0_vue@3.4.38_typescript@4.9.5_\node_modules\@dcloudio\uni-cli-shared\dist\resolve.js

......
```

测试库运行并没有包含 vuex 相关应用，不应该加载 vuex 相关依赖，导致运行失败。

如果单独安装 vuex 可运行成功，但这并不是项目应该需要的。

感谢查看，烦请解决，感谢。