<h1>  Xssing - Funny and easy xss platform  </h1>
<font color='green'><h2>  基于  php+mysql 的  xss  利用平台      <a href='http://xssing.sinaapp.com'>http://xssing.sinaapp.com</a>   </h2> </font>


项目发布地址   http://yaseng.me/xssing-1.html  <br>
介绍文章       <a href='http://yaseng.me/bind-xss-tutorial.html'>http://yaseng.me/bind-xss-tutorial.html</a> <br>
Google 托管    <a href='http://code.google.com/p/xssing/'>http://code.google.com/p/xssing/</a><br>
演示视频       <a href='http://v.youku.com/v_show/id_XNDYzODM5MDcy.html'>http://v.youku.com/v_show/id_XNDYzODM5MDcy.html</a>  <br>
交流qq群       209546692<br>
作者微博  <a href='http://t.qq.com/uaucya'>http://t.qq.com/uaucya</a>

<h2>安装 </h2>

在下载http://code.google.com/p/xssing/ 或 <a href='http://yaseng.me/xssing-1.html'>http://yaseng.me/xssing-1.html</a>
导入 xssing.sql 到mysql  配置 config/mysql.php  删除 /apps/running/uauc.php 可以运行<br>
<h4> 在sae部署 </h4>
<blockquote>新版本的xssing 完全兼容 sae  请修改配置总入口文件 /uauc/uauc.php<br>
define('SAE',1);        // 1 在sae部署</blockquote>

<blockquote><h4> 邮件配置  </h4>
apps\index\lib\common\common.php  修改 send_mail( send_sae_mail) 对应的信息 更新缓存  你懂的</blockquote>

<h4> 常见问题 </h4>
<blockquote>q:安装之后一片空白  <br>
a:更新至最新版  开启php错误提示  (uauc/uauc.php 加一个 os_start())  <br></blockquote>

<blockquote>q:怎么添加用户   <br>
a:查看  apps/index/action/User.Action.php 里面的生成邀请码算法   请改变token值   <br></blockquote>

<blockquote>q:怎么把?m=xing&a=info&bid=29  又长又臭的url  改成 想  /xing/info/bid   <br>
a:这个是mvc框架的典型特征  请自行编写url rewrite   <br></blockquote>

<blockquote>q:打开之后没有 样式  css  图片没加载就来 <br>
a:手动定义一下  uauc/define.php  define('SITE_ROOT',"网站url 带http") <br></blockquote>

<blockquote>q:擦 你在源码里面留了后门吧  看  /demo/test.php  一句话 echo  htmlentities($<i>GET['a']);</i><br>
a:好吧  你赢了  这TM能用菜刀连接我就自宫</blockquote>



<h2>使用 </h2>
<a href='http://yaseng.me/xssing-1.html'>http://yaseng.me/xssing-1.html</a>  详细使用方法<br>
<br>
<br>
<h2>开发 </h2>
<h4>概述</h4><p>
<blockquote>xssing 是一个基于 php+mysql的 网站 xss 利用与检测平台,可以对你的产品进行黑盒xss安全测试,可以兼容各种浏览器客户端的网站url,cookies已经user-agent下线,批量管理代码,采用MVC构架,易于阅读和二次开发.  基于Php+Mysql  采用轻量级快速框架UAUC,  框架代码下  uauc 下面,入口文件 为 uauc.php,框架核心采用缓存编译机制,修改uauc 目录和 config 目录下的文件都要删除缓存重新编译(/apps/running/uauc.php)<br>
</blockquote><blockquote>项目开发主要于 apps 下面的文件  mvc 架构的  action  和 model 的编写,已经view 视图前台设计</p>
<h4>开发规范</h4>
<blockquote>请加qq群 209546692也可以联系作者  yaseng@uauc.net<br>
<h4>项目目录结构</h4>
<pre>
├─apps<br>
│  └─index                     /*项目*/<br>
│      ├─action                /*动作*/<br>
│      ├─lib<br>
│      ├─model<br>
│      ├─running<br>
│      └─view                 /*模板视图文件*/<br>
│          ├─index<br>
│          ├─project<br>
│          ├─public<br>
│          │  ├─js<br>
│          │  └─style<br>
│          │      └─toolbar<br>
│          ├─user<br>
│          └─xing<br>
├─config                     /*系统配置*/<br>
├─demo                       /*简单的留言加后台系统*/<br>
│  ├─admin<br>
│  └─static<br>
│      ├─css<br>
│      │  └─images<br>
│      │      └─source<br>
│      ├─images<br>
│      │  ├─panel<br>
│      │  └─toolbar<br>
│      └─js<br>
├─release<br>
├─static                    /*图片  css  js 等静态文件*/<br>
│  ├─js<br>
│  └─style<br>
└─uauc                      /*核心框架库*/<br>
├─class<br>
├─common<br>
├─core<br>
└─lib </pre></blockquote></blockquote>



<h2> 更新记录 </h2>
<blockquote><h4> xssing 1.0 </h4>
完成xss 平台基本框架<br>
<h4> xssing  1.1 </h4>
修复几个bug  完善在 linux 环境下的兼容性<br>
<h4> xssing  1.2 </h4>
修改几个逻辑bug和  自身的xss (伪造USER_AGENT) ps:感谢法克论坛的灰太狼<br>
完全兼容sae平台<br>
<h4> xssing  1.3 </h4></blockquote>

<blockquote>内核框架 uauc framework 调试升级可以记录脚本运行时间 当前执行sql语句<br>
xss 获取信息兼容性<br>
增加浏览器批量删除  全选  功能<br>
增加 126 网址缩短<br>
增加邮件提醒 (sae 兼容)</blockquote>












