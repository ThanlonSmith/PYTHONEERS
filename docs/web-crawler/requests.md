#### 1. requests的方法
requests模块中的方法有get、post、put、delete、patch等，常用的是get和post方法。使用示例是：
```python
requests.requets(method='get')
requests.requets(method='post')
```
<hr>

#### 2. requests的参数
get方法的参数有：url、headers、cookies、params、proxies等，示例：
```python
requests.get(
    url='https://www.baidu.com',
    headers={},
    cookies={},
    params={'k1': 'v1', 'k2': 'v2'},  # https://www.thanlon.cn?k1=v1&k2=v2
    data={'user': 'thanlon', 'pwd': '123456'},
    json={'user': 'thanlon', 'pwd': '123456'},
    proxies={
        # 如果是http向123.206.74.1:80发送请求，由123.206.74.1:80来帮助我们向目标站点发请求
        # 如果是https就会找http://123.206.74.24:3000这个代理
        'http': '123.206.74.1:80',
        'https': 'http://123.206.74.24:3000',
        # 指定的地址使用指定的地址
        'http://www.thanlon.cn': 'http://123.206.74.24:3000'
        # 公司里要随机去动态使用代理 ip，可以使用random函数
    },
    files={
        # 'f1': open('log.txt', 'rb')
        # 自定义上传的文件名
        # 'f1': ('test.txt', open('log.txt', 'rb'))
    },
    # 认证，下面有详细介绍
    auth=None,
    # 连接超时。timeout=(5,1):返回超时，连接超时。
    # 如果请求的地址重定向了，默认浏览器重定向到其它地址拿到结果。但如果写了False表示不重定向，拿到的是响应头（重定向），没有相应体。
    timeout=1,
    # 是否允许重定向
    allow_redirects=True,
    # 大文件下载，下面有详细介绍
    stream=True,
    # verify = False：不用确认，直接进行下去
    cert='xxx.pem', verify=False
)
```
post方法的参数有：url、headers、cookies、data、json等，基本上和get方法的参数通用，示例：
```python
requests.post(
    url='https://www.baidu.com',
    headers={},
    cookies={},
    # 传请求体，放到请求头中，不显示在url中 GET /index http1.1\r\nhost:c1.com\r\n\r\nuser=thanlon&pwd=123456
    data={'user': 'thanlon', 'pwd': '123456'},
    json={'user': 'thanlon', 'pwd': '123456'},
    proxies={},
    files={
        # 'f1': open('log.txt', 'rb')
    },
    # 认证，下面有详细介绍
    auth=None,
    # 连接超时。timeout=(5,1):返回超时，连接超时
    timeout=1,
    # 是否允许重定向
    allow_redirects=True,
    # 大文件下载，下面有详细介绍
    stream=True,
    # verify = False：不用确认，直接进行下去
    cert='xxx.pem', verify=False,
)
```
代理的验证：
```python
# coding:utf-8
import requests
from requests.auth import HTTPProxyAuth

proxies = {
    'http': '123.206.74.1:80',
    'https': 'http://123.206.74.24:3000'
}
auth = HTTPProxyAuth('thanlon', 'kiku')  # 代理认证是需要的代理的用户名和密码，通过data传入
ret = requests.get('http://www.thanlon.cn', proxies=proxies, auth=auth)
# 如果给目标站点的用户和密码使用data
# ret = requests.get('http://www.blueflags.cn', data={'thanlon', 'kiku'}, proxies=proxies, auth=auth)
print(ret.text)
```
认证auth：浏览器弹窗(路由器)内部是将用户和密码加密，放在请求头中传给后台。浏览器做的：

- 把用户名和密码拼接成字符串"用户:密码"

- 对该字符串进行加密，base64("用户:密码")，base64是可以反解的

- 对字符串拼接，再构造一个字符串"Basic base64('用户|密码')"

- 把该字符串放在请求头中， Authorization:"basic base64('用户|密码')"
```python
import requests
from requests.auth import HTTPBasicAuth, HTTPDigestAuth  # HTTPDigestAuth是数字认证，算法与基础认证不一样

result = requests.get('https://api.github.com/user', auth=HTTPBasicAuth('thanlon', 'xxx'))
print(result.text)
'''
{"message":"Bad credentials","documentation_url":"https://developer.github.com/v3"}
'''
```
>**安全机制弱，一般不用，不可以自己定义加 token，也不可以自己定义请求头，这是定死的规则。**

stream：大文件下载。使用 requests 可以下载大文件，比如视频文件。如果有8G的视频，发个请求8个G视频全部放到内存，需要把视频从内存写到文件中。内存如果没有8G，很可能宕机。如果使用 stream = True，是一点一点下载。
```python
import requests

from contextlib import closing

with closing(requests.get('http://google.com/', stream=True)) as r:  # 一点一点下载
    # 处理响应
    pass
for i in r.iter_content():  # 一点一点取
    print(i)
```
<hr>

#### 3. requests的6种常见异常
* requests.ConnectionError：网络连接异常，如DNS查询失败，拒绝连接

* requests.HTTPError：HTTP错误异常

* requests.URLRequired：URL缺失异常

* requests.TooManyRedirects：超过最大重定向次数，产生重定向异常

* requests.ConnectTimeout：连接远程服务器超时异常

* requests.Timeout：请求url超时，产生超时异常

>**`值得注意的是：Timeout异常是发出url请求获取内容整个过程的超时异常，而ConnectTimeout异常仅指与远程服务器连接产生的超时异常。`**

<hr>