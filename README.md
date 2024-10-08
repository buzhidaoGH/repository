# Github

## repository

存储项目静态资源仓库(repository)

可以通过CDN加速服务器访问(仓库名@XXX)代表仓库分支,默认是@master

+ `https://XXX/gh/用户名/仓库名@XXX/资源路径`

+ `https://cdn.jsdelivr.net/gh/buzhidaoGH/repository/资源路径`

+ ```
  前端动态切换CDN(script标签的onerror|onload方法监听)
  //  <script src="默认链接地址" onerror="函数">
  //  script对象的onerror函数
  1. jsd.cdn.gitkf.com 完美
  1. jsd.cdn.zzko.cn 完美 （由54ayao提供，稳如老狗，推荐）
  2. testingcf.jsdelivr.net 完美
  3. cdn.jsdelivr.us 优秀
  4. jsdelivr.codeqihan.com 优秀
  4. originfastly.jsdelivr.net 优秀 官方
  5. fastly.jsdelivr.net 优秀			官方
  6. gcore.jsdelivr.net 一般
  7. cdn.bili33.top 一般
  0. test1.jsdelivr.net 报错
  0. https://cdn.jsdelivr.net （官方默认加速）
  0. https://Fastly.jsdelivr.net （官方默认加速）
  0. https://jsd.cdn.zzko.cn
  0. https://cdn.jsdelivr.us
  0. https://cdn.jsdmirror.com
  ```

默认github资源镜像raw加速

+ `https://XXX/用户名/仓库名/分支名/资源路径`
+ `https://raw.githubusercontent.com/buzhidaoGH/repository/master/资源路径`
+ `https://raw.gitmirror.com/buzhidaoGH/repository/master/资源路径`
+ `https://raw.fastgit.org/buzhidaoGH/repository/master/资源路径`
+ `https://raw.sevencdn.com/buzhidaoGH/repository/master/资源路径`
+ `https://raw.staticdn.net/buzhidaoGH/repository/master/资源路径`

github镜像文件加速

+ https://moeyy.cn/gh-proxy 文件加速
+ https://gh.api.99988866.xyz/ 文件加速
+ https://github.zhlh6.cn/ 仓库加速
+ https://hub.nuaa.cf/ 镜像网站
+ https://hub.yzuu.cf/ 镜像网站
+ https://github.ur1.fun/ 文件加速
+ https://raw.gitmirror.com
+ https://raw.fgit.cf

## 加速方式

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

# Gitee

## repository

国内使用的仓库:具体核心为gitee的Pages工程

+ Page默认绑定的是master分支;且需要手动提交更新
+ 访问方式为:`Pages： http://buzhidaogh.gitee.io/repository/资源路径`

或者raw访问方式

+ `https://gitee.com/XXX用户名称/XXX仓库名称/raw/分支版本/资源路径`

+ `https://gitee.com/buzhidaoGH/repository/raw/master/资源路径`