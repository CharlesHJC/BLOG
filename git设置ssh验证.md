# git本地设置通过ssh秘钥对验证登录github

```bash
#生成8192位密码验证
$ssh -keygen -b 8192 -C "charles_hjc@outlook.com" -t rsa

#生成一堆公私秘钥对，在~/.ssh/id_rsa和id_rsa.pub

#然后从git bash中使用命令添加私钥
$eval $(ssh-agent -s)
$ssh-add ~/.ssh/id_rsa
#如果出现Agent pid XXXX 则说明添加成功了

#如果出现报错，例如“Could not open a connection to your authentication agent”，则输入
$ssh-agent bash
#然后重新输入ssh-add命令即可

#ssh公钥添加到Github中
$clip < ~/.ssh/id_rsa.pub
```

也可以在github personal account页面中选择SSH and GPG keys，然后点击New SSH key，手动添加ssh公钥以及备注。

以上就是github配置ssh秘钥对的方式。

文章借鉴：<br>
[GitHub使用SSH连接以及生成修改添加密钥详细过程](https://www.cnblogs.com/zolich/p/12906838.html/)
