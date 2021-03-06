[TOC]
# 可视化日程统计开发

标签： 项目开发日志 PHP

---

### 0. 简介

- 项目地址: https://github.com/FaceShawn/ReDay
- 部署地址：http://reday.webtree.cc
- 2018.06
- 软件设计与开发实践 3

### 1. 配置 WAMP 本地开发环境

##### 1. 下载 [wampserver_X86_2.5.1455519048](http://www.wampserver.com/)

> `wampserver3.1.0_x64` 在windows7 64 下报错 `The setup files are corrupted Please obtain a new copy of the program`(安装文件已损坏，请获取程序的新副本)

> 尝试 DirectX修复工具，也失败

##### 2. 配置 wamp

##### 3. 场景配置

- [快速入门ThinkPHP 5.0--基础篇 2-8 场景配置](https://www.imooc.com/video/14755)
- [PHP项目配置运行环境的正确姿势](https://github.com/lisijie/homepage/blob/master/posts/tech/PHP%E9%A1%B9%E7%9B%AE%E9%85%8D%E7%BD%AE%E8%BF%90%E8%A1%8C%E7%8E%AF%E5%A2%83%E7%9A%84%E6%AD%A3%E7%A1%AE%E5%A7%BF%E5%8A%BF.md)

---

### 2. 配置 LAMP 服务器部署环境

##### 1. 配置网站根目录

```
# 修改网站根目录
vi /etc/apache2/sites-available/000-default.conf
# 重启 apache
sudo /etc/init.d/apache2 restart
```

##### 2. [ubuntu 二级域名配置](https://blog.csdn.net/u010071211/article/details/79511611)

##### 3. [非正常关闭 vi 编辑器后提示错误的解决方法](https://blog.csdn.net/qq_35447305/article/details/77922788)

---

### 3. [手把手编写PHP MVC框架实例教程](https://www.awaimai.com/128.html)

##### 1. [下载源码](https://github.com/yeszao/fastphp/archive/master.zip)
##### 2. 配置 Apache
1. 打开 httpd.conf

2. 打开重写扩展

> LoadModule rewrite_module modules/mod_rewrite.so 这句前面的 注释 # 去掉
> 将文件中所有的 AllowOverride None 改为 AllowOverride All

3. 设置DocumentRoot
```
DocumentRoot "c:/wamp/www/dwm/"
```

4. 设置目录
```
<Directory "c:/wamp/www/dwm">
    Options Indexes FollowSymLinks    #显示当前文件夹下的所有文件
    AllowOverride All #允许重写apache默认配置
</Directory>
```

5. 重启 wamp

##### 3. 设置重定向
    如果是Apache服务器，在根目录下新建一个 .htaccess 文件
```
<IfModule mod_rewrite.c>
    # 打开Rerite功能
    RewriteEngine On

    # 如果请求的是真实存在的文件或目录，直接访问
    RewriteCond %{REQUEST_FILENAME} !-f
    RewriteCond %{REQUEST_FILENAME} !-d

    # 如果访问的文件或目录不是真事存在，分发请求至 index.php
    RewriteRule . index.php
</IfModule>
```

##### 4. 配置项目配置文件

> 修改/config/config.php
---

### 6. 入坑 Atom 编辑器

##### 1. Sync 配置备份

- [Atom 配置备份神器 Sync Settings 教程](https://www.cnblogs.com/hooray/p/5885211.html)

    Personal access tokens : b22a2d7d325e069b004f7ae262dd80c10129990a
    Gist Id : 4bed82817c679576258683eb7d70cb6a
    Gist 库[已被墙]: https://gist.github.com/FaceShawn/4bed82817c679576258683eb7d70cb6a
- [自建 shadowsocks 服务器教程](https://github.com/Alvin9999/new-pac/wiki/%E8%87%AA%E5%BB%BAss%E6%9C%8D%E5%8A%A1%E5%99%A8%E6%95%99%E7%A8%8B)，建立 gist 仓库存储 sync 备份的 .atom 配置文件

- [通过PayPal取消Vultr预核准付款防止自动扣费M](https://www.wn789.com/5496.html)

##### 2. MarkDown 插件

- [markdown-preview-enhanced 文档](https://shd101wyy.github.io/markdown-preview-enhanced/#/zh-cn/)

##### 3. JSHint 插件

- [atom 中使用自定义 JSHint](https://blog.csdn.net/u010620152/article/details/71404192)

---

### 7. HTML & JQuery
##### 1. html 引用公共的头部和尾部
1.  [通过 jQuery 中的函数 load() ](https://blog.csdn.net/qq_35393869/article/details/79803190)

2.  [通过 iframe 框架标签](https://www.jianshu.com/p/140c71ccd7a6)

> Scrolling: 是否有滚动条，yes有，no无，auto 根据被显示html自动显示或隐藏

##### 2. [DOM 对象中 innerHTML，innerText，outerHTML，textContent的用法与区别](https://segmentfault.com/a/1190000000410375)
##### 3. [bootstrap 加载表格 & 单击获取当前行号](https://blog.csdn.net/framic/article/details/70254705)
##### 4. [Bootstrap Table 使用文档](https://www.jianshu.com/p/53505ec42fa3)
##### 5. [js 简单的实现点击选中点击取消的效果](https://www.jianshu.com/p/ab8f9de0739a)
##### 6. [$.inArry() 根据值删除数组元素](https://blog.csdn.net/m0_37290635/article/details/56487205)
##### 7. [为input的date类型设置默认值](http://ghmagical.com/article/page/id/unacjkHzT3W0)
##### 8. [JS 操作 JSON](https://www.cnblogs.com/worfdream/articles/1956449.html)
##### [JSON.parse() 和 JSON.stringify() 的区别 ](https://www.jianshu.com/p/eb449b29a2bd)

[document.getElementById() 与 $() 区别](https://www.cnblogs.com/hujunzheng/p/4907482.html)

##### 模态框

- [模态框被灰色阴影遮罩挡住](https://blog.csdn.net/oschina_41012066/article/details/78982969)

- ##### [模态框modal的高度和宽度设置](https://blog.csdn.net/u014326004/article/details/69789187)

##### 用时间戳动态加载 js 解决浏览器缓存，即 js 文件修改后浏览器不能及时更新的问题
    <script         src="/static/js/schedule.js?v=<%=timestamp()%>"></script>

1. [js 文件修改后浏览器不能及时更新](https://my.oschina.net/guopengfei/blog/411306?p=2)

2. [解决 js 缓存动态更新](https://segmentfault.com/a/1190000007404333)

3. [web 页面布局结构](https://images0.cnblogs.com/i/17148/201406/061638243337718.png)

---

###  8. MVC 框架
##### 1. [ORM 对象关系映射](https://www.pureweber.com/article/orm/)
##### 2. [pdo 数据库访问抽象层使用](https://www.kancloud.cn/curder/mysql/354884)
##### 3. [pdo 数据库访问抽象层详解](https://blog.csdn.net/nailwl/article/details/4733655)

---

### 9. PHP

##### 1. [spl_autoload_register() 和 __autoload()](https://my.oschina.net/alexskywinner/blog/92737)

---




[1]: https://images0.cnblogs.com/i/17148/201406/061638243337718.png
