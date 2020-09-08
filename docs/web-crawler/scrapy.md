### 1. 爬虫基本原理概述
#### 1.1 爬虫基本流程
爬虫基本工作流程是：发起请求、获取响应内容、解析响应内容、保存数据

- 发起请求：通过HTTP库向目标站点发起请求，即发送一个Request，请求可以包含额外的headers等信息，等待服务器响应。

- 获取响应内容：如果服务器能正常响应，会得到一个Response，Response的内容便是所要获取的页面内容，**`类型可能有HTML，Json字符串，二进制数据（如图片视频）等类型`**。

- 解析响应内容：得到的内容 **`可能是HTML，可以用正则表达式、网页解析库进行解析`**。**`可能是Json，可以直接转为Json对象解析`** ，可能是二进制数据，可以做保存或者进一步的处理。

- 保存数据：保存形式多样，可以存为文本，也可以保存至数据库，或者保存特定格式的文件。

<hr>

#### 1.2 请求与响应
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;浏览器发送消息给该网址所在的服务器，这个过程叫做 **`HTTP Request(请求)`**。服务器收到浏览器发送的消息后，能够根据浏览器发送消息的内容，做相应处理，然后把消息回传给浏览器。这个过程叫做 **`HTTP Response(响应)`**。 浏览器收到服务器的Response信息后，会对信息进行相应处理，然后展示。
<hr>

#### 1.3 请求
* 请求方式：**`主要有GET、POST两种类型`**，另外还有HEAD、PUT、DELETE、OPTIONS等

* 请求URL：URL全称统一资源定位符，如一个网页文档、一张图片、一个视频等都可以用URL唯一来确定

* 请求头：包含请求时的头部信息，如User-Agent、Host、Cookies等信息

* 请求体：请求时额外携带的数据，如表单提交时的表单数据

<hr>

#### 1.4 响应
* 响应状态：有多种响应状态，如200代表成功、301跳转、404找不到页面、502服务器错误

* 响应头：如内容类型、内容长度、服务器信息、设置Cookie等等

* 响应体：最主要的部分，包含了请求资源的内容，如网页HTML、图片二进制数据等

<hr>

#### 1.5 抓取内容数据类型
- 网页文本：如HTML文档、Json格式文本等

- 图片：获取到的是二进制文件，保存为图片格式

- 视频：同为二进制文件，保存为视频格式即可

- 其他数据：只要是能请求到的，一般都能获取

<hr>

#### 1.6 解析内容的方式
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;直接处理、Json解析、正则表达式、**`bs4`**、PyQuery和Path等方式。如果遇到js渲染问题可以通过 **`分析Ajax请求、Selenium/WebDriver`**、Splash、PyV8和Ghost等来处理。
<hr>

#### 1.7 数据的保存
- 文本：纯文本、Json、Xml等

- 关系型数据库：如MySQL、Oracle、SQL Server等具有结构化表结构形式存储

- 非关系型数据库：如MongoDB、Redis等Key-Value形式存储

- 二进制文件：如图片、视频、音频等等直接保存成特定格式即可

<hr>
<div style="width: 60px;height: auto;z-index: 99;bottom: 30%;position: fixed;right: 0px" id="plug-ins">
    <div style="position: relative;float: right">
        <a target="_blank" href="https://blog.csdn.net/thanlon" id="weibo"
           style="display: block;width: 40px;height: 40px;background-color: #c4351b;margin-top: 1px;">
            <img width="22" height="20" src="../img/csdn.ico" alt=""
                 style="margin-top: 10px;margin-left: 9px">
        </a>
        <a target="_blank" href="http://wpa.qq.com/msgrd?v=3&uin=3330447288&site=qq&menu=yes" id="qq" style="display: block;width: 40px;height: 40px;background-color:#0e91e8;margin-top: 1px">
            <img width="20" height="20" src="../img/qq.png" 
                 style="margin-top: 10px;margin-left: 10px" alt="点击这里给我发消息" title="点击这里给我发消息">
        </a>
        <a href="javascript:" id="wechat"
           style="display: block;width: 40px;height: 40px;background-color:#01b901;margin-top:1px">
            <img width="22" height="20" src="../img/wechat.png"
                 style="margin-top: 10px;margin-left: 9px">
        </a>
        <a href="javascript:" id="go_top"
           style="display: none;width: 40px;height: 40px;background-color: #b5b5b5;margin-top: 1px">
            <img width="22" height="20" src="../img/top.png" alt=""
                 style="margin-top: 10px;margin-left: 9px">
        </a>
    </div>
</div>
