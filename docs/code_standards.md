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

id使用`_`连接副

```html
<div id="task_list" class="task-list-title">
    <h3 class="task-list-title-h3">
        这里是标题
    </h3>
</div>
<style>
    #task_list {
        display: flex;
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
- **函数命名：** 驼峰命名法，小写字母开头。规则：**动词 或 动词 + 名词组合**

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

-   UI框架选择

    -   四大场景框架

-   组件结构规范：文件路径按照菜单定义。顶级菜单对应一个一级文件夹，依次类推。

    -   基础组件：

        当项目中需要自定义比较多的基础组件的时候，比如一些`button，input，icon`，建议以一个统一的单词开头，或者放到通用文件夹统一管理，这样做的目的是为了方便查找。
        公共组件应该都放到`components`文件夹下，单个组件独 立一个文件夹，用来放相对应的vue文件以及页面相关的样式 文件，样式少可直接写到页面组件里边，这样更符合组件化 的思想。组件结构：
        组件结构遵循从上往下`templates，scripts，styles`的结构。

    -   项目组件：

        组件名以单词大写开头，当多个单词拼写成的组件时，采用驼峰式命名规则。一般是多个单词全拼，减少简写的情况，这样增加可读性。

        页面级组件应该放到相对应页面文件夹下，比如一些组件只有这个页面用到，其他地方没有用到的，可以直接放到页面文件夹，增加`components`子文件夹。

-   Template模板文件

    1.   尽量使用以.vue结束的单文件组件，方便管理，结构清晰。
    2.   标签语义化，避免清一色的div元素
    3.   DOM的层级数尽可能少，优化渲染速度。
    4.   编写业务代码时，尽量查看原型后开发，页面布局样式尽量保持一致。比如列表页面的查询和表格等通用功能。先确认后开发。
    5.   尽量少使用br标签换行。使用布局`flex，grid`等（ps：grid布局chrome 57以上才支持），少使用table布局。
    6.   样式class的命名：统一以小写字母开头，小写字母、下划线和数字组成。命名中尽量避免使用中文拼音，应该采用更简明有语义的英文单词进行组合。不建议使用驼峰法命名class属性。使用下划线的目的是为了和第三方库中的命名冲突。例如：xx_left,xx_line。
    7.   自定义标签：使用自闭标签的写法。例如：，如果自定义标签中间需要传入slot，则写开始标签和结束标签，结束标签必须加/。
    8.   v-slot：在vue2.6版本中，slot与slot-scope已被弃用，统一使用v-slot指令。
    9.   相同的卡片布局，首先整合数据，尽量使用循环方式去增加，避免变更多处的问题。

-   Script脚本

    1.   在 script 标签中，遵守 Js 的规范和ES6规范。
    2.   组件名称：必须以大写字母开头驼峰法命名。使用时，用小写英文，单词之间使用 ‘-’分割，eg:
    3.   Data必须是一个函数。
    4.   Props定义：提供默认值，使用type属性校验类型，使用props之前先检查prop是否存在
    5.   全局已经引入的组件，不要重复引用注册到局部。
    6.   尽量按照Vue钩子调用顺序和推荐顺序书写，`components, props, data, computed, watch, created, mounted, activited , update, methods`.
    7.   调试信息 `console.log()` `debugger`使用完及时删除。
    8.   为v-for设置Key值。(不建议 用index 作为 key，和没写基本上没区别，因为不管你数组的顺序怎么颠倒，index 都是 0, 1, 2 这样排列，导致 Vue 会复用错误的旧子节点，做很多额外的工作)
    9.   规避v-if和v-for用在一起。或者增加一层
    10.   使用ES6风格编码源码,定义变量使用`let`, 定义常量使用`const`, 使用`export, import`模块化。
    11.   指令缩写：都用指令缩写 (用 : 表示 v-bind: 和用 @ 表示 v-on:)。
    12.   使用 data 里的变量时请先在 data 里面初始化。
    13.   函数中统一使用_this=this来解决全局指向问题。
    14.   使用‘===’和‘!==’。
    15.   整合数据时尽量使用ES6，`Object.assign`和 `…` 扩展符（ps：Object.assign() 为浅复制）
    16.   页面定义只是用来转化显示的对象时，直接声明到顶部，属于无需监听的数据。
    17.   校验时，先去校验公共库查找是否有对应校验，有则使用，没有则查看是否要多处使用，如果可复用，则进行抽离。
    18.   vue项目中尽量减少或避免进行dom操作，全部通过vue数据进行驱动。

-   CSS 样式 / Style

    1.   使用 scoped关键字，约束样式生效的范围。
    2.   避免使用标签选择器（效率低、损耗性能）。
    3.   CSS 属性书写顺序：**先决定定位宽高显示大小，再做局部细节修饰！**推荐顺序：定位属性(或显示属性，display)->宽高属性->边距属性(margin, padding)->字体，背景，颜色等，修饰属性的定义。

    

Vuex中store

1.   各个文件的命名根据上面的项目结构命名。

2.   应用层级的状态应该集中到单个 store 对象中。

3.   提交 mutation 是更改状态的唯一方法，并且这个过程是同步的。

4.   异步逻辑都应该封装到 action 里面。

5.   vuex 的dispatch和commit提交mutation的区别：dispatch=>actions用来触发异步操作，commit=>mutation用来触发同步操作的方法。当操作行为中含有异步操作，比如向后台发送请求获取数据，就需要使用action的dispatch去完成，其他使用commit即可。



Router 路由

1.   路由至少包含三个选项：`path、name、component`。path统一小写；name对应于组件中的name，大写开头驼峰；component组件驼峰。名称大写开头的组件

2.   路由使用动态路由。



组件化及代码复用

当有多处使用相同代码逻辑时，应该将代码逻辑进行抽离，进行代码复用，包括不限于`vue mixins、vue components、filters、自定义指令、js函数、sass样式等`，且抽离的公共部分尽量不要包含业务逻辑，以保证最大限度的复用性。



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

