# study-in-com
Js在使用for in遍历对象的时候会讲对象的键1234变成字符串

const { status } = (this.refundDetail = data);

先赋值然后再从数据中结构status出来

封装请求接口的时候 由于axios本来就是使用promise来进行封装 故此再进行二次封装的时候，使用函数将接口请求的函数return 出去  再使用async await来得到结果

项目中的数据都是根据权限来控制显示的

后台管理系统中 
H5页面中通过使用cookie的方式将token给到后端进行校验用户权限然后再返回对应人员的数据 获取到url地址栏的token之后setCookie 然后每次请求都会带上这个token值 
Vue进入路由的时候将token setcookie 路由完全执行完成将url进行替换 把token去掉window.location.hash = window.location.hash.replace(/token=[^&]*&?/)

Js继承 组合继承 寄生组合继承
1定义函数，在函数的原型上面定义一些方法
2
Promise当使用promise使用all方法的时候 我们需要做错误异常处理的时候我们可以自己在map定义prommise的时候 自定义出需要return的数据
Promise 封装的时候会将你的函数返回值再次封装promise所以return 出具体值的时候你.then也是可以获取到值的
## Token 
一般是后台在返回的时候设置cookie，然后前端获取到cookie然后设置到请求头中

一般单点登录以后 前端是可以使用document。cookie来读取cookie的 可以设置在请求头的Authorization字段中以Bearer
Token  将token带过来之后 在路由加载完成在讲地址栏中的token进行清除 location.hash
开头
## 链表结构
单链表 每个单链表中的元素都可以看作是一个对象 每个对象上都存在一个next 的属性来记录下一个节点的信息。
## webpack
happypack 是开启多个子进程来进行文件解析，处理完成之后将结果返回给主进程，然后在执行后续操作。是loader

HappyThreadPool定义多个进程公用一个线程池

rimraf插件
在打包之前先将上次打包的文件进行删除

process.stdout终端输出文本

semver 比较提取版本号

插件：
copy-webpack-plugin 复制文件到指定目录下

HtmlWebpackPlugin指定打包模版

ExtractTextWebpackPlugin 将css在打包的文件中抽离出来

OptimizeCSSPlugin将css进行压缩

uglifyjs-webpack-plugin对js进行压缩

Webpack的原理是将提供一个apply的方法 触发该插件的时候会被注入complie实例 再指定webpack的钩子 然后在调用webpack提供的回调将处理的结果返回
## Ant-design 
table 子表格嵌套自定义点击展开

设置expandIconColumnIndex移除+号

Form中设置初始值 在组件不刷新的情况下 改变初始值页面显示是不会刷新的。在修改值之后使用form的来进行设置值即可
## git 
Git 发版的步骤

1. 首先是在远程的tag上创建一个分支 然后切换过去 eg: git branch release/v1.73.0 v1.72.0

#### git branch 本地新建分支名 v1.72.0（远程tag分支名）

2. 然后在分支上cherrypick自己需要的代码hash  eg: git cherry-pick 0396bccb8829cd9efe4b0a17d19d642bb2e4ffa4

3. 然后推到远程的分支上  add commit pull push 

4. 代码库操作：推到远程分支之后，会提示你需要自己创建merge 然后自己创建一个merge添加一些修改的点自动生成一个mr,再通过mr给对应的人员进行审核代码，然后再合到master  然后再出发cicd

5. Cicd 从release分之合过来的代码进行区分 发布到不同的服务器

fflow 实际是做了一个前置，自己给你创建了一个merge (实则帮你创建了一个mr)

因为正常的流程应该是推送到远程之后，自己需要通过提示创建mr 然后就会有提示要进行代码审核

如果此时线上的代码有问题 此时应该切换到master分支上 提交自己的fix 然后再自己的分支上将这次的代码cherrypick过去 

## git use tips
git在使用的时候是可以将暂时写的使用git stash 然后进行切换分支开发其他功能并将其他推送到远程，本地再使用git stash pop将缓存的内容取出来

git也是支持多次commit就是刚刚commit了 但是又有点改动又可以继续commit

git clone的时候是可以在指定文件夹的外层拉去的 拉取成功之后 文件夹中就会多出一个项目的文件夹
## 抓包工具 proxyman 使用步骤
1 下载安装

