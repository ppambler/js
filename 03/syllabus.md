### ✍️ Tangxt ⏳ 2021-02-20 🏷️ 大纲

# 大纲

## ★第一部分：面向对象

### <mark>1）面向对象基础</mark>

- 【60 min】理解面向对象思想、掌握类的写法
  - 【5 min】类的用途：React/Vue 中的组件、Koa 中的服务器、JS 中的 Date
  - 【20 min】面向对象思想
    - 是什么，包含什么（变量、方法、构造函数），概念（类、实例、成员、成员变量、成员方法）
    - 封装（东西都在一起）、继承（在已有的类的基础上添加或修改特性）、多态
  - 【10 min】类的写法
    - 古典方式：类和构造函数、原型基础
    - ES6 方式：class
    - 类的本质：编译成普通代码的 class 长什么样（为什么我们还有用 OO——因为写着方便）
      - 从本质上说，没有“面向对象这个概念”，类最终会被编译为变量和函数
      - 当然，函数其实也不存在，本质上就是一堆代码
  - 【10 min】typeof、instanceof 和 constructor
  - 【15 min】**实例：榜单类的实现**
    - 构造函数：处理 DOM 和初始数据
    - 方法：reload、prev、next 等
    - 属性：当前页码
- 【25 min】理解 prototype 原型的含义，并掌握其用法
  - `__proto__`和`prototype`
  - 【10 min】原型的工作原理：往上找
  - 【15 min】**实例：补充系统类的功能**
    - Array：map、filter、from
      - 静态成员修饰符：static
    - String：startsWith
- 【30 min】明确 JS 中 this 的规则及使用技巧
  - 【15 min】this 的本质：方法由谁调用——手动编译 JS 代码
    - 方法
    - 普通函数、严格模式
    - 事件
    - 定时器
  - 【15 min】操纵 this：call/apply/bind、箭头函数
- 【15 min】**实战：UI 组件类的编写**
  - 豆瓣 FM

### <mark>2）面向对象与继承</mark>

- 【35 min】继承的意义
  - 【10 min】作用：层次、共享父级的属性和方法
  - 【15 min】适用场景：拥有明确的父子级关系、子类能完全覆盖父类
    - 例子：组件继承自 Component 类
    - 例子：ImageFile 继承 File 类
    - 例子：VipUser 继承 User
    - 反例：File 继承 User 类
  - 【10】继承与组合
    - JS 支持单继承，不支持多重继承（C++支持）
    - 例子：Company 类、Staff 类、jobs 类
- 【40】继承的写法
  - 【10】古典写法
  - 【15】ES6 写法：super、extends 关键字
  - 【5】instanceof
  - 【10】继承可以覆盖父类方法（可以重用、也可以完全重写）
- 【15】原型链
  - 【10】何为原型链
  - 【5】原型链的意义——对语言自身意义重大，对我们用处不大
- 【30】实战继承
  - 【20】实例：Employee 类、Coder 类、Designer 类、Manager 类
    - Employee：name、department、entry、basicSalary、calcSalary()
    - Coder：manager、language、*calcSalary()
    - Designer：manager、style、*calcSalary()
    - Manager：manager、staffs[]、*calcSalary()
  - 【10】实例：User 类、VipUser 类
    - User：name、img、render()
    - VipUser：level

### <mark>3）可响应对象</mark>

- 【30 min】高阶类（Higher-order class）的使用
  - 【5 min】为类动态添加一些公共方法、属性
    - 继承的同时，为子类添加新的成员（而这个成员是要在父类中进行使用的——换句话说，父类无法直接单独使用）
  - **【15 min】实战：Store 类（全局统一存储及其订阅）的编写**
  - **【10 min】实战：Store 衍生类的编写（LocalStorage、SessionStore 和 ServerStore）**
- 【5 min】可响应对象
  - 【5 min】数据监听——当数据发生变化时，能得到通知
