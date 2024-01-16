# 从零实现一个 React

## 项目初始化

1. 使用`pnpm`配置`monorepo`。

   `pnpm-workspace.yaml`

   ```yaml
   packages:
     - 'packages/*'
   ```

1. 安装`eslint`配置`eslint`的相关配置

   ```bash
   # -w 安装在项目的根目录
   pnpm i -D -w eslint
   # 本地调用执行，pnpm dlx 是远程执行
   pnpm exec eslint --init
   ```

   > 这里配置的时候会出现安装`TS`的`eslint`插件的时候会有问题，可采用去除`@latest`标记自行安装。

1. 安装`prettier`。

   ```bash
   pnpm i -D -w prettier
   ```

   新建`.prettierrc.json`

   ```json
   {
     "$schema": "https://json.schemastore.org/prettierrc",
     "semi": false,
     "tabWidth": 2,
     "singleQuote": true,
     "printWidth": 100,
     "trailingComma": "none"
   }
   ```

1. 安装`husky`

   ```bash
   pnpm dlx husky-init && pnpm install
   ```

1. 配置`commitlint`

   ```bash
   npx husky add .husky/commit-msg 'npx --no -- commitlint --edit "$1"'
   ```

   `.commitlintrc.cjs`

   ```js
   module.exports = {
     extends: ['@commitlint/config-conventional']
   }
   ```
