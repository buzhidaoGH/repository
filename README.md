# repository
存储项目静态资源仓库(repository)

可以通过CDN加速服务器访问(仓库名@XXX)代表仓库分支,默认是@master

+ `https://XXX/gh/用户名/仓库名@XXX/资源路径`
+ `https://cdn.jsdelivr.net/gh/buzhidaoGH/repository/资源路径`
+ `https://test1.jsdelivr.net/gh/buzhidaoGH/repository/资源路径`
+ `https://testingcf.jsdelivr.net/gh/buzhidaoGH/repository/资源路径`
+ `https://fastly.jsdelivr.net/gh/buzhidaoGH/repository/资源路径`
+ `https://gcore.jsdelivr.net/gh/buzhidaoGH/repository/资源路径`

默认github资源镜像raw加速

+ `https://XXX/用户名/仓库名/分支名/资源路径`

+ `https://raw.githubusercontent.com/buzhidaoGH/repository/master/资源路径`
+ `https://raw.gitmirror.com/buzhidaoGH/repository/master/资源路径`
+ `https://raw.fastgit.org/buzhidaoGH/repository/master/资源路径`
+ `https://raw.sevencdn.com/buzhidaoGH/repository/master/资源路径`
+ `https://raw.staticdn.net/buzhidaoGH/repository/master/资源路径`

# 加速方式

+ 使用Watt ToolKit加速

加速raw

+ ```text
  # 原地址 
  $ wget https://raw.githubusercontent.com/kubernetes/kubernetes/master/README.md 
  # 加速下载方法一 
  $ wget https://raw.staticdn.net/kubernetes/kubernetes/master/README.md 
  # 加速下载方法二 
  $ wget https://raw.fastgit.org/kubernetes/kubernetes/master/README.md
  ```

加速release

+ ```text
  # 原地址 
  wget https://github.com/goharbor/harbor/releases/download/v2.0.2/harbor-offline-installer-v2.0.2.tgz 
  # 加速下载方法一 
  wget https://download.fastgit.org/goharbor/harbor/releases/download/v2.0.2/harbor-offline-installer-v2.0.2.tgz 
  # 加速下载方法二 
  wget https://hub.fastgit.org/goharbor/harbor/releases/download/v2.0.2/harbor-offline-installer-v2.0.2.tgz 
  ```

加速clone

+ ```text
  # 方法一：手动替换地址 
  #原地址 
  $ git clone https://github.com/kubernetes/kubernetes.git 
  #改为 
  $ git clone https://github.com.cnpmjs.org/kubernetes/kubernetes.git 
  #或者 
  $ git clone https://hub.fastgit.org/kubernetes/kubernetes.git 
  #或者 
  $ git clone https://gitclone.com/github.com/kubernetes/kubernetes.git 
   
  # 方法二：配置git自动替换 
  $ git config --global url."https://hub.fastgit.org".insteadOf https://github.com 
  # 测试 
  $ git clone https://github.com/kubernetes/kubernetes.git 
  # 查看git配置信息 
  $ git config --global --list 
  # 取消设置 
  $ git config --global --unset url.https://github.com/.insteadof 
  ```

