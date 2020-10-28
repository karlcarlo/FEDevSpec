## 端到端测试(End to End)

虽然单元测试为开发者提供了一定程度的信心，但是单元测试和组件测试在部署到生产环境时提供应用整体覆盖的能力是有限的。因此，端到端测试可以说从应用最重要的方面进行测试覆盖：当用户实际使用应用时会发生什么。

- [Cypress.io](https://www.cypress.io/) 是一个测试框架，旨在通过使开发者能够可靠地测试他们的应用，同时提供一流的开发者体验，来提高开发者的生产率。

- [Puppeteer](https://pptr.dev/) 是一个 Node.js 库，它提供高阶 API 来控制浏览器，并可以与其他测试运行程序 (例如 `Jest`) 配对来测试应用。

## 单元测试(Unit)

单元测试允许你将独立单元的代码进行隔离测试，其目的是为开发者提供对代码的信心。通过编写细致且有意义的测试，你能够有信心在构建新特性或重构已有代码的同时，保持应用的功能和稳定。

- [Jest](https://jestjs.io/zh-Hans/) 是一个专注于简易性的 JavaScript 测试框架。一个其独特的功能是可以为测试生成快照 (snapshot)，以提供另一种验证应用单元的方法。
- [Mocha](https://mochajs.org/) 是一个专注于灵活性的 JavaScript 测试框架。因为其灵活性，它允许你选择不同的库来满足诸如侦听 (如 [Sinon](https://sinonjs.org/)) 和断言 (如 [Chai](https://www.chaijs.com/)) 等其它常见的功能。同时支持在Node.js和浏览器里运行测试。


## Mock数据

Mock 数据是前端开发过程中必不可少的一环，是分离前后端开发的关键链路。通过预先跟服务器端约定好的接口，模拟请求数据甚至逻辑，能够让前端开发独立自主，不会被服务端的开发所阻塞。

### 约定式 Mock 文件

Umi 约定 `/mock` 文件夹下所有文件为 mock 文件。

```
├── mock
    ├── api.ts
    └── users.ts
└── src
    └── pages
        └── index.tsx
```

`/mock` 下的 `api.ts` 和 `users.ts` 会被解析为 mock 文件。

### 引入 Mock.js

[Mock.js](http://mockjs.com/) 是常用的辅助生成模拟数据的三方库，借助他可以提升我们的 mock 数据能力。

参考[语法规范文档](https://github.com/nuysoft/Mock/wiki)

示例:

```typescript
import mockjs from 'mockjs';
export default {
  // 使用 mockjs 等三方库
  'GET /api/tags': mockjs.mock({
    'list|100': [{ name: '@city', 'value|1-100': 50, 'type|0-2': 1 }],
  }),
};
```