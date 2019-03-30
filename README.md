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
        