2  安卓手机需要安装证书 用手机上下载的chrome打开 http://proxy.man/ssl 下载一个pem的证书进行安装 

（也可以在抓包工具上将证书进行导出，存在手机上，然后进行安装，注意有的手机是需要在设置里面才能进行安装的）

3 在使用抓包的时候 我们在手机端链接wifi的时候设置代理 然后设置和电脑wifi相同ip和端口 就可进行抓包（手机和电脑连接同一个wifi）

4 如果抓包时手机访问不了可以检查是否是认证证书没有安装成功
## H5页面手机上联调
手机和电脑同时链接同一个wifi

手机访问电脑的wifi 的ip即可进行查看

（注意启动本地前端项目的ip地址应该是0.0.0.0）

注意点1：连接的wifi不能设置代理，不然访问不了；需要设置wifi的代理是在使用手机抓包的时候才用到

注意点2: 在微信上进行抓包的时候，网络设置代理之后如果微信访问不了，可以将微信后台杀死，重新启动。
## css
transition  左右一组样式变化的动作

transform 是某个样式变形的css

响应式布局中需要知道自己定义的高度才能很好的定位好自己的元素 

如果自己的样式中使用padding margin把自身的元素增加 那样子来计算定位会有些许的偏差

先定义父元素整体的height 在根据这个height来定位 这样无论你布局放大缩小 都没有问题

window.pageXOffset是滚动条滚动出去的距离 offsetTop是子元素距离父元素的距离

浮动的元素 可以使用position：relative来进行定位居中

currentColor使用在伪类元素上 根据父元素的颜色来自动变化颜色

一般的背景图png 都可以使用tinypng.com进行压缩

H5页面宽度尽量不要给定值  避免屏幕小的时候 文字内容挤出

场景

滚动组件功能开发

使用transform：translate3d(0, y ,0) 结合transition:600ms

每次滚动的高度应该是列表中单个的高度 如果页面是使用vw 则用vw

html结构div -> div -> list<div>

无限滚动（原理）
animation可以实现  定时器也可以实现动态的修改数据，将第一条数据放到最后，将第一条数据去除

1.所有子元素都采用定位根据left值来进行布局

2.所有子元素都采用transition来进行运动

3.当第一个元素运动消失之后，计算出最后一个元素的位置 然后给第一个元素添加left值跑到最后一个子元素后面 

也可以使用top 结合transition 

列表最后进行无缝衔接的时候 使用settimeout处理
## vue 
当组件没有等到数据加载完成就渲染出来，则需要使用watch来监听数据的变化

当数据是属于异步请求回来的时候我们需要使用watch来监听数据的变化

数组中进行数据的push 是可以监听其变化的

什么时候需要使用watch来监听数据 当页面中的数据依赖某个数据去做处理的时候我们需要使用watch

v-if只是根据你的数据来现实隐藏

Params 要结合name来传递参数 params是路由：id query是拼接数据

使用history可以用来监听手机端的返回

使用history.pushState 可以来做手机端返回处理

进入本页面进行pushState的一次 然后监听pushState事件 手机端返回一次会用掉一次历史记录

需求 根据状态来显示三个不同状态的页面

由于报错之后 回来还能将之前编辑的内容展示出来前端使用keepalive来包裹来包裹component is来来回切换的三个组件

三个组件 一个是成功后的组件 一个是失败后的组件 一个是申请的界面

当申请失败会切换到失败的界面 申请成功会切换到成功的界面 

需求 申请成功 返回会切换到主页面 但是申请失败返回会切换到申请的页面并且之前写的内容存在

手机上的回退是回退一个历史栈

Vue 2.0 如果你想做一个动画 必须要使用v-show。不能使用v-if 如果一个组件刚开始已经渲染 只是用display来进行显示与隐藏。当你再次使用变量来显示出来就会存在动画效果 反正就是必须先存在才能慢慢的来显示

## 项目功能点

1.图片中添加文本信息 使用canvas

第一步：使用canvas + img 将https上的图片进行下载下来 

第二步：使用canvas fillText方法将一些数据添加到图片中

第三步：将生成好的canvas资源转换成blob的格式