- 【15 min】方案 1：访问器
  - 【10 min】get/set
  - **【5 min】实例：改进第一课的榜单类（支持 page++、page—）**
    - throw new RangeError('out of range')
- 【40 min】方案 2：defineProperty
  - 【15 min】Object.setPrototypeOf、Object.defineProperty
  - **【10 min】实例：改进第一课的榜单类（支持支持 page++、page—）**
  - **【15 min】改进 Store 类**
- 【50 min】方案 3：Proxy
  - 【5 min】Observe 对象（已废弃）
  - 【20 min】Proxy 类使用
  - **【10 min】实例：改进第一课的榜单类（支持支持 page++、page—）**
  - **【15 min】改进 Store 类**
- **实战：豆瓣音乐播放器**

## ★第二部分：事件与队列

![image-20210220142921962](https://gitee.com/ppambler/blog-images/raw/master/images/image-20210220142921962.png)

### <mark>1）JS 事件</mark>

- 【80】事件对象
  - 【5】用于获取事件的信息：`ev || event`
  - 【15】通用事件（Event）
    - cancelBubble/stopPropagation
    - preventDefalut
    - stopImmediatePropagation()
    - target
    - ~~type、srcElement~~
  - 【15】鼠标事件（MouseEvent）
    - ~~alt/ctrl/shift~~
    - clientX/Y
    - pageX/Y
    - offsetX/Y
  - 【20】实例：放大镜
  - 【15】键盘事件（KeyboardEvent）
    - ~~alt/ctrl/shift~~
    - key/keyCode
    - repeat
  - **【10】实例：图集翻页**
- 【10】事件流
  - 冒泡阶段
  - 捕获阶段
- 【15】掌握 JS 中的常用事件
  - oninput
  - onfocus、onblur
  - onchange
  - onload 和 DOMContentLoaded
- 【15】理解移动端 touch 事件的使用
  - touchstart、touchmove、touchend

### <mark>2）事件队列</mark>

- **【60】实战：移动端手势识别库**
  - 【15】拖动事件
  - 【30】方向锁定
  - 【25】手势识别
- 【20】自定义事件
  - 【15】dispatchEvent()
  - 【5】事件触发的机制
- 【5】事件订阅模式
  - 优势：事件双方隔离
- 【25】事件队列
  - 【15】加入等待
  - 【10】触发事件
- **【20】实战：豆瓣音乐播放器（事件订阅）**

## ★第三部分：DOM 与虚拟 DOM

DOM 操作也是原生 JS 的一类重要功能，同时，虚拟 DOM 在性能上拥有巨大优势，可以对原生 DOM 操作进行很好的补充，在各大视图层框架中（Vue、 React 为代表）作为内核代码存在，这一部分我们将学习这两项技术的使用

### <mark>1）DOM 操作与节点编译</mark>

- 【15】DOM 节点
  - 【5】父节点：parentNode
  - 【10】子节点
    - children
    - childNodes
      - nodeType、ELEMENT_NODE-innerHTML、TEXT_NODE-data
  - 节点的遍历：Array.from
- 【25】DOM 操作
  - 【10】创建：document.createElement、document.createTextNode('aaa')、`*createElementNS`
  - 【5】插入：appendChild(new)、insertBefore(new,old)
  - 【5】删除：removeChild(ele)
  - 【5】替换：replaceChild(new,old)
- 【25】文档碎片——高效操作大量重复元素
  - 【5】创建：document.createDocumentFragment
  - 【5】使用：fragment.appendChild
  - 【15】实例：使用文档碎片（性能大约提示 2.5 倍）
    - 方式 1：直接操作、每次重新创建元素
    - 方式 2：开始时创建一组元素装入 frag，后续对该 frag 进行 cloneNode
- 【30】DOM 属性操作
  - 【10】获取和设置：get/setAttribute、与直接操作的区别
  - 【15】属性列表：attributes
    - 循环：普遍 for
    - 元素项：attributes[0]:Attr
      - .name
      - .value
  - 【5】自定义数据和 dataset
- 实战：DOM 节点编译（初级版）
  - 《1.DOM 与可响应对象。html》

### <mark>2）虚拟 DOM</mark>

- 虚拟节点的抽象
- DOM 节点的编译：elm、属性、children、事件
- 虚拟 DOM 树、节点的递归编译

## ★第四部分：数据交互与数据操作

数据交互是非常常见的一类功能，几乎所有应用中都会用到，在这一部分中我们将深入学习数据交互的各类方法、各种数据和应用场景的处理

### <mark>1）数据交互与异步操作</mark>

- 原生数据交互方式：XHR 对象、 fetch 对象
- 深入 FormData：文件、进度
- 跨域数据请求的处理
- websocket 使用
- **实战：多人协作文档**

### <mark>2）数据操作</mark>

- FileReader、文件数据处理：base64、blob、 Array Buffer（及封装类型）
- Html5 File Api 的使用
- **实战："我画你猜"游戏简易版**

## ★第五部分、图形与动画

canvas 和 SVG 是最常用的两种 web 端图形处理技术，在各类图表、游戏等场景中有丰富的应用；动画也是非常常用的功能，从简单的 CSS3 动画到 JS 实现的自定义动画，此部分课程将带领大家学习这两个内容

### <mark>1）图形操作 </mark>

- canvas 图形操作：点、线、图形、img 等
- **实战：canvas 图形操作类的封装** 
- SVG 图形操作：图形元素的创建、删除、修改
- **实战：SVG 图形操作库的封装**

### <mark>2）动画操作 </mark>

- CSS3 动画：transition、 animation、js 动画监听、动态动画类的生成
- **实战：基于 CSS3 的 jS 动画库**
- JS 实现动画：关键帧、路径计算
- **实战：纯 JS 动画库**

## ★实战一：数据交互的封装与应用

axios.js 是非常常用的数据交互开发库，而在这个部分中，我们将剖析其功能并从零开始完成自己的数据交互库的编写和封装（**并不会分析和拆解 axios.js 自身的代码，而是从零开始自己实现**）

### <mark>1）封装数据交互</mark>

- 核心请求的封装（XHR 对象）、请求超时、请求取消
- 数据解析：body、 header
- 请求配置、全局配置、配置对象

### <mark>2）封装数据交互（续）</mark>

- 请求变换、响应变换、拦截器模式
- 错误处理
- 全端请求配置（Node.js、前台 JavaScript）

## ★实战二：深入剖析 MVVM 框架 

Vue.js 是非常流行的 mvvm 视图层框架，能极大的降低程序开发难度，同时，其中大量运用了响应、数据同步、虚拟 DOM 等技术，理解其原理，既可以对原生 JS 开发有很大的借鉴，同时也是对本课程所学知识的系统、深入应用，在此部分，我们将从零开始探究 mvvm 框架的编写和应用（**并不会分析和拆解 vue.js 自身的代码**，而是从零开始自己实现）

### <mark>1）MVVM 模式、编译 HTML 代码</mark>

- 理解 mvvm 模式中各个模块的角色（ model 的数据监听、ⅴ的视图渲染、vm 的逻辑功能）
- 配置的解析、对象的构造
- 数据（ model）的构建
- HTML 代码编译、虚拟 DOM 树的生成和维护
- 渲染操作

### <mark>2）数据绑定、虚拟 DOM 的更新</mark>

- 属性解析
- 数据绑定、事件绑定
- 数据更新与重新渲染、DOM 复用（diff 判定算法）
- 组件的创建、管理

### <mark>3）指令</mark>

- 指令集合、自定义指令
- v-bind 指令
- v-if 指令
- v-for 指令、key 属性
- v-on 事件

### <mark>4）全局数据管理</mark>

- 状态对象、访问器的使用
- 数据的更新、监控
- getters 访问器
- 数据管理器的简化

### <mark>5）路由与视图更新</mark>

- 路由的原理
- 动态组件渲染
- 路由匹配、参数采集