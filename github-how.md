# 怎么用好GitHub
## 如何搭建GitPress博客
本文记录个人在搭建GitPress博客的流程。

### 目标描述
**流程**：通过本地ME编辑，github desk或git命令行同步到github，发布到gitrpess和公众号。
**重点**: 
#### 入门
1. 用GitHub帐号开通GitPress，关联一个GitHub Repo(etc."Blog")；选择文章同步路径（etc."/source")
2. 在刚关联的GitHub Repo指定路径（Blog/source)下创建以``.md``为后缀的文档,保存提交。
3. 在GitPress-Setting-Repo Setting点击【Rebuild】，刷新页面，Done.
#### 进阶
1. 如何创建博客目录导航栏？ [Ues table of content](https://gitpress.io/c/helps/collection-toc)
2. 如果插入图片及个性签名？图片同步七牛云。
3. 购买个人域名，完成网站备案，完成博客链接绑定个人域名。
花1块钱在腾讯云购买一个个人域名，在网站备案过程中遇到要输入备案授权码，而备案授权码要关联3月以上的云服务器才能生成，腾讯云服务最少要238！转念走万宝，搞定。
5. 每天写作更新
## 问题待办
- 如何通过github桌面版clone share仓库下的wiki？
![](./_image/2019-04-23-08-33-39.png)
![](./_image/2019-04-23-08-34-35.png)
更新：直接用命令行git发布，简浩高效。
- github文档中的图片在gitpress中拉取不出来？
![](./_image/2019-04-23-11-05-38.png)
  - [How to upload images and pictures?](https://gitpress.io/c/helps/faq)
可能要借助第三方云来搭建图床工具，目前有2种方案:1 是七牛云+腾讯云申请的域名；2 是升级ME为PRO版，赠送一年ME云图床
190523更新:不想折腾了，我的初衷是培养写作习惯，这阶段不应该花太多精力在这边角上，否则太消耗热情。以前有必要直接在ME上转付费用户。

## 思考
- 感觉我一直陷于工具的操作使用层面，并且经常因此页忘记最初需要解决的问题。比如，我最初搭建博客的目的是写作，学习Github使用，各种编辑器的操作技巧，本来是为了更好地服务写作，现在却因此沉迷于工具操作而忘记写作。
- 什么是云，什么是SSL，什么是域名，为什么一定要域名
- 快速熟练掌握ME写作技能
                            
有哪些比较好的gitpress博客推荐学习？
https://gitpress.io/@lyric/

##更多
- 请仔细阅读[官方说明文档](https://gitpress.io/c/helps/welcome)
- [为什么我选择用 Github issues 来写博客](https://mp.weixin.qq.com/s/1guyr383fAMXhS6JYVL2xA)