第四步：结合img将生成的图片进行copy

知道原始图片宽高就能将数据写入图片

2.模拟用户退出的时候收集用户输入的数据

Hash history 原理使用history里面的replaceState pushState 修改与添加历史栈 再监听popState事件。获取到对应路由之后再去渲染render对应的组件

3.list列表滚动 先将数据列表渲染出来 然后使用transform属性中的translate来改变滚动的距离方向就ok了

window.location.replace替换当前文档内容

offsetTop是当前元素距离上一层元素的高度

父元素监听某个子元素的是否在可视区域进行显示隐藏 抽象成class。使用class来对dom元素来进行监听scroll事件

New Image 来加载图片 加载完成之后显示图片 没加载完成则显示默认图片

getBoundingClientRect获取的是元素在页面窗口的位置

文件上传input formData 文件选择后会存在一个File类型的原始数据类型 可以转换成base64 blob

项目中使用cors跨域时需要注意几点

1。前端本地联调的时候，如果需要设置cookie给到后端，按道理来说跨域时 cookie是不会自动传递给后端的 需要在axios 请求头中添加withCredentials

2。后端使用cors跨域的时候必须要设置允许跨域的域 这样才能成功

后端设置允许跨域的设置 意思是指 在这个域名下请求我后端的接口是被允许的

后端设置cookie的过程

1. 前端请求后端的接口 后端会指定cookie 并且会指定一个域名

2. 前端再开一个网页去请求后端设置了cookie的域名时，会自动将刚才获取到的cookie设置上去 当然你重新打开网页的域名后端要支持允许你跨域

编辑器功能

monaco-editor 可以对代码进行展示编辑 满足编辑器的系列功能

## react
问题点

useCallback 将需要的函数进行一个缓存的效果，主要是为了防止每次都会重复渲染组件，如果某个组件的数据量比较大，渲染比较的慢的时候就需要使用到

useEffect第二个参数为[]为空数组

useHistory

useMemo

useState 是使用异步的形式来完成

useEffect会在render之后再执行 子组件useEffect执行之后父组件才执行

useEffect执行之后render会再次执行

useEffect是依次执行

useContext(MyContext)创建一个上下文然后可以进行多个子组件同时接收一样的数据

不管传递的子组件有没有接受该值 都会重新渲染 或者层级嵌套过深

memo是

cloneElement

先创建好组件 然后 组件内部使用变量来控制显示隐藏 ref来获取组件内部变量

路由配置
  HashRouter,
  Redirect,
  Route,
  Switch,
  withRouter,
从react-router-dom引入
路由route和需要重定向的Redirect都需要放在route中
React.Suspense
React.lazy通过懒加载添加进来的路由组件 可以使用React.Suspense来优化交互 在加载前做些什么，例如加载前使用loading
结构：

<HashRouter>

	<withRouter>

		<Switch>

			<Redirect></Redirect>

			<Route></Route>

		</Switch>

	</withRouter>

</HashRouter>

useRef使用ref来操作子组件方法

setImmediate只执行一次 定时器


通过异步请求回来的数据 在点击之后获取不到请求回来的数据

原因是使用hooks setState来返回的第一个参数和第二个参数都变化了 生成了一个新的数据 点击的时候还是获取的原来定义的数据

解决办法1
const goodsListRef = React.useRef(goodsList);

  useEffect(() => {

    goodsListRef.current = goodsList;

  }, [goodsList]) 

在列表中需要进行切换 就需要在list列表中在点击之后再修改某条数据中的值 达到切换的效果

React 里面是一个花括号里面可以使用数据类型 eg:{ aaa } { {a:n} }

React 里面更新对象的时候可以申明空对象 然后使用解构来赋值 然后替换。或者使用Object.assgin({},{})

react setState数据的时候页面刷新 思考

当页面中需要使用文字超出显示tooltip没超出不显示时 如果渲染的是一个数组。可以在每个子数据中添加一个数据来做处理。也可以封装成一个组件 所以组件都有自己的状态控制

useEffect传递空数组时，只会执行一次  例如父组件中循环渲染子组件 子组件中使用useEffect传递空数组，则父组件再次更改子数据则不会执行useEffect

