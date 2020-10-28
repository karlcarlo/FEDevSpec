## 代码规范

### 行业规范

- [Standard](https://standardjs.com/readme-zhcn.html): JavaScript 标准编码风格
- [Airbnb](https://github.com/airbnb/javascript): 一份最合理的 JavasScript 编码规范

**两种常用规范的差别:**
1. 默认必须要分号，而`eslint`默认不添加分号
2. 默认不允许使用`var`创建变量，而是使用`let`或`const`代替
3. 接上一条，如果使用了`let`创建了变量，在后面没有对此变量改变，应当使用`const`代替
4. 最变态的一点，不能使用`for`循环，就算是设置了可以使用`for`循环，不能`for(let i = 0;)`，会提示要使用`const`代替
5. 对箭头函数的使用，能使用监听函数的，需要使用监听函数，对箭头函数使用的限制，有很多。
6. 空格的不同，定义属性时，如 `a : 1`，在`eslint`的标准版，冒号前后需要都加空格，而在`airbnb`中，冒号前面不能加空格。

**项目默认使用`Airbnb`规范**

### 命名规范

> 驼峰式命名法  
> Pascal Case 大驼峰式命名法：首字母大写。`eg：StudentInfo、UserInfo、ProductInfo`  
> Camel Case 小驼峰式命名法：首字母小写。`eg：studentInfo、userInfo、productInfo`

- 项目命名
  > 全部采用小写方式， 以下划线分隔

  例：my_project_name

- 目录命名
  > 参考项目命名，有复数结构时，要采用复数命名法。

  例：scripts, styles, images, templates, pages, layouts, components

- 文件命名
  > 全小写，以下划线分隔

  例：image_preview.js

  如过项目是MVC结构，文件命名可以带上当前模块，便于搜索和理解  
  app/scripts/controllers/login.controller.js  
  app/scripts/services/login.service.js

- 语义化，准确的表达意图
  > 使用英文单词缩写, 避免使用拼音

### CSS规范

- 英文单词，多单词使用`-`连接

```html
<div class="task-list-title">
    <h3 class="task-list-title-h3">
        这里是标题
    </h3>
</div>
<style>
    .task-list-title {
        float:left;
    }
</style>
```

### HTML规范

- 文件编码: 使用不带 BOM 的 UTF-8 编码；
- 在 HTML中指定编码 <meta charset="utf-8"> ；
- 无需使用 `@charset` 指定样式表的编码，它默认为 `UTF-8` （参考 `@charset`）；
- 一律使用小写字母；
- 自闭合（self-closing）标签，无需闭合 ( 例如： `img input br hr` 等 )；
- 可选的闭合标签（closing tag），需闭合 ( 例如：`</li>` 或 `</body>` )；
- 尽量减少标签数量；

### JS规范

- **变量命名：** 驼峰命名法，小写字母开头，**必须声明**
- **函数命名：** 驼峰命名法，小写字母开头。规则：动词或动词 + 名词组合

```javascript
let removeSession = function() {}
let getUser = function() {}
let isAdmin = function() {}
let findMessagesByIdentifier = function() {}
    $scope.taskOpen = function () {
        $scope.taskOpenState = true
    }
```

- 类命名：驼峰命名法，首字母大写
- 每行代码结束尽量不写分号
- 常量用全大写字母，下划线分割
  
  例: `const HTTP_SUCCESS = 200`

- 空格，该有的空格的地方按代码格式化的标准
- 使用单引号 `'`
- 使用三目等，用`===`, `!==`代替`==`, `!=`
- 严格模式，在js文件头部声明 `use strict`
- 一个`function`超过100行就必须要重构，10行内是比较理想的
- 一个文件只干一件事，文件行数不超过200行
- 函数参数不能超过3个，可使用对象代替
- 一个值在代码上出现2次以上就需要提取为常量

### ES6+规范

- 声明变量
  
	一般情况下使用`const`声明 `eslint: prefer-const, no-const-assign`
  
  值需要变化时使用`let`声明 `eslint: no-var jscs: disallowVar`

- 声明方法
  - 使用函数声明代替函数表达式
  - 永远不要在一个非函数代码块（`if`、`while` 等）中声明一个函数，把那个函数赋给一个变量
  - 永远不要把参数命名为 `arguments`。这将取代原来函数作用域内的 `arguments` 对象
  - 不要使用 `arguments`。可以选择 rest 语法 `...` 替代
- 声明类
  - 使用 `class`, 替代传统构造函数。不会变量提升。static 代表静态，其他为原型方法。在内部定义静态属性无效，结尾无分号
- 函数式编程
  
  拆分功能为最小事务单位，每个函数只做一件事，相同的输入必须有相同的输出

- 异步操作
	- Promise
	- async/await

### React规范

- 每个文件只包含一个React组件。`eslint: react/no-multi-comp`
- 始终使用JSX语法
- 不要使用`React.createElement`方法

### Vue规范

---

## 接口文档规范

### 登录功能 <!-- {docsify-ignore} -->

> 测试地址: [/auth/login?userName=user1&&password=abc123](/auth/login?userName=user1&&password=abc123)

- 地址: `/login`
- 请求方式: `POST, GET`
- 请求参数:

| 字段     | 类型     | 必须? | 说明   |
|----------|----------|:-----:|--------|
| userName | `String` | `Y`   | 用户名 |
| password | `String` | `Y`   | 密码   |

- 返回参数:

```json
{
  "code": 0,
  "data": {},
  "msg": "ok"
}
```

| 字段 | 类型     | 默认值 | 说明         |
|------|----------|:------:|--------------|
| code | `Number` | 0      | 返回错误代码 |
| data | `Object` | {}     | 返回数据     |
| msg  | `String` | 'ok'   | 信息状态描述 |