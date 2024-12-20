# Repository | Git存储库

<font color="red" size=3>通过Git仓库存储来达到资源存储仓库的目的(Github|Gitee)</font>

+ Temp1:https://raw.githubusercontent.com/ZhaoUncle/image/main/README.md
+ Temp2:https://cdn.jsdelivr.net/npm/jquery@3.6.4/dist/jquery.min.js

## 访问 | Access

**Github**

+ 原始raw访问方式:https://raw.githubusercontent.com/:User/:Repo/:Branch/:Path 
  + <font color="blue" size=3>[优点:无大小限制(或者50MB),CORS,快]</font>

**Gitee**

+ 原始raw访问方式:https://gitee.com/:User/:Repo/raw/:Branch/:Path

**<font color="blue" size=3>jsDelivr加速</font>**

+ |                             名称                             | 替换域名                                                     | 说明                                                         |
  | :----------------------------------------------------------: | ------------------------------------------------------------ | ------------------------------------------------------------ |
  | www.jsdelivr.com<br />原始:https://cdn.jsdelivr.net<br />清除jsDelivr缓存<br />用:https://purge.jsdelivr.net<br />可以查看包(Package):<br />https://www.jsdelivr.com/package/npm/:Package<br />https://www.jsdelivr.com/package/gh/:User/:Repo | ⭐1.fastly官:https://fastly.jsdelivr.net/<br />+ https://originfastly.jsdelivr.net/<br />说明2个:50MB;CORS;超级快<br />⭐2.gcore官:https://gcore.jsdelivr.net/<br />说明:20MB;CORS;快<br />⭐3.Cloudflare官:https://testingcf.jsdelivr.net/<br />说明:20MB;CORS;快<br />⭐4.quantil官:https://quantil.jsdelivr.net/<br />说明:50MB;CORS;超级快 | Npmjs加速:<br />https://:Replace/npm/:Package@:Version/:Path<br />Github加速:<br />https://:Replace/gh/:User/:Repo@:Branch/:Path<br />查看目录列表:<br />https://:Replace/gh/:User/:Repo@:Branch/<br /> |
  |                            第三方                            | 1.渺软:https://jsd.onmicrosoft.cn<br />说明:20MB;CORS<br />2.jsdmirror:https://cdn.jsdmirror.com<br />说明:20MB;CORS<br /> | 1.个人NoTitle:https://cdn.bili33.top<br />说明:20MB;CORS;快<br />2.个人pai233:https://jsdelivr.pai233.top<br />说明:20MB;CORS;快 |

+ <img src="https://i-blog.csdnimg.cn/blog_migrate/f1dfb26c38fb7b08508e8a7964cf1171.png" alt="jsDelivr工作原理" style="zoom:10%;" />

## 其他 | Other

|                   名称                   | 使用                                                         | 说明                                                         |
| :--------------------------------------: | :----------------------------------------------------------- | :----------------------------------------------------------- |
|  源:cdnjs.com<br />cdnjs.cloudflare.com  | ⭐1.Zstatic:https://s4.zstatic.net/<br />2.渺软:https://cdnjs.onmicrosoft.cn/<br />3.https://mirrors.sustech.edu.cn/cdnjs/<br />4.https://c.mx.sb/ | 1.同步cdnjs，默认缓存时间 1 年<br/>2.资源并非完全同步 npm，对资源有要求。<br/>示例:https://cdnjs.cloudflare.com/ajax/libs/jquery/3.7.1/jquery.min.js<br />替换:https://s4.zstatic.net/ajax/libs/jquery/3.7.1/jquery.min.js |
|                unpkg.com                 | ⭐1.Zstatic:https://s4.zstatic.net/npm/<br />+ https://lf6-unpkg.zstaticcdn.com/<br />2.zhihu:https://unpkg.zhihu.com/<br />+ https://unpkg.zhimg.com/<br />3.渺软:https://npm.onmicrosoft.cn/<br />4.度娘:https://code.bdstatic.com/npm/<br />5.东子:https://unpkg.shop.jd.com/ | 1.同步npmjs，默认缓存1年(建议通过语法来获取包内容)<br/>语法:https://unpkg.com/:Package@:Version/:Path<br/>替换:https://:Replace/jquery@3.7.1/dist/jquery.min.js |
| 源:www.npmjs.com<br />registry.npmjs.org | ⭐镜像:https://registry.npmmirror.com/<br />npm:https://registry.npmjs.org/<br/>yarn:https://registry.yarnpkg.com/<br/>tencent:https://mirrors.tencent.com/npm/<br/>cnpm:https://r.cnpmjs.org/<br />npmMirror:https://skimdb.npmjs.com/registry/<br/>huawei:https://repo.huaweicloud.com/repository/npm/ | 0.使用:https://registry.npmjs.org/:Package<br />1.更换node的npm\|yarn\|pnpm工具镜像源<br />`npm config set registry https://registry.npmmirror.com/` |
|                                          | 国内字节<br />(恶意篡改)https://cdn.bytedance.com/           | 传输字体文件专用<br />https://font.onmicrosoft.cn/包名@版本号/文件路径 |
|                                          | 国内StaticFile<br />(恶意篡改) https://staticfile.org/       | Web缓存网<br />https://www.webcache.cn/                      |
|                                          | BootCDN<br />https://www.bootcdn.cn/                         |                                                              |