React中想要在操作完数据之后操作dom元素 例如添加一个数据 在数据渲染完成之后，滚动页面到最底部，在set完数据之后再去操作dom  需要使用useEffect来实现  写一个useEffect添加一个参数为条件 来控制
useEffects是在render完成之后再执行的 这个是顺序

ref 绑定的原理实则是绑定一个函数 然后会讲该dom结构传递给该函数作为参数返回;

useState原理 使用一个数组。定义一个初始index 使用多次该hooks时创建多个数据放入数组中存起来 再进行修改的时候根据创建时的index来进行修改

Hooks相当于一个函数式组件

React  定义变量需要定义到外层 不然使用到变量依赖。虽然没有变 但是组件会刷新。useEffect会一直刷新

React 组件中嵌套route 将route上定义path则可以通过路由来进行切换
￼

useMemo是依赖项变化就重新计算  依赖项不变化则返回缓存的值  此hooks是在render之前执行

useCallback是依赖项变化重新执行某个函数

useReducer是指定某个纯函数，给更新的数据加一个管道函数的特效

useContext 可以实现子孙组件的值传递

useImperativeHandle在子组件中使用时可以向父组件中传递方法，每次render之后都会被执行，如果有参数依赖，每次参数变化都能获取到最新的数据，如果依赖是空数组则不会获取到最新的数据

在一次函数中多次修改某个数据 页面不会多次渲染。只会渲染一次， 并且如果你修改的数据没有变页面也不会重新渲染

React.FC是将react的组件定义为函数组件 是function component的缩写

React.component是将react的组件定义为class组件 

## Gitlab cicd流程

一，使用安装gitlab

二，在gitlab上注册runner

三，在项目文件中添加gitlab.ci.yml文件

四，当触发文件的方式与yml文件中定的方式一致时，就会触发流水线cicd一套流程

一套流程中会有多个stage

每个stage中又含有多个job

在每个job中可以指定分支的名字以及指定用怎样的runner

Docker的使用是可以构建一个运行的镜像，在执行完构建stage之后 利用docker 开启nigix部署资源


多分支构建这里指的是项目中的多个分支都需要触发cicd 

构建的思路一： 可以利用docter来创建不同的docker部署环境

构建的思路二： 可以在yml文件中配置多个job的然后指定不同的分支

Runner来执行yml的文件 还是执行yml的文件指定runner 制定runner之后为什么又感觉是执行yml里面的配置 到底是谁依赖谁

## Git rebase merge 的区别

Rebase和merge都是属于合并分支，举个例子说明两者的区别，

同时开发的两个人，都checkout分支到新分支开发，开发完成之后，一个人提交commit 2，3，4.到master另一个人提交commit 5，6到master。如果使用rebase，就能够将两者的代码都记录在master上，形成，1，2，3，4，5，6.如果使用的是merge的话就只能形成1，2

会将2，3，4，5，6合并形成新的commit提交。

## typeScript

枚举 

	eg：enum Color {Red, Green, Blue}

	let c: Color = Color.Green;  // 1

函数

在某个类型中定义属性为函数

interface typeFun {

  handleFun: (params:any) => void;
	
}

类型断言

As 断言将某个类型断言为后面的类型

关键字
1.typeof是找到当前typeof类型的原始爸爸的类型

2.keyof 是将一个类型的键展开成一个组合类型 结合omit可以将一个类型中的键全部去掉 

注意点，如果某个键是某个对象的属性，则可以让这个属性 keyof 那个对象的interface

3.extends是在某个类型中必须是某个类型对像中的某个键

4.type定义的类型是属于类型的别名
	
注意点：如果某个对象的键是通过枚举[enum.enter]定义，那么这个对象的interface也要使用[enum.enter]来进行定义

工具泛型
Record
eg: type newType  = Record<'a' | 'b' | 'c', string> 等价于 newType = { 	a: string,
	b: string,
	c: string }

Partial 将类型接口变成可选

Required 将类型接口变成必须与partial相对的

Readonly 将一个类型的所有属性都变成只读的

Exclude T是U的子类型，那么就返回nerver,否则就返回T

type Exclude<T, U> = T extends U ? never : T

Extract T是U的子类型，那么就返回nerver,否则就返回T

Extract<T, U> = T extends U ? T : never;

