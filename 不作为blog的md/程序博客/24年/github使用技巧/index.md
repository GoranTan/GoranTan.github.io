# 

```toml
title: 我的第一个博客：使用Github的小技巧
date: 2024-11-03
# tags分为Github,前端，python，AI等
# categories分为code和life以及study
tags:
  - Github
categories:
  - code
# 进入文章的第一张图
featuredImage: &#34;https://gorantan-blog.oss-cn-shanghai.aliyuncs.com/pic/20241204091417901.jpg&#34;
# 还没进入文章的封面图，可在网站自动生成：https://coverview.lruihao.cn/
featuredImagePreview: &#34;https://gorantan-blog.oss-cn-shanghai.aliyuncs.com/pic/20241204093206748.png&#34;

author:
  name: Goran
  link: https://github.com/GoranTan
  email: &#34;2446040095@qq.com&#34;
  avatar: &#34;https://gorantan-blog.oss-cn-shanghai.aliyuncs.com/pic/20241203195700868.png&#34;

page:
  - authorAvatar: true
  - wordCount : true
  - readingTime : true
  - endFlag: &#34;end&#34;
  - toc: true
```

简介：本文分享我作为新手的一些github的使用技巧，分别是如何快速的访问github，如何不进入github实现加速github项目的下载和clone，以及github的项目文档书写规范。



# 1.如何快速的访问github

内容：本人实测的可行的加速github方法，网上发布的很多方法经过测试已经无法使用，比如修改host地址，目前是2024年10月30日，以下方法仍然可用。



## 1.1. 下载使用steam&#43;&#43;

这个方法本人并未使用，但是在搜索时在2024年有多条评论显示steam&#43;&#43;可以实现github加速。



## 1.2. 下载devsidecar

devsidecar是一个github的开源项目，可以实现：dns优选，请求拦截，github直连加速，npm加速，Stack Overflow加速。

项目路径：[docmirror/dev-sidecar: 开发者边车，github打不开，github加速，git clone加速，git release下载加速，stackoverflow加速](https://github.com/docmirror/dev-sidecar)

下载路径：[Releases · docmirror/dev-sidecar](https://github.com/docmirror/dev-sidecar/releases)

使用方法：按照教程下载安装之后，在首页打开默认模式。如果打不开github连接，可以复制下载链接在下面介绍的加速下载网站打开。

&lt;center&gt;{{&lt;figure src=&#34;../assets/app1.png&#34; width=&#34;100%&#34; title=&#34;软件图片&#34;&gt;}}&lt;/center&gt;



# 2.如何加速github的下载和clone

大家经常可以遇到clone速度以kb/s甚至b/s计数，在网上找到一个好用的方法，有两个网站，可以把要clone的网址复制下来，粘贴到网站里，第一个网站速度接近1mb，第二个网站可以达到2到4mb，这个也和网络有关。

[GitHub加速下载](https://github.moeyy.xyz/)
[GitHub 文件加速](https://gh.api.99988866.xyz/)



# 3.如何培养好的文档编写习惯

从一个github大佬那里参考过来的，有点忘记名字了，一个好的文档编写习惯对于小白来说还是挺重要的。

软件手册是一部完整的书，建议采用下面的结构。

- 简介(Introduction)：[必备][文件]提供对产品和文档本身的总体的、扼要的说明。
- 快速上手(Getting Started)：[可选][文件]如何最快速地使用产品。
- 入门篇(Basics)：[必备][目录]又称“使用篇”，提供初级的使用教程。
  - 环境准备(Prerequisite)：[必备][文件]软件使用需要满足的前置条件。
  - 安装(Installation)：[可选][文件]软件的安装方法。
  - 设置(Configuration)：[必备][文件]软件的设置。
- 进阶篇(Advanced)：[可选][目录]又称“开发篇”。提供中高级的开发教程。
  - API(Reference)：[可选][目录/文件]软件 API 的逐一介绍。
  - FAQ：[可选][文件]常见问题解答。
- 附录(Appendix)：[可选][目录]不属于教程本身、但对阅读教程有帮助的内容。
  - Glossary：[可选][文件]名词解释。
  - Recipes：[可选][文件]最佳实践。
  - Troubleshooting：[可选][文件]故障处理。
- ChangeLog：[可选][文件]版本说明。
- Feedback：[可选][文件]反馈方式。

&lt;!-- 采用 HTML 标签的方法来插入图片

&lt;center&gt;&lt;img src=&#34;../assets/content.png&#34; width=&#34;50%&#34; /&gt;&lt;/center&gt; --&gt;

&lt;!-- Hugo 官方提供了一些 shortcodes 短代码，其中就包含插入图片的短代码 figure
&lt;center&gt;{{&lt;figure src=&#34;../assets/content.png&#34; width=&#34;50%&#34; title=&#34;这是一个测试图片，位于assets文件夹下&#34;&gt;}}&lt;/center&gt; --&gt;

&lt;center&gt;{{&lt;figure src=&#34;../assets/content.png&#34; width=&#34;100%&#34; title=&#34;原文截图&#34;&gt;}}&lt;/center&gt;





# 4.正确的github工作流，和开源作者们使用同一套流程



1. git clone // 到本地 
2. git checkout -b xxx 切换至新分支xxx （相当于复制了remote的仓库到本地的xxx分支上 ）
3. 修改或者添加本地代码（部署在硬盘的源文件上） 
4. git diff 查看自己对代码做出的改变 
5. git add 上传更新后的代码至暂存区 
6. git commit 可以将暂存区里更新后的代码更新到本地git 
7. git push origin xxx 将本地的xxxgit分支上传至github上的git

-----------------------------------------------------------

如果在写自己的代码过程中发现远端GitHub上代码出现改变）

git checkout main 切换回main分支 

git pull origin master(main) 将远端修改过的代码再更新到本地 

git checkout xxx 回到xxx分支 

git rebase main 我在xxx分支上，先把main移过来，然后根据我的commit来修改成新的内容 （中途可能会出现，rebase conflict -----》手动选择保留哪段代码） 

git push -f origin xxx 把rebase后并且更新过的代码再push到远端github上 （-f ---》强行） 

原项目主人采用pull request 中的 squash and merge 合并所有不同的commit

----------------------------------------------------------------------------------------------

远端完成更新后 

1.git branch -d xxx 删除本地的git分支

2.git pull origin master 再把远端的最新代码拉至本地





# 5.开源项目选题要求

1.以用户数为标准，选题需要足够窄，然后满足自己的需求，最好是自己用得上的，项目需要持续开发和维护。

2.做好竞品调研，不要重复造轮子。

3.对自己第一个版本的时间要有预估，建议几周到小几个月，沉没成本低，好反馈，时间太长证明选的太大。

4.在用户很少的时候也能成立。如果希望更多人用的话，使用门槛一定要低，也就是面向非程序猿，用户下载之后就能直接用

5.考量自己的支出。比如图床被拉爆。



# 6.如何使用

【【研1基本功 别人不教的，那就我来】SSH&#43;Git&#43;Gitee&#43;Vscode 学会了就是代码管理大师】 https://www.bilibili.com/video/BV1Fw4m1C7Tq/?share_source=copy_web&amp;vd_source=a575ce7a1cd7085db12b84cb640a37ea

代码管理&#43;文献管理


---

> 作者:   
> URL: https://gorantan.github.io/%E4%B8%8D%E4%BD%9C%E4%B8%BAblog%E7%9A%84md/%E7%A8%8B%E5%BA%8F%E5%8D%9A%E5%AE%A2/24%E5%B9%B4/github%E4%BD%BF%E7%94%A8%E6%8A%80%E5%B7%A7/  

