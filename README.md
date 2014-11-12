## nginx 基本认证配置

### nginx准备
* 使用的nginx官方的repo，然后yum install nginx -y
* 然后把/etc/nginx中的nginx.conf conf.d/ 和缺省的www目录copy过来，并修改路径
* 将html目录（也就是缺省的www）中的index.html做一个修改，让其与原版不同
* 增加基本认证配置
    * 生成一个passwd文件，加上两个用户名密码，密码是用openssl passwd算个hash
    * 按[这里](http://nginx.org/en/docs/http/ngx_http_auth_basic_module.html)进行配置，其实上一步也是按这个链接配置的
* 具体修改完的结果看这个demo

### nginx启动
* 进入这个demo配置目录
* sudo nginx -p ./ -c ./nginx.conf

### 检验
* curl localhost，这时候是401
* curl -u name1:password1 localhost，这时候就可以访问了

### 参考：
* [nginx auth basic](http://nginx.org/en/docs/http/ngx_http_auth_basic_module.html)
* [openssl passwd](http://www.openssl.org/docs/apps/passwd.html)
* [客户端使用](http://www.cnblogs.com/tankxiao/archive/2012/09/26/2695955.html)
