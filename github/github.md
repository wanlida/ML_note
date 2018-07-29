

https://dillinger.io/
### github learning 常用代码
>
windows环境下安装了github后，配置git

 -  配置提交者名称和邮箱：用于确定代码提交者的身份  
 - Windows打开Git Bash，Mac & Linux打开普通终端即可。执行以下命令：
 - 后面的有户名和邮箱请替换为自己的  
```sh
$ git config --global user.name "wanlida"  
$ git config --global user.email 914674505@qq.com
```
   
 

 配置ssh公/密钥:用于本地和Github网站间的安全通讯
 
```sh
# cd进入自己用户目录下  # Windows用户  
$ cd C:/Users/michaelx  # Mac & Linux用户  
$ cd ~ # 生成一对ssh钥匙：公钥和密钥。  
$ ssh-keygen -t rsa -b 4096 -C  "michaelx@michaelx.tech"  # 接着几个回车即可。cd进入.ssh目录  
$ ssh-add id_rsa # 将.ssh下的id_rsa.pub公钥文件用编辑器或者vim打开，command/Ctrl + C复制里面的所有文本内容到粘贴板
```
    打开你的个人中心的公钥访问设置：[SSH and GPG keys](https://github.com/settings/keys)  
点击右上角：`New SSH key`。输入任意标题title，将粘贴板上的公钥粘贴到key内容框中，`Addd SSH key`按钮保存。

 - 验证Github访问权限
 ```sh
 $ ssh -T git@github.com 
 # 出现以下提示，代表ssh公/密钥配置ok。需要输入2次yes
 ```
### 将本地项目文件上传,  先下载clone创建的项目到本地：
```sh
$ git clone git@github.com:xiong-it/test.git
```
### 将待提交的**项目文件全部拷贝**到`test`目录下面。执行下面命令即可提交了:
```sh
$ cd test 
$ git add . # ‘.’号表示添加该目录下所有待提交文件到追踪区  
$ git commit -m "提交说明文字：第一次提交"  
$ git push # 提交文件到test仓库的master分支
```