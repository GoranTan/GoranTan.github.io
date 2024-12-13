# 

# 1.背景介绍



**初步想法**：AI大模型&#43;金融/法律。

**初步尝试：**github中找了一些开源的法律金融大模型，效果不佳，维护不好。还可以的是北大的chatlaw大模型，发现了dbgpt的技术，基于豆包的建议，准备尝试做《基于 DB-GPT 的法律案例智能检索与相似性分析系统设计与实现》。

实际上[Chatlaw ——面向未来的法律人工智能](https://www.chatlaw.cloud/)，已经可以做的很好，我想尝试在dbgpt框架下使用代理chatlaw模型，通过工作流和微调实现可以复制的针对于公司内部私域的大模型系统。

![76511f8f38f6dce4a508631823c78bf](https://gorantan-blog.oss-cn-shanghai.aliyuncs.com/pic/20241209083817788.png)

相关资料：

【DB-GPT项目整体介绍】 https://www.bilibili.com/video/BV1Dr421W7mb/?share_source=copy_web&amp;vd_source=a575ce7a1cd7085db12b84cb640a37ea

[DB-GPT开源地址](https://github.com/eosphoros-ai/dbgpts)

[DB-GPT使用文档](https://www.yuque.com/eosphoros/dbgpt-docs/urh3fcx8tu0s9xmb)

[DB-GPT V0.6.0新版本发布, 定义AI原生数据应用新标准](https://www.yuque.com/eosphoros/dbgpt-docs/pfbmw9e9ymy5ggc6)：这个里面有DB-GPT是什么，2. DB-GPT解决了用户哪些核心痛点？它强调的核心价值理念是什么？3. DB-GPT在行业内能对标的竞品有哪些？DB-GPT跟他们相比有什么差异化优势？DB-GPT 有哪些客户在使用？他们使用的场景是什么。这些问题回答的很好。

[基于DB-GPT的财报分析助手](https://www.yuque.com/eosphoros/dbgpt-docs/cmogrzbtmqf057oe)

还有资料是一些对应的bili视频，讲的很棒。

**同时我也可以尝试使用longchain解决同一个任务进行对比。**



# 2.实操



1.按照刚刚的使用文档clone部署。

问题1：使用mysql数据库需要





---

> 作者:   
> URL: https://gorantan.github.io/%E4%B8%8D%E4%BD%9C%E4%B8%BAblog%E7%9A%84md/%E7%A8%8B%E5%BA%8F%E5%8D%9A%E5%AE%A2/%E6%AF%95%E8%AE%BE/%E6%B5%81%E7%A8%8B/  