Pick从一个复合类型中，取出几个想要的类型的组合

Omit 从一个复合类型中，剔除几个属性，剩下的组成一个新的类型

## 本地嵌套h5页面在手机上进行查看

手机能访问pc端的界面需要连接同一个wifi 

本地两个项目进行嵌套。都起服务，用起服务的地址进行嵌套即可

## taro 
启动小程序项目的时候要确定taro的脚手架的版本
	
## 微信小程序
1 开发的时候可以关闭域名校验。

2 小程序中弹出用户信息是没有权限获取用户数据则弹出，有权限不会弹出，直接获取

3 h5中跳转到小程序可以直接使用location.href进行跳转

## animation


## promise
用法1：

handlePromise() {

   let rs;

   let rj;

   const promise = new Promise((resolve, reject) => {

	(rs = resolve), (rj = reject);

   });

   function next() {

	axios.post("/api/payCharge").then(() => {

	  rs("11111111111111111");

   }).catch(() => {

	  promise.timeout = setTimeout(next, 1000);

   })

}

next();

return promise;

},

handlePromise().then((res) => {

  console.log(res)

})
	
注释: 在请求超时时候会给promise添加timeout方法并且去执行timeout方法，如果在第二次执行next获取到了数据 则在.then是可以获取到数据 进行了一个超时兜底；

## 公众号开发在微信开发者工具上访问也是需要在微信后台配置权限的和小程序一样 都需要权限

需求：fn(a,b)(c) fn(a)(b)(c) fn(a,b,c) 都能输出6

实现：

1.相比较参数个数都是3个 输出6是三个参数的和 也就是说

function add(a,b,c) {

    return a + b + c

}

2.参数不够3个时，return出一个函数进行参数的接受， 如果参数够了3个，则使用add函数进行求和


function currying(fn, length){
  let length = length || fn.length // 第一次不用传递length 直接取fn的参数个数 需要注意的是 fn的参数不能设置默认值

  //将函数add丢进去return出去一个函数来进行参数的收集 

  return function(...args) {

  //此时的args则是接受的参数的个数

    args.length >= length ? fn.apply(this, args) : currying(fn.bind(this, ...args), length - args.length)

  }

}

难易理解点: 在currying中 为什么使用fn.bind() 不直接使用 fn 是为了使用bind来将上一次传递的参数进行收集；不然第一次传递两个参数， 第二次传递一个参数，调用fn是需要三个形参的，第二次却只有一个则报错

bind函数也称为延迟调用函数，里面实现的原理相当于给修改this指向的对象添加一个新的函数，也就是在bind函数中return出一个新的函数，bind会将第一次传递进行的参数进行收集。

bind也是使用了颗粒化将参数进行递归传递，如果一个函数，如下

function foo(a,b){

  console.log(a,b);

}

let a = foo.bind(this, 1);

a(2);

结果如下：

console.log(1, 2); // 原因就是bind会参数利用科理化来进行收集，并返回新的函数


fn = currying(add)

此时就完成实现

找出变化的点，刚开始 需要比较的参数个数是3 如果你传递进来的是3个 就直接调用add函数 
如果第一次传递的是两个参数，则仍需要传递出去一个函数来进行参数接收 。则下次比较的参数就应该是1个 原先的三个减去传进来的两个 则是1个 如果再次传进来一个参数 就应该调用fn函数

## cookie的携带方式

请求：本地起服务在http:local.school.com 浏览器打开之后向http:test.school.com上进行请求；

（此时是在local服务器来请求test上的服务，所以有跨域）下面就是解决跨域的方法

此时需要在请求http:test.school.com上携带上cookie;

第一步： 在http:local.school.com域名下设置cookie

第二步：
	
此时应该区分请求的方式：

1.fetch的方式，在该请求方式下请求http:test.school.com是不会设置cookie的 即使是同域情况下也不会携带。则此时应该设置with-credentials: true才能在请求的时候将当前local的cookie携带

2.axios ajax 的方式，在同域的情况下，会自动携带cookie。在不同域也就是上述这种场景。不会自己带上，则需要设置with-credentials: true，才能在请求的时候携带上local本地的域名

