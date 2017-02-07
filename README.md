## Windows Proxy Setting for Programmer

工作环境为 Win7 , 而且上网还要使用代理（还有用户名密码那种，方便记小本本，看你上了啥网那种），在此恶劣的环境之下，也练就了啥东西都要搞个Proxy才能使用

脑袋不够用，在这里记录下，也欢迎大家来补充。

### Atom

修改 `C:\Users\your_username\.atom\.apmrc` 在里面增加 proxy 设置

```
http-proxy=http://username:password@proxy:port
https-proxy=https://username:password@proxy:port
strict-ssl=false
```

### Sublime-Text2

打开 Sublime-Text2; 菜单 View - Show Console 或者 ctrl + \` 快捷键; 调出 console。将以下 Python 代码粘贴进去并 enter 执行，不出意外即完成安装

不需要代理输入：
```python
import urllib2,os;pf='Package Control.sublime-package';ipp=sublime.installed_packages_path();os.makedirs(ipp) if not os.path.exists(ipp) else None;open(os.path.join(ipp,pf),'wb').write(urllib2.urlopen('http://sublime.wbond.net/'+pf.replace(' ','%20')).read())
```

代理的话输入

> 注意修改 `'http': 'http://username:password@proxy:port'` 这段代码

```python
import urllib2,os;proxy=urllib2.ProxyHandler({'http': 'http://username:password@proxy:port'});opener=urllib2.build_opener(proxy);urllib2.install_opener(opener);pf='Package Control.sublime-package';ipp=sublime.installed_packages_path();os.makedirs(ipp) if not os.path.exists(ipp) else None;open(os.path.join(ipp,pf),'wb').write(urllib2.urlopen('http://sublime.wbond.net/'+pf.replace(' ','%20')).read())

```
