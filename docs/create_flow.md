## 常用组件或框架

- lodash
- axios
- mock.js
- antd
- umi

## 创建本地项目

在开始构建项目阶段，一般有3种方式：
1. 使用基本命令创建目录和初始化npm项目环境，手动配置依赖包。或者使用通用构建脚手架，例如[Yeoman](https://yeoman.io/)建立项目；
2. 利用[vue-cli](https://cli.vuejs.org/zh/)、[Create React App](https://create-react-app.dev/)或[Umi](https://umijs.org/zh-CN)创建专属项目；
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

`Vue CLI 4.x` 需要 [Node.js](https://nodejs.org/zh-cn/) v8.9 或更高版本 (推荐 v10 以上)。你可以使用 [n](https://github.com/tj/n)，[nvm](https://github.com/creationix/nvm) 或 [nvm-windows](https://github.com/coreybutler/nvm-windows) 在同一台电脑中管理多个 Node 版本。

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

4. **Umi**

```bash
# 创建目录
$ mkdir myapp && cd myapp

# 安装依赖
$ yarn add umi

# 创建页面
$ npx umi g page index --typescript --less

# 启动开发
$ npx umi dev
```

或者

```bash
yarn create @umijs/umi-app
或
npx @umijs/create-umi-app
```

参考[Umi框架文档](https://umijs.org/zh-CN/docs)

### 拉取远程Git项目

* git库地址: <http://gitlab.corp.elensdata.com/>

```bash
git clone repo-url
```

## 项目文件夹结构

```
├── dist 线上打包
├── mock 本地测试数据
├── public 静态资源
└── src
    ├── components 组件
    ├── models 数据模型
    ├── layouts
        └── index.tsx 默认模板
    ├── pages 页面
        ├── index.less 默认样式
        └── index.tsx 默认页面
    ├── routes 路由
        └── index.ts 默认路由
    └── app.ts 入口文件
├── tests
    ├── e2e 端到端测试
    └── unit 单元测试
└── package.json 项目依赖包
```

## 配置vscode插件
- **Auto Close Tag** 
  
  自动闭合HTML/XML标签

- **Auto Rename Tag** 
  
  自动完成另一侧标签的同步修改

- **Bracket Pair Colorizer** 
  
  给括号加上不同的颜色，便于区分不同的区块，使用者可以定义不同括号类型和不同颜色

- **Debugger for Chrome：** 
  
  映射vscode上的断点到chrome上，方便调试

- **GitLens** 
  
  方便查看git日志，git重度使用者必备

- **ESLint** 
  
  是VSCode ESLint的扩展，将ESLint JavaScript集成到VS Code中

- **JavaScript(ES6) code snippets** 
  
  ES6语法智能提示，以及快速输入，不仅仅支持.js，还支持.ts，.jsx，.tsx，.html，.vue

- **open in browser** 
  
  vscode不像IDE一样能够直接在浏览器中打开html，而该插件支持快捷键与鼠标右键快速在浏览器中打开html文件，支持自定义打开指定的浏览器，包括：Firefox，Chrome，Opera，IE以及Safari

- **Path Intellisense** 
  
  自动提示文件路径，支持各种快速引入文件

- **Prettier** 
  
  将整个 JS 和 CSS 文档快速格式化为统一的代码样式。如果你还想使用 ESLint，那么还有个 Prettier – Eslint 插件

- **React/Redux/react-router Snippets** 
  
  React/Redux/react-router语法智能提示

- **Vetur** 
  
  Vue多功能集成插件，包括：语法高亮，智能提示，emmet，错误提示，格式化，自动补全，debugger。vscode官方钦定Vue插件。

- **VueHelper** 
  
  snippet代码片段, 变量名跳转


## 配置git库

### git flow

![](/assets/gitflow.webp)

- Master分支
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
```

## 启动本地服务

根据项目中package.js中scripts中定义的项启动

```bash
# Vue
vue start

# React
yarn start

# Umi
yarn start:dev
```