区分：当线上的域名与请求的域名在相同域名下，设置cookie如果用的是axios ajax的方式请求则都能携带上cookie，如果是不同域则可以设置with-credentials: true才能在请求的时候携带上cookie

所以我们在本地起服务与线上环境进行联调的时候，如果本地需要设置cookie则是在本地的域名下进行设置cookie，不应该是在线上的域名下设置cookie。

## 栈 堆 与 内存之间的联系

执行上下文

1.创建阶段：词法环境和变量环境 区别在于词法环境申明的是const let function 变量环境申明的是var

2.执行阶段

闭包是把变量存储到了内存中，所以能访问到该变量；闭包要谨慎，不合理会导致内存溢出；

栈和堆都是用来存储不同的数据类型。最终是在内存中存储

[].shift.call(arguments)是将arguments伪数组，调用数组的shift方法，截取伪数组中的第一个参数， shift会修改到原数组，所以此时的arguments就是去除第一项的参数集合

中间件是一个数据共享池，也类似一个拦截器，所有的数据改动都会到中间件中。

## 正则

let reg = /token=(\w*)/g

let str = token=wqeqweqweqweqwe&cookie=qweqwewsadadwqezc&token=uiiuwqeqwey

当使用正则test的方法时，如果正则使用的是全局g 

则每使用一次reg.test(str)正则的lastindex都会更新一次 当匹配两次时就会出现错误

第一次

reg.test(str) -------- true

第二次

reg.test(str) -------- true

第三次

reg.test(str) -------- false

## promise原理
new promise的时候给构造函数添加一个函数参数，在构造函数中将函数进行执行，执行时给函数添加一个函数（此函数为resolve）形参，然后在函数（此函数为new promise传入的函数）执行的时候再去执行resolve的时候，首先会将值保存起来。将状态变换成fulfilled。此时会去判断队列（此队列是收集then时传入的函数）中是否存在函数，如果存在就循环调用，并将值作为函数参数进行传递。then的时候会将函数传入，构造函数会进行利用队列进行收集。

问题：在new promise执行传入的函数时，队列中没有then传入的函数。 此时的解决办法是，在then里面会去进行判断，当status仍然是pending的时候，代表resolve还没有执行（因为执行了状态就会变化）。此时就需要将then传入的函数收集起来，在resolve的时候就会调用函数，并将值作为形参传递。如果status改变成了fulfilled就代表resolve已经执行了，value值已经收集起来了，此时直接调用then传入的函数，并将value作为形参传入即可。（所以常说，promise的状态一旦改变就不会在发生变化）


class Promise {

    callbacks = [];

    state = 'pending';//增加状态

    value = null;//保存结果

    constructor(fn) {

        fn(this._resolve.bind(this));

    }

    then(onFulfilled) {

        if (this.state === 'pending') {//在resolve之前，跟之前逻辑一样，添加到callbacks中

            this.callbacks.push(onFulfilled);

        } else {//在resolve之后，直接执行回调，返回结果了

            onFulfilled(this.value);

        }

        return this;
    }

    _resolve(value) {

        this.state = 'fulfilled';//改变状态

        this.value = value;//保存结果

        this.callbacks.forEach(fn => fn(value));

    }

}

promise的链式调用原理，在promise执行then函数的时候，会再次return new promise 如果then没有传入函数只是调用，例如.then().then((res) => res) 此时会利用promise中的resolve方法将this.value再次包裹成promise 如果传入了一个函数，会先将函数进行执行（此时就是当前then传递的函数执行），再将返回的值，再次利用resolve的方法封装成一个promise，留给下一个then

class Promise {

    callbacks = [];

    state = 'pending';//

    value = null;//保存结果

    constructor(fn) {

        fn(this._resolve.bind(this));

    }

    then(onFulfilled) 

        return new Promise(resolve => {

            this._handle
                onFulfilled: onFulfilled || null,
                resolve: resolve
            });

        });

    }

    _handle(callback) {

        if (this.state === 'pending') {

            this.callbacks.push(callback);

            return;

        }

        //如果then中没有传递任何东西

        if (!callback.onFulfilled) 

            callback.resolve(this.value);

            return;

        }

        var ret = callback.onFulfilled(this.value);

        callback.resolve(ret

    }

    _resolve(value) 

        this.state = 'fulfilled';//改变状态

        this.value = value;//保存结果

        this.callbacks.forEach(callback => this._handle(callback));

    }

}