## 动态切换CDN

```js
// 前端动态切换CDN(script标签的onerror|onload方法监听)
// 默认的CDN链接
const defaultCDN = "https://cdn.example.com/library.js";
// 备用的CDN链接
const fallbackCDN = "https://backup.example.com/library.js";
// 创建script元素
const script = document.createElement('script');
script.src = defaultCDN;
// onload 事件：当脚本加载成功时执行
script.onload = function() {
  console.log("脚本加载成功: " + defaultCDN);
  // 这里可以调用加载的库中的函数
};
// onerror 事件：当脚本加载失败时执行
script.onerror = function() {
  console.error("脚本加载失败: " + defaultCDN + "，尝试加载备用地址。");
  // 更换为备用CDN
  script.src = fallbackCDN;
  document.head.appendChild(script); // 重新添加script标签以加载备用链接
};
// 将script元素添加到document中
document.head.appendChild(script);
```

```js
// 动态切换CDN Promise
// Promise.any和Promise.race的区别 同时发起请求:race主要看谁第一个完成(无论成功还是失败),any主要看谁第一个成功
import axios from 'axios';
const source1 = axios.CancelToken.source();
const source2 = axios.CancelToken.source();
const source3 = axios.CancelToken.source();
const requests = [
  axios.get('https://api.example.com/endpoint1', { cancelToken: source1.token }),
  axios.get('https://api.example.com/endpoint2', { cancelToken: source2.token }),
  axios.get('https://api.example.com/endpoint3', { cancelToken: source3.token }),
];
Promise.any(requests)
  .then(response => {
    // 第一个成功的请求
    console.log('第一个成功的请求:', response.data);
    // 取消其他请求
    source1.cancel('请求被取消');
    source2.cancel('请求被取消');
    source3.cancel('请求被取消');
  })
  .catch(error => {
    // 所有请求都失败
    console.error('所有请求都失败:', error);
    // 可以选择在这里取消未完成的请求
    source1.cancel('请求被取消');
    source2.cancel('请求被取消');
    source3.cancel('请求被取消');
  });
```

# 代理Github RAW

+ >原始:https://raw.githubusercontent.com/:User/:Repo/:Branch/:Path 无限制;CORS;快;
  >
  >⭐RAW加速1:https://raw.gitmirror.com/ 超过20MB好像部分报错;CORS;快;
  >
  >RAW加速2:https://raw.kkgithub.com/ 无限制;CORS;慢;
  >
  >⭐RAW加速3:https://gitdl.cn/ 无限制;无CORS;快;
  >
  >⭐RAW加速4:https://ghproxy.net/ 无限制(最少50MB);CORS;快;

+ >> 原始RAW:https://raw.githubusercontent.com/:User/:Repo/:Branch/:Path
  >>
  >> 分支源码：https://github.com/User/:Repo/archive/:Branch.zip
  >>
  >> release源码：https://github.com/:User/:Repo/archive/:File
  >>
  >> release文件：https://github.com/:User/:Repo/releases/download/:Tag/:File
  >>
  >> 分支文件：https://github.com/:User/:Repo/blob/:Branch/:path
  >
  >⭐镜像代理加速1:https://github.moeyy.xyz/[原始RAW]|[分支源码]|[release源码]|[release文件]|[分支文件]
  >
  >+ 可以直接加速下载; 支持CORS跨域 ;
  >
  >⭐镜像代理加速2:https://gh.api.99988866.xyz/[原始RAW]|[分支源码]|[release源码]|[release文件]|[分支文件]
  >
  >+ 可以直接加速下载; 支持CORS跨域 ; 原始破除20MB限制

+ https://github.zhlh6.cn/ 仓库加速
+ https://gitclone.com/ 克隆加速