# Em
i don't know how to do this. It is just a try.

可在head中添加{
<title>...</title>
<script>...</script>
<meta>
<style>...</style>
<link>
}

hx标题标签自动加粗
<em 斜体
<strong 加粗
<span 对文字单独设置样式 （span{}
<q 引用 双引号由网页自动添加
<blockquote 长文本引用
空标签 <br /> <hr /> <img />
空格 &nbsp;
<address 地址标签
<code 引用代码
<pre 引用大段代码 内可保留空格和换行符
<div
<table{
tbody
caption标签，为表格添加标题和摘要
<table summary=  摘要
}

<a href table=""用于提示信息，鼠标移至。。时显示内容
电子邮件相关内容（如下
http://img.mukewang.com/52da4f2a000150b714280550.jpg
注意：电子邮件里面的subject和body不用加双引号
<img{
src alt title(提示文本

<form method="post/get" action="" 表单
<input   type="text/ password/ textarea/        name=" " value="网页中的提示内容"
        type="radio(单选框） checkbox(复选框）  selected="selected"
      multiple="multiple"
    type="submit reset
    placeholder 提供可描述输入字段预期值的提示信息（hint）。
该提示会在输入字段为空时显示，并会在字段获得焦点时消失  
   <lable 标签 
  
css
<link href="style.css" rel="stylesheet" type="text/css" />
class与id 区别 ： id只能引用一次，class 可无限次引用
css中，class前面为. 即.class ,而id为#id     分别称为类选择器和id选择器
子选择器，用于有子选项 >
注意与后代选择器的区别  (空格
分组 ,字符（同时为多个对象添加相同样式
!important 最高权值   大于用户自己设置权值
italic斜体  text-decoration   underline 下划线 line-through
text-indet 首字缩进
line-height 行间距（行高
letter/word-spacing

在讲解CSS布局之前，我们需要提前知道一些知识，在CSS中，html中的标签元素大体被分为三种不同的类型：块状元素、内联元素(又叫行内元素)和内联块状元素。
常用的块状元素有：
<div>、<p>、<h1>...<h6>、<ol>、<ul>、<dl>、<table>、<address>、<blockquote> 、<form>
常用的内联元素有：
<a>、<span>、<br>、<i>、<em>、<strong>、<label>、<q>、<var>、<cite>、<code>
常用的内联块状元素有：
<img>、<input>
display-block/inline incline-block
   dashed dotted solid
        
modern flow float layer
float 浮动
sans-serif 英文字体设置









全局配置 app.json   //即全局样式 pages等为局部样式
        页面路径 界面表现 网络超时时间 底部tap
        pages 描述所有界面路径
        windows 所有界面的顶部背景颜色 文字背景定义
工具配置 project.config.json

json 语法
        json的文件被包含于大括号中，通过key-value表达数据。key必须被包含于一个双引号中
   json值的数据格式
   数字
   字符串
   bool值
   数组
   对象
   Null   
   //json文件无法使用注释
   
WXML  充当html作用
        view button text 等
   //渲染与逻辑分离 （不再利用js记录用户行为，传递到dom api引起用户界面改变，让js管理状态
 wxml:   <text> {{msg}} </text>
 json:  this.setData({msg:'Hello World'})
 通过{{}}将变量绑定到界面上，称之为数据绑定
 
 Wxss css 
 JS 交互
 例如：更改msg文件内容为hello world
 <view> {{ msg }} </view>
 <button bindtap="clickMe">点击我</button>
 在js文件里申明clickMe 方法
 page({
        clickMe(){
        this.setData({msg:'hello world'})
        }
      })
      
      
小程序宿主环境 
逻辑层 （js)
渲染层 （wxml wxss)

渲染层 界面利用WebView 渲染
逻辑层 jsCore                     //native 代指微信客户端、
利用native作中转

程序与界面 
微信打开小程序 前 下载代码包到本地
利用 app.json 里的pages 了解所有界面路径
        其中 pages中第一个页面为首页
        
开发史
js-SDK
主要面对两大操作系统

json语法{//用大括号框起
"名称":"key",//名称与名称之间用逗号分隔
}

wxml 
//大小写敏感
//属性值也可以动态改变但必须包含于双引号中
//未被定义变量或是设置值为undefined值不会输出到wxml中

条件逻辑
        是否渲染 wx:if="{{condition}}
    使用wx:elif,wx:else添加else块
        //可利用标签将多组件包装一起判断
        
<block wx:if="{{true}}>
              <view>view1</view>
              <view>view2</view>
</block>    
    使用wx:for对组件重复渲染
        默认数组当前下标变量名：item
        默认数组当前元素变量名：index                   
     使用wx:key指定项目中唯一的标识符内容
         wx:key的值以两种形式提供
              字符串:代表在for循环中的array某个item的property，该值为列表中唯一的字符串或数字，且不能被改变
              保留关键词this 代笔在for循环中item本身(需要item本身为唯一的字符串或数字

template 模板
    定义代码片段，在不同地方引用
    使用is属性声明需要的模板，然后将所需数据传入
引用 import和include
import 不具有递归属性
include 可以将目标文件中除了 <template/> <wxs/> 外的整个代码引入，相当于拷贝代码
       
界面布局       
flex
    约定：布局元素（容器） container(类名) 容器内元素（项目） item表示项目类名
    
    
    
wxss
    尺寸单位rpx
    尺寸换算：宽度为375物理像素的屏幕下，1rpx = 1px
    样式引用
    内联样式 
    选择器
        类选择器 .class
        id选择器 #id
        元素选择器 element
        伪元素选择器 ::after 在view组件后面插入内容
                    ::before 在view组件前面插入内容
         权重优先级：
                !important  无限大
                style="" 1000
                #id     100
                .class  10
                element 1
ECMAscript      标准化脚本程序设计语言   javascript为其一种实现。
//浏览器中 javascript分为  ECMAscript BOM(浏览器对象类型) DOM(文档对象类型)
//NodeJS 中              ECMAscript NPM native
//小程序                   ECMAscript 小程序框架 小程序API
       //没有DOM BOM 因而JQuery、Zepto这种浏览器类库无法运行
遵循 ECMAscript5  ECMAscript6标准
        小程序IDE提供两者的转换标准 
        
模块化
可将JavaScript 文件作为一个模块，通过module.exports 或者 exports 对外暴露接口
小程序的脚本执行顺序
        入口文件为app.js
        由require文件顺序决定加载顺序
        
作用域
        与JQuary相似
        文件中定义的函数和变量只在当前文件有效
        使用getApp()获取全局变量
        
渲染与逻辑
1.渲染层与数据相关
2.逻辑层负责产生、处理数据
3.逻辑层通过Page的setData方法将数据传递至渲染
数据驱动
wxml对象和js可以看作是DOM树
{name:"view",
children:[
        {text: "hello world"}
        ]
       }
 
 //下使用app来代替代码层面的程序概念
 利用App()来注册程序App,其他js脚本可使用宿主环境提供的getApp()来获取程序实例
 App({
  onLaunch: function(options) {},
  onShow: function(options) {},
  onHide: function() {},
  onError: function(msg) {},
  globalData: 'I am global data'
})
其中onLaunch / onShow / onHide 三个回调是App实例的生命周期函数
onLaunch 当小程序初始化完成时，会触发onLaunch（全局只触发一次
onShow 当小程序启动，或从后台切回前台时触发
onHide 前台进入后台触发
onError 脚本错误或调用API 失败

程序的生命周期
初次打开小程序时，微信客户端初始化好宿主环境，下载小程序的代码包注入到宿主环境，初始化环境后调用onLaunch函数
home键或右上角退出小程序并未销毁（程序进入后台 onHide方法被调用
再次打开 onShow方法被调用
打开方式被分配给options函数
        app({
        onLounch:function {console.log(options)},
        onShow:function {console.log(options)}
        })
小程序全局数据
App实例是单例的，不同页面直接可以通过App实例下的属性来共享数据
App({
        globalData:"I am globalData"
        })
    other.js
var appInstance=getApp()
console.log(appInstance.globalData)

页面
//默认Pages字段的第一个页面为主页

Page构造器
Page({
  data: { text: "This is page data." },
  onLoad: function(options) { },
  onReady: function() { },
  onShow: function() { },
  onHide: function() { },
  onUnload: function() { },
  onPullDownRefresh: function() { },
  onReachBottom: function() { },
  onShareAppMessage: function () { },
  onPageScroll: function() { }
})

生命周期函数
onload 初次加载
onReady 初次渲染完成
onShow 监听页面显示，触发早于onReady
onHide 监听页面隐藏
onUnload 卸载
onPullDownRefresh 监听用户下拉
onReachBottom 上拉处理事件
onShareAppMessage 右上角转发
onPageScroll 页面滚动函数
初次加载 onLoad方法被调用，Page未被销毁则仅调用一次，回调时获取当前页面的打开参数option
当前页面使用wx.redirectTo或wx.navigateBack返回到其他页时，当前页面会被微信客户端销毁回收，此时Page构造器参数所定义的onUnload方法会被调用

// pages/list/list.js
// 列表页使用navigateTo跳转到详情页
wx.navigateTo({ url: 'pages/detail/detail?id=1&other=abc' })

// pages/detail/detail.js
Page({
  onLoad: function(option) {
        console.log(option.id)
        console.log(option.other)
  }
})
页面路径用？分割path和query部分，query多参数用&分割
page构造器里onLoad里option可以拿到当前页面打开参数，类型为Object,键值与界面URL上query 值一一对应

页面数据
wxml通过数据绑定的方法绑定从逻辑层传来的数据字段，数据即Page里data,data参数是页面第一次渲染时从逻辑层传到渲染层
setData函数，可以在Page实例下的方法调用this.setData把数据传递给渲染层更新数据，由于渲染与逻辑是两个线程，传递数据相当于异步过程，setData第二个参数callBack回调，在这次setData渲染完毕后触发。
Page({
  onLoad: function(){
    this.setData({
      text: 'change data'
    }, function(){
      // 在这次setData对界面渲染完毕后触发
    })
  }
})

注意事项：
直接修改 Page实例的this.data 而不调用 this.setData 是无法改变页面的状态的，还会造成数据不一致。
由于setData是需要两个线程的一些通信消耗，为了提高性能，每次设置的数据不应超过1024kB。
不要把data中的任意一项的value设为undefined，否则可能会有引起一些不可预料的bug。

页面的用户行为
onPullDownRefresh 下拉刷新
需要在app.json的window选项中或页面配置page.json中设置enablePullDownRefresh为true。当处理完数据刷新后，wx.stopPullDownRefresh可以停止当前页面的下拉刷新

Page({
onShareAppMessage: function () {
 return {
   title: '自定义转发标题',
   path: '/page/user?id=123'
 }
}
})
等等...

页面跳转
使用 wx.navigateTo({ url: 'pageD' }) 可以往当前页面栈多推入一个 pageD，此时页面栈变成 [ pageA, pageB, pageC, pageD ]。
使用 wx.navigateBack() 可以退出当前页面栈的最顶上页面，此时页面栈变成 [ pageA, pageB, pageC ]。
使用wx.redirectTo({ url: 'pageE' }) 是替换当前页变成pageE，此时页面栈变成 [ pageA, pageB, pageE ]，当页面栈到达10层没法再新增的时候，往往就是使用redirectTo这个API进行页面跳转。
多页面的生命周期等等。详见https://developers.weixin.qq.com/ebook?action=get_post_info&docid=0004eec99acc808b00861a5bd5280a

组件
API
多数API挂在wx
wx.on* 监听某个事件发生 接受一个Callback参数，当事件触发，调用Callback函数
wx.get* 获取宿主环境数据的接口
wx.set* 写入数据到宿主环境

接口回调
success 调用成功
fail 调用失败
complete 调用完成（无论结果

事件
<view id="tapTest" data-hi="WeChat" bindtap="tapName"> Click me! </view>

// page.js
   Page({
  tapName: function(event) {
    console.log(event)
  }
})

事件通过bindtao绑定到组件上，在Page中定义对应的事件处理函数，当触发事件，处理函数执行，同时受到一个事件对象event

事u件绑定与冒泡捕获
key以bind或catch开头，后跟上事件类型
bind 和capture-bind 分别表示事件的冒泡阶段和捕获阶段（捕获在前
catch可以阻止事件向上冒泡

flex布局
flex-direction 属性 设置坐标轴方向
flex-wrap 设置是否允许多行排列及方式
justify-content 在主轴上对齐方式，及项目间是否空隙
align-items 在行中对齐方式

.container
