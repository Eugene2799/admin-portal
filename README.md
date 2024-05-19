# admin-portal 项目

### 安装使用

> #### 注意: 本地环境需要安装 [Node.js 18.x+](https://nodejs.org/en)、[pnpm 8.x+](https://github.com/pnpm/pnpm/)

```shell script
# 安装pnpm

npm install pnpm -g

# 安装依赖
pnpm install

# 启动服务
pnpm serve

# build
pnpm dev

# prettier 格式化代码
pnpm lint:prettier

```

### 项目结构目录

```text
admin-portal
├─ build                  # Vite 配置项
├─ public                 # 静态资源文件（该文件夹不会被打包）
├─ src
│  ├─ api                 # API 接口管理
│  ├─ assets              # 静态资源文件
│  ├─ components          # 全局组件
│  ├─ config              # 全局配置项
│  ├─ hooks               # 常用 Hooks 封装
│  ├─ languages           # 语言国际化 i18n
│  ├─ layout              # 框架布局模块
│  ├─ router              # 路由管理
│  ├─ store               # pinia store
│  ├─ styles              # 全局样式文件
│  ├─ typings             # 全局 ts 声明
│  ├─ utils               # 常用工具库
│  ├─ views               # 项目所有页面
│  ├─ App.vue             # 项目主组件
│  ├─ main.ts             # 项目入口文件
│  ├─ auto-import.d.ts    # 自动导入vue、vue-router、pinia相关API（无需import引入）
│  └─ vite-env.d.ts       # 指定 ts 识别 vue
├─ .env.dev               # 开发环境配置
├─ .env.prod              # 生产环境配置
├─ .env.sit               # 测试环境配置
├─ .eslintignore          # 忽略 Eslint 校验
├─ .eslintrc.cjs          # Eslint 校验配置文件
├─ .gitignore             # 忽略 git 提交
├─ .prettierignore        # 忽略 Prettier 格式化
├─ .prettierrc.cjs        # Prettier 格式化配置
├─ .stylelintignore       # 忽略 stylelint 格式化
├─ .stylelintrc.cjs       # stylelint 样式格式化配置
├─ index.html             # 入口 html
├─ stats.html             # Rollup Visualizer html
├─ deploy.sh              # 发布GitHub Pages指令
├─ LICENSE                # 开源协议文件
├─ pnpm-lock.yaml         # 依赖包包版本锁
├─ package.json           # 依赖包管理
├─ postcss.config.cjs     # postcss 配置
├─ README.md              # README 介绍
├─ tsconfig.json          # typescript 全局配置
└─ vite.config.ts         # vite 全局配置文件
```

### Git 提交规范

- `ci`: ci 配置文件和脚本的变动;
- `chore`: 构建系统或辅助工具的变动;
- `fix`: 代码 BUG 修复;
- `feat`: 新功能;
- `perf`: 性能优化和提升;
- `refactor`: 仅仅是代码变动，既不是修复 BUG 也不是引入新功能;
- `style`: 代码格式调整，可能是空格、分号、缩进等等;
- `docs`: 文档变动;
- `test`: 补充缺失的测试用例或者修正现有的测试用例;
- `revert`: 回滚操作;