let a = new Promise((resolve) => {

	resolve('123');

})

let b = Promise.resolve(a);
	
b.then((res) => {

	console.log('res',res); // 123

})

resolve的方法实则是获取到value并赋值给this.value 便于then的时候能调用函数传递值；

问题点： 当接受到的是一个promise的时候，先去获取到该promise的then方法，然后调用then方法，then方法就会判断是否状态为pending，是则是痛callbacks收集，否则调用then的回调函数，并使用value作为行参

Promise.resolve() 原理实则是return 出一个promise 然后调用了这个promise的resolve方法，把值收集了起来。以便于你再then的时候直接调用函数并以value作为形参

if (

          value &&

          (typeof value === "object" || typeof value === "function")

        ) {

          var then = value.then;

          if (typeof then === "function") {

            then.call(value, this._resolve.bind(this));

            return;

          }

        }
	
## scrollIntoView
是可以将当前设置id的元素，自动与父元素底部对齐；eg: scrollIntoView({ behavior: 'smooth', block: 'end' })

## css函数env()、constant()
设置安全区域 因为一般的机型都存在一定的安全区域，简单点就是手机打开页面的时候会触及到屏幕四周的非安全区域，有时会出现乱入的感觉，重合什么的 我们就需要将两个区域隔离开

safe-area-inset-left：安全区域距离左边边界的距离
safe-area-inset-right：安全区域距离右边边界的距离
safe-area-inset-top：安全区域距离顶部边界的距离
safe-area-inset-bottom ：安全距离底部边界的距离

主要就是为了将我们的页面内容展示到安全区域内，不能超出；padding-bottom: constant(safe-area-inset-bottom);

#### 微信分享步骤

1.首先import Share from 'wechat-share-manager';初始化一个分享实例

2.调用实例的init的方法添加一些配置

3.再着引入import wx from 'weixin-js-sdk';

4.在需要分享的地方调用实例的share方法，传入回调函数，并且在回调函数中，调用wxsdk的ready方法，因为在调用所有的方法都需要在微信config信息认证之后，ready就能保证在认证信息之后再执行

你需要分享的appid也就是用户点击进入之后的公众号，小程序的appid 

#### 微信小程序授权

1.先调用微信授权接口

2.授权之后调用wx登陆接口，给后台传入授权code

3.后台拿到code，去访问微信后台，返回openid和seesion_key

4.本地就可以保存这个openid，第二次登陆时，就直接获取到openid去请求登陆接口进行登录了


用户关注公众号

后端做的鉴权，检验该用户是否在该公众号注册信息。

#### 不同操作使用不同的请求封装
再使用不同的数据请求的时候，可以利用两个不同的函数，分别来请求不同的接口，使用promise.resolve将请求回来的数据进行包装 并return出去，使用的地方await 结果
	
#### Vue3学习

vue3 项目搭建，使用vite脚手架来构建项目框子

小项目使用pinia来做状态管理 可以使用tailwindcss来做适配和管理css

ref 与 toRef toRefs的区别 

ref关联的值在改变的时候，不会影响到原有的值，原来的值变化也不会影响到ref关联后的值 但是toref和toRefs在修改值的时候会修改到原来的值， 不管的定义的值是响应式还是非响应式,  原来的值变化，会影响到toref 与 torefs关联后的值
	
https://overreacted.io/zh-hans/before-you-memo/

npm 引入包的时候是可以进行传值的。export出来函数，然后进行使用的时候就可以进行传递值

npm ci 可以根据package-lock.json来下载依赖，多人开发不会因为依赖不同导致出现问题。

npm outdated 可以查看是否包是否有兼容性的问题，红色代表可以任意升级，黄色是有兼容性版本；npm update则可以将红色进行更新（黄色不能随意更新，可能版本之间差异很大）

npm prune 将没有使用的依赖进行删除

https://ts.xcatliu.com/basics/type-assertion.html

https://tinypng.com/
	
https://jkchao.github.io/typescript-book-chinese/#why

xmind

https://www.animejs.cn/ 动画库的使用
	
	
	


