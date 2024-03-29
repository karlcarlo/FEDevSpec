## 常用组件或框架

- [lodash](https://lodash.com/docs) 一个一致性、模块化、高性能的 JavaScript 实用工具库。
- [dayjs](https://github.com/iamkun/dayjs) 一个极简的JavaScript库，可以为现代浏览器解析、验证、操作和显示日期和时间。
- [axios](https://github.com/axios/axios) 一个基于 `promise` 的 `HTTP` 库,可以用在浏览器和 `node.js` 中
- [mock.js](https://github.com/nuysoft/Mock/wiki) 生成随机数据，拦截 `Ajax` 请求
- [antd](https://ant.design/) 基于 Ant Design 设计体系的 React UI 组件库，主要用于研发企业级中后台产品。
- [vben](https://vvbin.cn/doc-next/) 一个开箱即用的企业级前端框架。



## 创建本地项目

在开始构建项目阶段，一般有3种方式：
1. 使用基本命令创建目录和初始化`npm`项目环境，手动配置依赖包。或者使用通用构建脚手架，例如[Yeoman](https://yeoman.io/)建立项目；
2. 利用[vue-cli](https://cli.vuejs.org/zh/)、[Create React App](https://create-react-app.dev/)或[Vite](https://vitejs.cn/)创建专属项目；
3. 第三种，直接从代码库拉取已有的项目；



### 手动创建本地项目

```bash
# 创建目录
mkdir app-name && cd app-name

# 初始化项目
npm init

# 安装npm依赖
npm install package-name
```



### 通过构建器创建项目

1. **Yeoman**

```bash
# 安装
npm install -g yo

# 安装定制的生成器
npm install -g generator-webapp

# 通过脚手架创建定制项目
yo webapp
```

2. **vue-cli**

**Node 版本要求：**

`Vue CLI 4.x` 需要 [Node.js](https://nodejs.org/zh-cn/) v8.9 或更高版本 (推荐 v16 以上)。你可以使用 [n](https://github.com/tj/n)，[nvm](https://github.com/creationix/nvm) 或 [nvm-windows](https://github.com/coreybutler/nvm-windows) 在同一台电脑中管理多个 Node 版本。

```bash
# 可以使用下列任一命令安装这个新的包
npm install -g @vue/cli
# OR
yarn global add @vue/cli

# 运行以下命令来创建一个新项目
vue create hello-world
```

参考[创建一个项目](https://cli.vuejs.org/zh/guide/creating-a-project.html)

3. **create react app**

```bash
# 快速创建React项目
npx create-react-app my-app
cd my-app
npm start
```

![](assets/reactStart.svg)

4. **Vite**

```bash
# 使用NPM
npm create vite@latest

# 使用Yarn
yarn create vite

# 使用 PNPM
pnpm create vite

```

然后按照提示操作即可

你还可以通过附加的命令行选项直接指定项目名称和你想要使用的模板。例如，要构建一个 Vite + Vue 项目，运行

```bash
# npm 6.x
npm create vite@latest my-vue-app --template vue

# npm 7+, extra double-dash is needed:
npm create vite@latest my-vue-app -- --template vue

# yarn
yarn create vite my-vue-app --template vue

# pnpm
pnpm create vite my-vue-app --template vue

```

参考[Vite-Vue3-VueRouter-Pinia-startkit](https://github.com/karlcarlo/vite-vue3-VueRouter-Pinia-startkit)



### 拉取远程Git项目

* git库地址: <https://git.diamchain.com/>

```bash
git clone <repo-url> [new Name]
```



## 项目文件夹结构

前端项目：

```
├── dist 线上打包
├── mocks 本地测试数据
├── public 静态资源
├── src
│   ├── components 组件
│   ├── models 数据模型
│   ├── layouts
│   │   └── index.tsx 默认模板
│   ├── pages 页面
│   │   ├── index.less 默认样式
│   │   └── index.tsx 默认页面
│   ├── routes 路由
│   │   └── index.ts 默认路由
│   └── app.ts 入口文件
├── tests
│   ├── e2e 端到端测试
│   └── unit 单元测试
└── package.json 项目依赖包
```

中台项目：

```
├── plop-templates 微构建模版
│   ├── controller.hbs
│   ├── model.hbs
│   └── route.hbs
├── src
│   ├── controllers 控制器
│   │   ├── auth_ctrl.ts
│   │   ├── roles_ctrl.ts
│   │   └── users_ctrl.ts
│   ├── models 模型
│   │   ├── role.ts
│   │   └── user.ts
│   ├── routes 路由
│   │   ├── auth_route.ts
│   │   ├── index.ts
│   │   ├── roles_toute.ts
│   │   └── users_route.ts
│   ├── utils 工具
│   │   ├── index.ts
│   │   └── pagination.ts
│   ├── config.ts 配置文件
│   └── main.ts
├── tests
│   ├── e2e 端到端测试
│   └── unit 单元测试
├── package.json
├── plopfile.js 微构建配置
├── tsconfig.json
└── tslint.json
```



## 配置vscode插件

- **Auto Rename Tag** 

  自动完成另一侧标签的同步修改

- **Bracket Pair Colorizer** 

  给括号加上不同的颜色，便于区分不同的区块，使用者可以定义不同括号类型和不同颜色

- **Better Comments**

  注释增强

- **Debugger for Chrome：** 

  映射vscode上的断点到chrome上，方便调试

- **EditorConfig for VS Code**

    简单编码风格配置

- **GitLens** 

  方便查看git日志，git重度使用者必备

- **ESLint** 

  是VSCode ESLint的扩展，将ESLint JavaScript集成到VS Code中

- **Highlight Matching Tag**

    标签高亮

- **Iconify IntelliSense**

    智能图标显示

- **Image preview**

    图片预览

- **Indent-Rainbow**

    代码缩进彩虹颜色提示

- **JavaScript(ES6) code snippets** 

  ES6语法智能提示，以及快速输入，不仅仅支持.js，还支持.ts，.jsx，.tsx，.html，.vue

- **open in browser** 

  vscode不像IDE一样能够直接在浏览器中打开html，而该插件支持快捷键与鼠标右键快速在浏览器中打开html文件，支持自定义打开指定的浏览器，包括：Firefox，Chrome，Opera，IE以及Safari

- **Path Intellisense** 

  自动提示文件路径，支持各种快速引入文件

- **Prettier** 

  将整个 JS 和 CSS 文档快速格式化为统一的代码样式。如果你还想使用 ESLint，那么还有个 Prettier – Eslint 插件

- **Volar** 

  Vue多功能集成插件，包括：语法高亮，智能提示，emmet，错误提示，格式化，自动补全，debugger。vscode官方钦定Vue插件。

  


## 配置git库

### git flow

![](/assets/gitflow.webp)

- Main分支
- Develop分支
- Feature分支
- Release
- Hotfixes



## 安装依赖包

```bash
# npm
npm install

# yarn
yarn

# pnpm
pnpm install

```



## 启动本地服务

根据项目中package.js中scripts中定义的项启动

```bash
# Vue
vue start

# Yarn
yarn dev

# Pnpm
pnpm dev
```