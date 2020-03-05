1.本地创建ssh key
本地Git库和GitHub仓库直接传输是通过SSH加密传输的，如果我们本地需要将代码提交到GitHub上，那么我们是需要创建SSH key的。
查看连接：

https://blog.csdn.net/k_520_w/article/details/82818847


常用命令
1、在安装完成之后，使用git config命令对Git进行全局设置：
git config --global user.name "your name" 
git config --global user.email "your email address"
2.克隆一份远程仓库
cd d:/GitTest   //指定存放的目录
git clone https://git.oschina.net/name/test.git   
//https://git.oschina.net/name/test.git你的远程仓库地址 
// 将远程仓库的代码拉取下来