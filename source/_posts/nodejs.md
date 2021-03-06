---
title: 手把手告诉你如何安装多个版本的node
date: 2017-04-13 13:32:56
tags: 
    - JavaScript
    - nodejs
categories: 
    - 环境安装
    - nodejs
---
最近好多人都问到node怎么同时安装多个版本? 如何配置node的环境变量,如何自如的在多个版本中切换node?因为这种种原因,所有打算写一篇文章来专门讲解如何安装多个版本的node!!!

**node版本可以去 [node中网网](http://nodejs.cn/) 或者到我的 [百度云盘](http://pan.baidu.com/s/1c2qw1f6) 下载**
 > 安装多个版本的node的时候一定要从低版本开始安装,如果你先安装高版本的话会出现许多问题,如果你已经安装啦,先卸载掉然后进行下面的步骤
 
 
1. 下载后得到啦安装包,有32位和64位的多版本安装包,用户根据自己系统自行选择
    ![node安装bao](/images/01.png)
2. 在安装node之前,我先选择一个node安装目录,我要安装到D盘下,所有我在D盘中新建啦一个node的目录,并且在里面创建啦一个4.42的文件夹,应为我一会要在这个文件夹中安装4.42版本的node
     ![node安装bao](/images/02.png)
3. 开始安装:
    1. 打开node4.42的安装包,一直点击下一步,直到出现安装路径:
        ![node安装bao](/images/03.png)
         ![node安装bao](/images/04.png)
    2. 安装路径更改我们创建的那个4.42文件夹的路径,然后一路下一步,安装成功后文件夹内出现啦好多文件,这个时候node就安装好啦
        > 把里面的路径改成`D:\node\4.42\` 
         ![node安装bao](/images/05.png)
    3. node安装好后是不是就能用啦呢?当然不是,你还需要配置环境变量  计算机=> 属性=> 高级系统设置=>环境变量
         ![node安装bao](/images/06.png)
         ![node安装bao](/images/07.png)
         ![node安装bao](/images/08.png)
    4. 在系统变量中点击新建,变量名:node_4.42,变量值就是你4.42版本的安装目录,也就是`D:\node\4.42\`
         ![node安装bao](/images/08.png)
         ![node安装bao](/images/10.png)
    5. 点击确定后再系统变量中找到`path` 变量,选中后点击编辑
         ![node安装bao](/images/11.png)
    6. 看到`path`变量中的值啦嘛?我们把刚才新建的变量添加到这里面,如何添加呢? 一对`%`号,中间写上刚才新建的变量明,然后放到path中的最后面,一定不能忘啦中间的`;`号,每条变量中间都应该有个`;`
         ![node安装bao](/images/12.png)
         ![node安装bao](/images/13.png)
    7. 放好后点击确定,然后咱们打开`CMD`  (win+R);输入:
        > $ node -v 
         ![node安装bao](/images/14.png)
        
    8. 如何出现啦版本号,那么我们的第一个node已经安装完成并且可以正常使用啦;


4. 安装多个版本:第一个安装好后安装第二个node版本;
    
    1. 在安装新的版本之前,我们需要做的就是先找到之前的那个版本的安装目录,也就是`D:\node\4.42`,然后把4.42这个文件夹给他重命名(因为你如果不修改名字的话你在安装新版本的时候无论你安装在什么地方,都会把之前的那个干掉):
         ![node安装bao](/images/15.png)
         
    2. 修改后再创建一个新的目录,我给他取名叫5.11(因为我打算下一个安装5.11版本的)
         ![node安装bao](/images/16.png)
         
    3. 接下来开始安装5.11就可以啦,还是和上面过程一样,直到配置完环境变量后我们的5.11就安装好啦.
         ![node安装bao](/images/17.png)
         
    4. 安装好5.11的版本后咱们再回来吧4.42的那个目录改回来;
         ![node安装bao](/images/18.png)
         
    5. 验证我们目前是否是安装了两个node版本:`where node ` ,和当前使用的版本:`node -v`
        > $ where node
        
        ![node安装bao](/images/19.png)
        
    > where node 出现啦两个,说明我们确实是安装啦两个版本的node,`node -v` 告诉我们当前使用的是哪个版本!!!
    
    > 如果我们还要在安装其他版本的话方法也是一样的,按照上面的就可以啦
    
5. 假如我们现在安装啦许多的node,但是当前的node版本不是我目前想用的怎么办呢?如何切换node版本呢?
    
    1. 打开环境变量,找到`path`.你想用哪个版本,就把哪个node变量放到所有node变量的最前面,比如我之前的path是%node_4.42%;%node_5.11%,我用的就是4.42的版本,我如果想
    用5.11的版本的话我就得把path里面的`%node_4.42%;%node_5.11%`改成`%node_5.11%;%node_4.42%`
       ![node安装bao](/images/20.png)
       
    2 这时候我们再看看: `where node`和`node -v`
       ![node安装bao](/images/21.png)

> 这就是我们的安装多个版本node和node之间的版本切换;



    