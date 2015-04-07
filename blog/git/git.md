#git学习小结

##git常用指令

###git新建仓库的两种方法
* 已存在远程仓库，直接克隆的方式

    git clone <远程仓库名>
    
    git clone git@github.com:crystalgirl91/myBlog.git
    
以上代码表示克隆仓库名为myBlog的远程仓库到本地

* 新建本地仓库，推送到远程主机上

    mkdir myBlog
    cd myBlog
    git init
以上代码
