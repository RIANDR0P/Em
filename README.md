2019.2.6 9:19-9:44
1. 一般习惯性把js放在body内容后面，因为网页加载是按顺序加载，可以提前加载网页内容再加载脚本
    常规：应用src连接同一服务器下的js文件或外部域（谨慎使用）
    使用defer 延迟加载脚本
    使用async 告诉浏览器立即下载文件，不保证按先后顺序执行。（不要在加载期间修改DOM）
    
2.文档模式
  混杂模式(quirks mode) 与标准模式(standards mode)
  准标准模式(almost standands mode)
  transitional/frameset
3.nostript
    使用nostript,当浏览器不支持脚本或禁止加载脚本,显示其中内容。
4.基本概念
   区分大小写。
   标识符采用驼峰大小写形式 forExample
   "use strict";（严格模式）可应用于function内
   始终在控制语句中使用代码块。
   变量：松散类型；
     var example;
     使用typeof检测数据类型；
     undefined；
     null；
     注意：通常要初始化变量，方便后期(typeof返回undefined时是未声明而不是未初始化)
     boolean类型 利用Boolean()（转型函数）转为对应boolean值
