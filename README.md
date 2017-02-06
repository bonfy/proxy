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
