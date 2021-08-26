# study-in-com
## Js在使用for in遍历对象的时候会讲对象的键1234变成字符串
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
2. 然后在分支上cherrypick自己需要的代码hash  eg: git cherry-pick 0396bccb8829cd9efe4b0a17d19d642bb2e4ffa4
3. 然后推到远程的分支上 flow pick start 
如果此时线上的代码有问题 此时应该切换到master分支上 提交自己的fix 然后再自己的分支上将这次的代码cherrypick过去 
## 抓包工具 proxyman 使用步骤
1 下载安装
2  安卓手机需要安装证书 用手机上下载的chrome打开 http://proxy.man/ssl 下载一个pem的证书进行安装 
3 在使用抓包的时候 我们在手机端链接wifi的时候设置代理 然后设置和电脑wifi相同ip和端口 就可进行抓包
4 如果抓包时手机访问不了可以检查是否是认证证书没有安装成功
## H5页面手机上联调
手机和电脑同时链接同一个wifi
手机访问电脑的wifi 的ip即可进行查看
注意点：连接的wifi不能设置代理，不然访问不了；需要设置wifi的代理是在使用手机抓包的时候才用到
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
3.extends是在某个类型中必须是某个类型对像中的某个键
4.type定义的类型是属于类型的别名

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






