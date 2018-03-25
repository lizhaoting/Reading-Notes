# Front_end_Interview
<a name='table-of-contents'>前端面试题 & 答案整理</a>





#### <a name='html-interviews'>HTML 相关：</a>

* Html的语义化

* 怎么得到一个页面的a标签（就说了getElementByTagName和选择器）

* 怎么在页面里放置一个很简单的图标，不能用img和background-img

  （说了canvas，或者一些库有icon库，data-icon).



* HTML5新增了哪些内容或API，使用过哪些

* input和textarea的区别
* 用一个div模拟textarea的实现
* 移动设备忽略将页面中的数字识别为电话号码的方法



<br>[⬆ Back to top](#table-of-contents)

---
#### <a name='css-interviews'>CSS 相关：</a>

* 并列布局的方式

   ```
核心思路是怎么让block不自适应平铺为整行。触发bfc就可以了；比如绝对布局，float，inline-block等等
   ```


* 说一下CSS盒模型

    IE的怪异盒模型和标注浏览器的盒模型，然后可以通过box-sizing属性控制两种盒模型的变换。

* box-sizing的应用场景
* 弹性FLEX布局

        各种概念和属性能想到的说了一大堆，也扯到了Grid布局

* 一个div(200px*200px)在左侧，另一个div自适应在右侧
* 一个未知宽高元素怎么上下左右垂直居中

        flex弹性布局的实现，说了一下兼容性，扯到了postcss的一些东西，然后说了一下常规的兼容性比较好的实现。
        
        这里除了用flex,可以用绝对定位XY方向50%，然后translate自身XY-50%的偏移修正达到居中效果；如果不支持flex,css3的，就没法了只能想到通过js实现

* css常用布局

        这个在面试上市公司和创业公司问的比较多。大概我会回答一些盒模型包括怪异盒模型，定位布局，流布局，浮动布局，flex和grid布局，包括还有三栏布局中的圣杯和双飞翼。这些都还比较熟悉，所以问到都还知道。其中flex布局问的比较多，阿里的交叉面还有别的公司有问到子元素的一些属性。

* BFC

        这个滴滴面试的时候有问道（滴滴是破例让我加入流程中的，并且他们还招的技术栈是vue）一般在问清除浮动的时候会说一下

* 居中问题

        这个应该是老生常谈的东西了，电话面试的时候有两家问到

* session、cookie、sessionStorage、localStorage等区别

        这个也是上市公司和创业公司问到，大概就是说了下中间的区别，还有会简单说下cookie的属性，以及一些前端安全方面

* px/em/rem的区别

        滴滴电面的时候问的，这个我也知道，大概说了下相对于父元素还是文档来确定大小之类的。

* animation和transiton的相关属性

        这个我也就用了个大概，大概知道的简写位置和属性，当然，阿里一面还问到，为什么动画推荐用c3而不是js，这个问题当时并没有回答好，大概就是从性能上扯了扯，但是什么占用主线程以及浏览器对c3加速都没聊到。然后网易面试也问到了，然后我巴拉巴拉说了下后来查的相关东西。然后网易问了一句，浏览器怎么优化的动画。。。我。。。不知道。

* css编写注意事项

        因为这个在之前团队里面没有明文规定，所以我也没总结过，大概说了下自己编码中的方式，和浏览器查抄的过程。

* css和HTML 问的的确都不是很多，然后还有什么标签，meta和media啥的，大概也就介绍了下，问的都不是很深，我也没有回答的很深。。。因为我HTML CSS真的一般般。

* px,em,rem区别

* 用html,css实现一个div居中在窗口
* 用css实现，两行文本，间距10px,字体是14px,距顶端和底端15px,拒左边10px(原题是有图的，我就大致描述下吧)

* css 盒模型
* css布局，左边定宽右边自适应。两种方法，NEC上的用负边距消除宽度，用弹性布局。然后问我有没有第三种。。。

* css:两个块状元素上下的margin-top和margin-bottom会重叠。啥原因？怎么解决？（应该给父类元素添加BFC）

* Css实现动画效果
* Animation还有哪些其他属性。
* Css实现三列布局
* Css实现保持长宽比1:1

* Css实现两个自适应等宽元素中间空10个像素。

* 浮动的原理以及如何清除浮动

* rem是什么？em是什么？如果上一层就是根root了，em和rem等价么？
* 左右布局：左边定宽、右边自适应，不少于3种方法
* CSS3用过哪些新特性
* BFC、IFC
* 对栅格的理解
* （水平）居中有哪些实现方式
* 1像素边框问题


<br>[⬆ Back to top](#table-of-contents)

---
#### <a name='js-interviews'>JS 相关：</a>

* 0.1 + 0.2?

  0.1 + 0.2 != 0.3

    > 简单解释：

    首先这个不是JavaScript设计的问题，C、C++、Java、Python等遵循IEEE 754标准都必然会产生这个问题。
    JavaScript中的小数采用的是双精度（64位）表示，由三部分组成：符号(1位) + 指数(11位) + 尾数(52位)，
    浮点数二进制表示, 有以下两个原则:

    ```js
    整数部分对 2 取余然后逆序排列
    小数部分乘 2 取整数部分, 然后顺序排列
    ```

    在二进制中0.1表示为0.0001100110011001100110011001100110011001100110011001…..（后面全是 1001 循环）
    双精度浮点数只有52位有效数字，从第53位开始，就舍入了。这样就造成了“浮点数精度损失”问题。

    > 解决方案：

    使用内置的函数toPrecision或toFixed来保留一定的精度。

    ```js
  (0.1 + 0.2).toPrecision(10) == 0.3
  > true

  (0.1 + 0.2).toFixed(10) == 0.3
  > true
    ```

    > 延伸问题：

    1、单精度（32位）、双精度（64位）三部分组成位数分别是多少？
    2、二进制中整数、实数分别如何存储
    3、0.1 + 0.2 + 1.0 = 1.3，为什么？
    4、toPrecision、toFixed如何使用

    > [JavaScript 浮点数陷阱及解法](https://github.com/camsong/blog/issues/9)

  ​



* 普通函数与构造函数的区别？

* 原型链，对象，构造函数之间的一些联系

* 什么是函数柯里化？以及说一下JS的API有哪些应用到了函数柯里化的实现？

    ```
    这个我就说了一下函数柯里化一些了解，以及在函数式编程的应用，最后说了一下JS中bind函数和数组的reduce方法用到了函数柯里化。

    ```



* ES6的箭头函数this问题，以及拓展运算符。

    ```
    这一块主要是API和概念的问题，扯了一些规范以及严格模式下其他情况this指向问题。
    ```

    ​

* 写一个js的通用事件绑定函数

* 事件代理js实现

* JavaScript的事件

    ```
    阿里交叉面问到的js事件执行机制。我大概谈了下event loop，microtask，task queue。然后事件委托、捕获、冒泡、目标阶段大概谈了下，也顺道谈了下target和currentTarget。
    ```

    ​

* DOM事件的绑定的几种方式

* DOM事件中target和currentTarget的区别





* 你平时怎么解决跨域的。以及后续JSONP的原理和实现以及cors怎么设置

* 深拷贝的实现原理

    这个也还好，就是考虑的细节不是很周全，先是说了一种JSON.stringify和JSON.parse的实现，
    以及这种实现的缺点，主要就是非标准JSOn格式无法拷贝以及兼容性问题，然后问了我有么有用过IE8的一个什么JSON框架，
    我也不记得是什么了，因为我压根没听过，然后说了一下尾递归实现深拷贝的原理，还问了我typeof null是啥，这个当然是Object。。

    ​

* JS模块化Commonjs,UMD,CMD规范的了解，以及ES6的模块化跟其他几种的区别，以及出现的意义。

        这个也是说了一下自己的理解和认知，自己对模块化历史以及一些规范都有所涉猎，这一块也还凑合。        

*  白板写代码，用最简洁的代码实现数组去重。

        我写了两种实现方式：
        ES6实现：
        [...new Set([1,2,3,1,'a',1,'a'])]
       
        ES5实现：
        [1,2,3,1,'a',1,'a'].filter(function(ele,index,array){
            return index === array.indexOf(ele)
        })        

* JavaScript数据类型分哪些

        这是一个初创公司电面的问题，问的都非常基础，比如css画三角形之类的。别说，之前没准备，还真的忘记了border怎么设置出现直角三角形还是等腰三角形。当然，这个类型还是。。。没得说的

* JavaScript闭包

        这个应该问的都比较多，我之前总结过，以及常用的场景，也结合es6谈了下作用域和单例模式谈了下

* 前端跨域

        这个我基本都知道，之前有在掘金上总结过，这个很多公司又问道，包括阿里、网易一面。一般方式我都知道，具体展开会把CORS跨域，heade信息字段都说了一遍。也不难

* JavaScript继承

        这个我之前也总结过相关文章，网易的一面第二个面试官问了，我大概从原型继承、构造函数继承、组合继承、寄生组合继承优缺点和实现方式都说了下，还有es6的实现方式。一般这样就回答差不多了。后来网易还接着问，es5如何实现super关键字。看过babel转换后代码，但是这个。。真的忘记看了。大概说了下自己的实现思路，也就是装饰着模式。然后也就浑过这题了。

* JavaScript的节流和防抖

        滴滴一面问到了，阿里交叉面的时候聊业务场景的时候，也有问到。之前看过文章，自己项目中也用过，所以大概知道些

    ​

    ​

* ajax请求方式

         因该算是考察基础功吧，谈了下XMLHTTPRequest的过程，readyState的几种类型和代表的意思。以及浏览器兼容性的处理方案。

* js判断数据类型的方法

         貌似有两家公司问到，大概说了下typeof、instanceof、constructor、prototype等判断方式，注意事项以及优缺点。应该回答的还可以

* 函数声明和变量声明

         这个大概我也知道，还说了下es6的相关东西

* this指向的问题

         这个我也总结相关文章，大概说了下四种绑定规则，还说下new的执行过程以及箭头函数注意事项

     ​

* 面向对象的理解

        滴滴一面问的，大概说了下理解以及实现，从封装、继承和多态上说了下es5和es6的实现方式

    ​

* 对于js这门语言你认为怎么样


        哇，这个问题问的真的大。有看过《JavaScript语言精粹》，大概说了哪些弱类型语言通病，因为之前搞过Java，所以综合对比了下，同时也说了这些诟病怎么解决。应该会的面试官还是挺满意的

* es6相关知识点

        这个应该回答的都不是很深入，大概我都用过，promise的实现方式也研究过，但是不记得哪一家公司问到generator的怎么实现的。大概从iterator上简单说了自己的方案，然后说没看过。然后对于别的其实问的不是很多。基本套路就是es6了解过吗？用过哪些语法。后面具体可能会说下哪一个新特性的实现方式或者转向babel、webpack的相关面试。

* 原型链的问题，内部原理，继承的方式之类

* =＝和===的区别？＝＝怎么进行类型转换的，说说有哪几种情况？

* js有哪些重要的内容，既然你说你学的很好？

* 给Object扩展一个方法clone，实现深度克隆对象。　


* 给Date扩展 format 格式化方法，比如：new Date.format("yyyy-mm-dd hh:mm:ss")


* 编写each({}|[],function(key,value){})函数，要求里面的函数：(我解释下：each函数第一个是对象或者数组，第二个是回调函数)

  　　（1）this指向传入对象或数组
    　　（2）结果是true,则continue
    　　（3）结果是false,则break

* 用js实现position:absolute的效果

* js中有一个函数不用去访问原型还是考虑原型？（忘了原话是啥了。。大家自己脑补）为什么？

* 写出结果：

    ​```js
    function b(c){
        console.log(c);
        function c(){
            console.log("d");
        }
    }
    b(10);
    ​```

    ​

* 项目中弹框怎么做的？如果你自己写插件，你怎么实现？

* 实现一个函数，验证一个字符串，长度8位，至少包括其中三种或四种（数字，大写，小写，_）

* A->B->C,A看向B,B看向C，已知A已婚,C未婚，是否一定存在这样的关系：已婚直接看向未婚 （1）存在（2）不存在（3）不确定

* 冒泡和捕获，事件流哪三个阶段？除了冒泡和捕获，还有目标阶段。他们的先后顺序，先捕获，到了目标，再冒泡。（不要只记概念，要了解是干么用的）

* 实现事件代理。用jquery写了。要求写原生。子元素传递上来的应该是event.target或者e.srcElement。这个强调下IE和W3C的区别，建议写一个封装。

* 原型链。继承的两种方法。原型链继承和类继承。然后类继承只继承了实例属性，没有原型属性。原型链继承可以继承所有。然后用apply和call怎么继承原型链上的共享属性？通过空函数传值。新建一个空函数C。C实例化后C的实例属性就是空，然后用B的apply/call去继承C，相当于继承了C的实例属性。

* ajax。原生ajax的四个过程。实例化，open，send,onreadystatechange，然后是req,readyState和status。那么问题是通过哪个属性得到data？jquery里是success回调里面的形参。

      responseText和responseXML。后者是XML解析了的。

* 闭包。简单说一个闭包的应用。然后闭包的主要作用是什么：封装！

* js：写一个递归。就是每隔5秒调用一个自身，一共100次。

  ​

* less和sass用过么

* js的异步加载，promise的三种状态，ES7中的async用过么
* js原型链的继承
* 静态属性怎么继承
* MVVM是什么

  ​

* 如何保持登录状态

* 原生js添加class怎么添加，如果本身已经有class了，会不会覆盖，怎么保留？
* Ajax原生

* Jsonp的原理。怎么去读取一个script里面的数据。

* 如果页面初始载入的时候把ajax请求返回的数据存在localStorage里面，然后每次调用的时候去localStorage里面取数，是否可行。（直接说了不能保证数据的实时性，请求和实时性必然会有一方有所牺牲）


* 数组去除一个函数。用arr.splice。又问splice返回了什么？应该返回的是去除的元素。

* js异步的方法（promise，generator，async）

* 对象中key-value的value怎么再放一个对象。（直接放也可以，转成json字符串存数，读取再解析）

* 实现页面的局部刷新

* 图片懒加载

* 实现页面加载进度条

* 事件委托

* 实现extend函数

* 为什么会有跨域的问题以及解决方式

* jsonp原理、postMessage原理

* 实现拖拽功能，比如把5个兄弟节点中的最后一个节点拖拽到节点1和节点2之间

* 动画：setTimeout何时执行，requestAnimationFrame的优点

* 手写parseInt的实现：要求简单一些，把字符串型的数字转化为真正的数字即可，但不能使用JS原生的字符串转数字的API，比如Number()

* 编写分页器组件的时候，为了减少服务端查询次数，点击“下一页”怎样能确保还有数据可以加载（请求数据不会为空）？

* ES6新增了哪些特性，使用过哪些，也有当场看代码说输出结果的

* JS模块化的实践

* require.js的实现原理（如果使用过webpack，进一步会问，两者打包的异同及优缺点）

* promise的实现原理，进一步会问async、await是否使用过

* 实现gulp的功能

* 使用前端框架（angular/vue/react）带来哪些好处，相对于使用jQuery

* vue双向数据绑定的实现

* 单页应用，如何实现其路由功能

<br>[⬆ Back to top](#table-of-contents)

---
#### <a name='react-interviews'>React 相关：</a>

* react、vue原理、基本思想和区别

        于我来说最直观的是写法的区别，jsx与模板；同时debug中也存在差异。再有就是框架实现思想上的区别了，数据绑定与diff

1. <a name='react_2'>react怎么优化？</a> 
1. <a name='react_2'>react怎么优化？</a> 

2. <a name='react_3'>react的思想是什么？</a> 

        数据驱动balabala，举了一个之前封装轮播图的例子

3. 说一下Vue实现双向数据绑定的原理，以及vue.js和react.js异同点，如果让你选框架，你怎么怎么权衡这两个框架，分析一下。

        主要是发布订阅的设计模式，还有就是ES5的Object.defineProperty的getter和setter机制，然后顺便扯了一下Angular的脏检测，以及alvon.js最先用到这种方式。然后扯了一下vue.js和react.js异同点，权衡框架选择，调研分析之类，噼里啪啦说了一大堆。

4. 对redux怎么看？

    [从时间旅行的乌托邦，看状态管理的设计误区](https://juejin.im/post/5a37075051882527a13d9418)


1. webpack的入口文件怎么配置，多个入口怎么分割？
2. 有没有自己写过webpack的loader,他的原理以及啥的
3. 有没有去研究webpack的一些原理和机制，怎么实现的。
4. webpack配置用到webpack.optimize.UglifyJsPlugin这个插件，有没有觉得压缩速度很慢，有什么办法提升速度

        一个想到是缓存原理，压缩只重新压缩改变的，还有就是减少冗余的代码，压缩只用于生产阶段，然后面试官问还有呢？
        我就说，还可以从硬件上提升，可以得到质的飞跃，比如换台I9处理器的电脑。。。。


1. node写的多入口怎么配置？

2. react部分必考的肯定有生命周期

        这里我大概说了下每一个生命周期，es5、es6的两种书写方式，以及每一个生命周期我们一般用来做些什么操作

3. setState是异步的还是同步的

        阿里一面的时候问到的，我大概说了两种setState设置方式，以及表现为同步的那种设置方式展开说了下

4. 子组件和父组件componentDidMount哪一个先执行

        这个也大概从生命周期分期了下。话说我到现在还不知道自己回答的对不对，技友们，你们觉得呢？

5. redux的一般流程

        这个我比较熟悉，一带说了下所有的技术栈，以及react-redux的原理、高阶组件、以及redux-saga的实现原理。（逮住会的，都啪啪啪说出来，自己掌握点节奏。但是要适当，比如问到我es6，我啦啦啦说了一二十分钟，一般面试官会有点不耐烦。所以视情况而定）

6. 如何设计一些组件，原则是什么，你写过什么自豪或者眼前一亮的组件

        阿里一面以及一家上市公司也闻到过这类似的问题，大概从组合、复用、重复、测试、维护等方面说了下

7. a组件在b组件内，c组件在a组件内，如何让他渲染出来，a组件和c组件同级

        阿里面试的时候问到的问题，想了一会，说了不会。后来查了下，大概可以通过react16中返回不带包裹元素的组件来实现。因为和阿里一面面试官后来聊得比较开心，加了微信，还斗胆为了下他，他说还有曲线救国的实现方式

8. react组件的优化

        从pureRenderMixin、ShouldComponentUpdate等方面说了下，以及组件的设计和木偶组建的函数编写方式说了下

9. react组件的通信

        这个大搞几种方式也都说了下，prop，context（顺道扯了react-redux的context实现方式）、redux甚至广播都说了一遍

10. react 的virtual dom和diff算法的实现方式

        阿里交叉面问的，直接说实现方式源码没有看过，但是大概说了下原理和步骤，具体代码怎么写的不知道。

11. MVC、MVVM了解么，数据双向绑定和单向绑定实现方式

         滴滴一面问的，实现方式还是说了不知道，然后说了下MVC和MVVM的设计模式，因为之前用过angular1，大概就说下脏检查步骤以及view-model的作用

12. react-router实现方式，单页面应用相关东西

         大概说了下react-router的一般使用方式，以及没有使用react-router的时候如何利用h5 的history API来实现路由跳转等。

13. react的ssr了解么？大概怎么实现

         阿里的一面问的，在github上写过demo，但是没有用过别的第三方库，这里我就大概说了下webpack的配置项以及大概的实现思路和注意事项。

14. react大概也就问了这么写，别的就是具体的业务场景改怎么写代码怎么分析，比较不大众，这里我就我细说了。其实也就考验你的项目经验吧。当然，还有一些react Native的面试题，比如常用组件，和原生如何通信之类的，这些就有赞问的多，但是因为RN玩的不是很透彻，所以对于交互原理都不是很明白。


你对组件的理解

  组件的html怎么进行管理

<br>[⬆ Back to top](#table-of-contents)

---
#### <a name='build-interviews'>构建工具：</a>

1. 项目用到了Babel的一个插件：transform-runtime以及stage-2，说一下他们的作用

        ES的一些API，比如generator啥的默认不转换，只转换语法，需要这个来转换，然后说profill啥的，扯了一下stage-1，stage-2，stage-3，


1. babel把ES6转成ES5或者ES3之类的原理是什么，有没有去研究。

2. 编写过webpack的扩展嘛，Plugin或者loader

        这个我看过一本书《深入浅出webpack》，所以基本都能回答上来。包括原理和编写loader、Plugin注意事项。当然，我自己没有写过。。。《深入浅出webpack》

3. babel 问的不多，但是我也准备了，包括每一个包的作用和内部转换过程，不记得哪家公司问了，大概我也就说了下babel转换的过程。

4.  commonJS和AMD。

<br>[⬆ Back to top](#table-of-contents)

---
#### <a name='regular-interviews'>正则 相关：</a>

1. 编写验证函数：验证类似username@163.com,username@abc.com,username@adfs.com（我就记得163,其他的我瞎编的，这道题考正则，还有考查字符串或者正则的方法）

2. ​ 3.正则表达式判断url（只写了判断是否是http或者https开头）

     4.怎么去除字符串前后的空格（正则匹配^\s和\s$并且替代，Jquery的$.trim，string.trim()）

---

#### <a name='app-interviews'>移动端 相关：</a>

1. <a name='app_1'>移动端做过什么优化么？</a>
         
        直出、域名收敛
        
        域名收敛？为什么要收敛？”“因为dns解析慢啊？”“那和pc端有什么区别，
        pc端域名不是发散来提高并发数么？”
        
        我心里一想是啊，其实浏览器pc和m没啥区别那为啥一个发散一个收敛，
        或者说发散我们都知道克服pc浏览器的并发限制。那m端？我当时有点迷没说上来就过了，
        回来又百度了一下感觉上其实就是m端网速慢dns太耗时。。我没反应过来还有网速的事情

2. <a name='app_2'>js与native怎么交互？</a>
         
        嗯虽然我没做过，但是我了解过应该是native定义一套协议，js使用该协议发请求，
        native拦截解析并返回js的所需balabala


1. <a name='app_3'>缓存策略都有哪些，包括native？</a>
         
        基于node的微小服务——细说缓存与304
        https://github.com/Aaaaaaaty/Blog/issues/8


1. m端与pc在html5的新特性上有哪些是不一样的？
         
        基于node的微小服务——细说缓存与304
        https://github.com/Aaaaaaaty/Blog/issues/8

2. 分析一下移动端日历，PC端日历以及桌面日历的一些不同和需要注意的地方。

        这个我能想到的大致都说了一遍，不同的场景交互和细节以及功能都有所偏差，以及功能的侧重都可能不同。


<br>[⬆ Back to top](#table-of-contents)

---
#### <a name='node-interviews'>Node 相关：</a>


<br>[⬆ Back to top](#table-of-contents)

---
#### <a name='http-interviews'>Http 相关：</a>

1. 有没有了解http2.0,websocket,https，说一下你的理解以及你所了解的特性

2. 了解http协议。说一下200和304的理解和区别
         
        协商缓存和强制缓存的区别，流程，还有一些细节，提到了expires,Cache-Control,If-none-match,Etag,last-Modified的匹配和特征

3. 业务场景：比如说百度的一个服务不想让阿里使用，如果识别到是阿里的请求，然后跳转到404或者拒绝服务之类的？

        主要是考察http协议头Referer，然后怎么判断是阿里的ip或者啥的，我也不太清楚。

4. http三次握手后拿到HTML，浏览器怎么加载

        阿里的一面问的问题，这个我之前在环球做过相关技术分享，所以大概都知道，从过程到不同内核差异（差异部分简单提了下）说了下dom、CSSDom以及paint等过程。然后面试官接着问如何防止repaint和reflow。大概从引起repaint和reflow等操作上说了下避免。网易的一面也问到了repaint和reflow。

5. 前端优化一般都做哪些

        这个之前总结过，雅虎的军规啥的。以及首屏优化。然后面试跟了些预加载http head信息相关的，这个没怎么看，回答的不是很好

6. 浏览器缓存

        这个我也做了相关的技术分享，也看过《图解http》大概从http 1.0和1.1都说了下，其中有一家公司问到200 From cache和200 ok区别（有赞），这个还真的忽略了，后来查了下大概了解了。其实也就是强缓存

7. http常见状态码

        从100~500 大概也说了十几种。其实也就是《图解http》中的东西，当时还刻意背了下

8. http2.0相关

        网易一面问题，说了下2.0的采用二进制格式、多路复用、报文头压缩、服务器主动推送还扯了websocket的相关内容WebSocket：5分钟从入门到精通。然后网易接着问，报文头怎么压缩的？我。。。？？不知道。。。然后大概也问了下https的TLS/SSL,之前看过漫画的htts的相关东西，大概说了下漫画里面的故事~

9. post、get区别

        这个回答的不是很好，也是一个大厂问的题目，我回答的都是表象。后来我看了一篇文章，大概知道了。99%的人都理解错了HTTP中GET与POST的区别

    3.cookie和session有什么区别。

     4.网络分层结构。4层，应用层，传输层，网络层和数据链路层。依次是http等应用，TCP/UDP，IP和物理连接。然后又追问了一下ssl在哪一层。ssl是socket，是单独的一层。如果要算应该算传输层。

   Cookie 是否会被覆盖，localStorage是否会被覆盖。

10.  304是什么意思？有没有方法不请求不经过服务器直接使用缓存。（强缓存和协商缓存的命中和管理）

   http请求头有哪些字段

    Cookie跨域请求能不能带上

11.  Get和post的区别
     Post一个file的时候file放在哪的？

<br>[⬆ Back to top](#table-of-contents)



---
#### <a name='performance-interviews'>性能优化：</a>


<br>[⬆ Back to top](#table-of-contents)

---

#### <a name='arithmetic-interviews'>算法数据结构 相关：</a>



1. 二分查找的时间复杂度怎么求，是多少

        。。。排序的还算清楚一点，查找真的不知所措，没回答上来，也没猜，意义不大，不会就是不会。

2. XSS是什么，攻击原理，怎么预防。
         
        这个很简单，跨站脚本攻击XSS(cross site scripting)，攻击类型主要有两种：反射型和存储型，简单说了一下如何防御：
        
        ①转义
        ②DOM解析白名单
        ③第三方库
        ④CSP
        
        自己对web安全这块系统学习过，前前后后大约了解了很多，对于XSS,CSRF,点击劫持，Cookie安全，HTTP窃听篡改，密码安全，SQL注入，社会工程学都有一定了解，所以这个自然也不在话下。

3. 线性顺序存储结构和链式存储结构有什么区别？以及优缺点。

        我是类比JS数组和对象来回答的，反正还算凑合吧，自己都数据结构这块多少还是有些印象，所以入了前端，对数据结构和算法确实一直淡忘了。

  单向链表怎么查找有没有环？

<br>[⬆ Back to top](#table-of-contents)

---

#### <a name='open-interviews'>开放性 相关：</a>

1. git大型项目的团队合作，以及持续集成啥的
         
        这里我就说了一下自己了解的git flow方面的东西，因为没有实战经验，所以我就选择性说明了这一块的不熟练，然后面试官也没细问。

2. 我看你也写博客，说一下草稿的交互细节以及实现原理。

        这一款就按照自己用过简书或者掘金，SG这类草稿的体验，详细说了一下，这个开放性问题，说到点基本就OK。

3. 说一下你项目中用到的技术栈，以及觉得得意和出色的点，以及让你头疼的点，怎么解决的

4. 说一下项目中觉得可以改进的地方以及做的很优秀的地方？

5. 一个业务场景，面对产品不断迭代，以及需求的变动该怎么应对，具体技术方案实现。

        具体业务场景，我就不一一描述，Boss在白板上画了一个大致的模块图，然后做了一些需求描述。
        然后需求一层一层的改变，然后往下挖，主要是考察应对产品能力，以及对代码的可维护性和可拓展性这些考察，开放性问题，我觉得还考察一些沟通交流方面的能力，因为有些地方面试官故意说得很含糊，反正就是一个综合能力，以及对产品的理解，中间谈到怎么实现，也问到了一些具体的点，记得问到的有一下几个。
        
        ① 怎么获取一个元素到视图顶部的距离。
        ② getBoundingClientRect获取的top和offsetTop获取的top区别
        ③事件委托

6. 怎么实现草稿，多终端同步，以及冲突问题？

   ```
    这个回答的不算好，本来也想到类比git的处理方式，但是说的时候往另外一个方面说了，导致与面试官想要的结果不一样。
   ```

7. 用过网易的哪些产品？优势劣势？

8. 职业规划？

9. 为什么想来网易？

10. 产品经理提需求，你怎么处理的？

11. 怎么证明自己善于沟通啊之类的？

12. 问我做了那么多项目，有没有自己的归纳总结。

13. 工程怎么进行文件管理

14. less和sass掌握程度

15. 平时是怎么学习的。

16.  怎么测试的？
     会自动化测试么？

      你觉得优势在哪？
     你觉得你什么技术最擅长？
     你平时有没有什么技术的沉淀啊

17. ​

    ​




​        　

<br>[⬆ Back to top](#table-of-contents)

