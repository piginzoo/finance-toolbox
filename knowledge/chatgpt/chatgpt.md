# ChatGPT中文手册大全

前言

这份资料来自于下方公众号，欢迎扫码关注，了解AI相关的优质学习资源、第一手使用体验。

![](https://img2023.cnblogs.com/blog/1950148/202304/1950148-20230428121433353-264080666.png)





## 第1章 国内可用的ChatGPT网站列表

https://github.com/LiLittleCat/awesome-free-chatgpt

https://lzw.me/x/chatgpt-sites/?type=all



## 第2章 快速了解ChatGPT

https://westudio-docs.oss-cn-beijing.aliyuncs.com/showdoc_e58ecf8153e9ac2ea2a3d2678c4a9fdf.pdf



## 第3章 ChatGPT FAQ

问：chatgpt 国内不开放注册吗？

OpenAI不允许大陆和香港用户注册访问
openai可以的，chatGPT不行

以下国家IP不支持使用 中国(包含港澳台) 俄罗斯 乌克兰 阿富汗 白俄罗斯 委内瑞拉 伊朗 埃及



问：ChatGPT和GPT-3什么关系？

GPT-3是OpenAI推出的AI大语言模型
ChatGPT是在GPT-3基础上构建的聊天应用产品



问：ChatGPT 是免费的吗？

除了付费版本ChatGPT Plus之外，还有一个仅需要登录的免费版本ChatGPT。



问：ChatGPT Plus多少钱？

ChatGPT Plus一个月20美元。开通之前还需要先排队。



问：OpenAI API 和 ChatGPT Plus 计费机制？

OpenAI 的 API 和网页版的 ChatGPT（包括 PLUS）是两套独立系统，功能和计费都是分开的，互相独立，互不影响。API 的试用额度用完了后，是按实际使用量付费的，用多少扣多少。网页版不开 PLUS 可以一直免费用。



问：为什么我的bing看不到ChatGPT？

当前微软仅邀请少量用户参与测试，并未完全开放



问：bing chat和ChatGPT有何不同？

Bing的限制器太多了，回答有諸多限制



问：ChatGPT如何接入微信群？

当前这些微信机器人主要是调用 OpenAI 的GPT-3 API实现的，并不是ChatGPT（基于GPT-3.5）



问：请问 100,000 token 相当于大约多少汉字？

50000



问：ChatGPT 的日常使用示例有哪些？

日常示例包括编程、脚本、电子邮件回复、列表文章、博客创意、摘要等。



问：ChatGPT 有哪些高级用途？

高级使用示例包括调试代码、编程语言、科学概念、复杂问题解决等。



## 第4章 注册ChatGPT全攻略

https://mirror.xyz/boxchen.eth/9O9CSqyKDj4BKUIil7NC1Sa1LJM-3hsPqaeW_QjfFBc

ps. 建议先用上面哪些国内的



## 第5章 ChatGPT Plus注册全攻略

https://mirror.xyz/boxchen.eth/fi-WPM78UeTRwo_r3rNZesrZ_hfQfFltkOT2kb9k6Jk



## 第6章 ChatGPT的提示

### ChatGPT提示学习教程

https://learningprompt.wiki/docs/chatgpt-learning-path



### 常用的提示词

写报告：我现在正在 [报告的情境与目的]。我的简报主题是 [主题]，请提供 [数字] 种开头方式，要简单到 [目标族群] 能听懂，同时要足够能吸引人，让他们愿意专心听下去。

研究报告：写出一篇有关 [知识] 的 [数字] 字研究报告，报告中需引述最新的研究，并引用专家观点。

反对观点：你是 [某个主题] 的专家，请针对以下论述 [附上论述]，提出 [数字] 个反驳的论点，每个论点都要有佐证。

报告总结：你是 [某个主题] 的专家，请总结以下内容，并针对以下内容提出未来能进一步研究的方向 [附上内容]。

搜集资料：给我 [数字] 篇，有关 [领域] 的文章。

内容总结：用列点的方式总结出这篇文章的 [数字] 个重点：[附上文章内容/附上文章网址]。

修改简历：改写以下简历，为每一点加上量化的数据，改写时请维持列点的形式。[附上简历]。

为不同的公司修改不同的简历：我今天要申请 [公司] 的 [职位]，改写以下经历，让我能更符合 [公司] 的企业文化。[附上经历]。

面试题：你现在是 [公司] 的 [职位] 面试官，请分享在 [职位] 面试时最常会问的 [数字] 个问题。

STAR原则回答问题：我在准备 [问题] 这个面试问题，请用 STAR 原则帮我回答这个问题。针对这个问题，我有的经历如下 [附上经历]。

写代码：你现在是一个 [程序语言] 专家，请帮我用 [程序语言] 写一个函式，它需要做到 [某个功能]。

解释代码：你现在是一个 [程序语言] 专家，请告诉我以下的程序在做什么。[附上程序]。

重构代码：你现在是一个 Clean Code 专家，我有以下的程序，请用更干净简洁的方式改写，让我的同事们可以更容易维护程序。另外，也解释为什么你要这样重构，让我能把重构的方式的说明加到 Pull Request 当中。[附上程序]。

解BUG：你现在是一个 [程序语言] 专家，我有一段程序，我预期这段程序可以 [做到某个功能]，只是它通过不了 [测试案例] 这个测试案例。请帮我找出我哪里写错了，以及用正确的方式改写。[附上程序]

写测试：你现在是一个 [程序语言] 专家，我有一段程序 [附上程序]，请帮我写一个测试，请至少提供五个测试案例，同时要包含到极端的状况，让我能够确定这段程序的输出是正确的。

写正则：你现在是一个 Regex 专家，请帮我写一个 Regex ，它能够把 [需求]

解说概念：详细的说明 [填入想了解的知识]

简易教学：你扮演 [科目老师] 的角色， 我需要理解 [理论]。请用 [方式] 方式描述。

深度教学：你是一个 [SEO 专家]，你要教我深度的 [SEO 知识]

教学与测验：教我 [二次方程式]，最后给我一个测验

背单词辅助：用 [中文/英文] 解释以下英文单字：[填入一个或多个单字]。请用表格的方式呈现，并且表格内须包含单字、词性、解释与例句。

模拟英语对话：Can we have a conversation about [话题]?

英文语法修复：Can you check the spelling and grammar in the following text? [附上英文文字]

回复邮件：你是一名 [职业]，我会给你一封电子邮件，你要回覆这封电子邮件。电子邮件：[附上内容]

起标题：写出 [数字] 个有关 [主题] 的 [社群平台] 风格标题，要遵守以下规则：[规则 1]、[规则 2]、[其他规则]。

写大纲：提供 [某主题] 主题的文章大纲

写文章：针对 [主题] 这个主题生成一篇文章

产品文案：将以下产品关键字生成 [数字] 句的产品文案。产品关键字：[附上关键字...]

生成食谱：提供给我一个食谱，食材包含 [食材 1]、[食材 2]、[食材...]。

活动清单：你扮演一位专业的活动企划，请生成 [活动] 活动计划清单，包括重要任务和截止日期。

提供创意点子：提供 [数字] 个 [想法] 的点子

路由计划：生成一份 [数字] 天的 [地点] 旅游计划，交通工具是 [交通工具...]。要遵守以下规则：[填入规则]

写歌词（方文山危）：大家都说我写的歌词像 [人名]，但我最近有点没灵感，请帮我用 [人名] 的风格写一首歌。歌中包含的元素要 [关键字...]。

写故事：写出一篇有关 [故事想法]，拥有 [风格] 风格的短篇故事

写rap：你是现在最红的饶舌歌手，请创作一首 Rap，主题是 [附上主题]。

模拟面试：你现在是一个 [职位] 面试官，而我是要应征 [职位] 的面试者。你需要遵守以下规则：1. 你只能问我有关 [职位] 的面试问题。2. 不需要写解释。3. 你需要向面试官一样等我回答问题，再提问下一个问题。我的第一句话是，你好。

当导游：你是一位导游，我会把我旅游的位置给你，你要推荐一个靠近我位置的地方。在某些情况下，我还会告诉您我想旅游地点的类型。你还会向我推荐靠近我的第一个位置的类似类型的地方。我的第一个需求是[填入需求]



### 写报告的提示例子

1、我现在正在 [报告的情境与目的]。我的简报主题是 [主题]，请提供 [数字] 种开头方式，要简单到 [目标族群] 能听懂，同时要足够能吸引人，让他们愿意专心听下去



我现在正在修台大的简报课，其中一项作业是要做一份让小学生能听懂的简报。我的简报主题是机会成本，请提供三种开头方式，要简单到小学生能听懂，同时要足够能吸引人，让他们愿意专心听下去



2、写出一篇有关 [知识] 的 [数字] 字研究报告，报告中需引述最新的研究，并引用专家观点



写出一篇有关自动驾驶的 300 字研究报告，报告中需引述最新的研究，并引用专家观点



3、你是 [某个主题] 的专家，请针对以下论述 [附上论述]，提出 [数字] 个反驳的论点，每个论点都要有佐证



你是大数据分析的专家，请针对以下论述「在数据分析中，越多数据越好」，提出 3 个反驳的论点，每个论点都要有佐证



4、你是 [某个主题] 的专家，请总结以下内容，并针对以下内容提出未来能进一步研究的方向 [附上内容]



你是金融科技专家，请总结以下内容，并针对以下内容提出未来能进一步研究的方向 [附上内容]



### 资料整理的提示例子

1、给我 [数字] 篇，有关 [领域] 的文章。



给我 5 篇，有关 SEO 的文章。



2、用列点的方式总结出这篇文章的 [数字] 个重点：[附上文章内容/附上文章网址]。



用列点的方式总结出这篇文章的 5 个重点：[附上文章内容/附上文章网址]。



3、用列点的方式总结出 [数字] 个 [领域] 知识重点



用列点的方式总结出 10 个量子力学知识重点。



使用示例：

![img](https://pic3.zhimg.com/80/v2-1c57f9cda2eef42573d3541ced489152_1440w.webp)



### 简历与自传的提示例子

1、这份 [职位] 的简历，有哪边可以写更好? 请以专业面试官的角度，提出具体改进建议。接着以你提出的建议来改写这段经历，改写时请维持列点的形式。[附上简历]



这份 UIUX 设计师的简历，有哪边可以写更好? 请以专业面试官的角度，提出具体改进建议。接着以你提出的建议来改写这段经历，改写时请维持列点的形式。



2、改写以下简历，为每一点加上量化的数据，改写时请维持列点的形式。[附上简历]



3、把这段经历写得更精简一点，让别人可以马上看到重点，同时维持生动的描述。[附上经历]



4、为不同公司定制化撰写简历



我今天要申请[公司]的[职位]，改写以下经历，让我能更符合[公司]的企业文化。[附上经历]



我今天要申请 Google 的前端工程师，改写以下经历，让我能更符合 Google 的企业文化。[附上经历]



### 准备面试的提示例子

1、你现在是[公司]的[职位]面试官，请分享在[职位]面试时最常会问的[数字]个问题。



你现在是 Google 的产品经理面试官，请分享在 Google 产品经理面试时最常会问的 5 个问题。



2、我针对 [问题] 的回答，有哪些可以改进的地方? [附上回答]



我针对「你会如何排定不同产品功能优先顺序?」的回答，有哪些可以改进的地方? [附上回答]



3、针对 [问题] 这个面试问题，请提供一些常见的追问面试题。



针对「你会如何排定不同产品功能优先顺序?」这个面试问题，请提供一些常见的追问面试题。



4、我在准备 [问题] 这个面试问题，请用 STAR 原则帮我回答这个问题。针对这个问题，我有的经历如下 [附上经历]



我在准备「请分享一个你在急迫的期限中完成专案的经验」这个面试问题，请用 STAR 原则帮我回答这个问题。针对这个问题，我有的经历如下 [附上经历]。



### 编程的提示例子

1、你现在是一个 [程式语言] 专家，请帮我用 [程式语言] 写一个函式，它需要做到 [某个功能]



你现在是一个 JavaScript 专家，请帮我用 JavaScript 写一个函式，它需要做到 输入一个一维阵列，把这个一维阵列转换成二维阵列。同时我要能够自由地决定二维阵列中的子阵列长度是多少



2、你现在是一个 [程式语言] 专家，请告诉我以下的程式码在做什么。[附上程式码]



3、你现在是一个 Clean Code 专家，我有以下的程式码，请用更干净简洁的方式改写，让我的同事们可以更容易维护程式码。另外，也解释为什么你要这样重构，让我能把重构的方式的说明加到 Pull Request 当中。[附上程式码]



4、你现在是一个 [程式语言] 专家，我有一段程式码，我预期这段程式码可以 [做到某个功能]，只是它通过不了 [测试案例] 这个测试案例。请帮我找出我哪里写错了，以及用正确的方式改写。[附上程式码]



你现在是一个 python 专家，我有一段程式码，我预期这段程式码可以判断一个字串是不是镜像回文，只是它通过不了 aacdeedcc 这个测试案例。请帮我找出我哪里写错了，以及用正确的方式改写。[附上程式码]



5、你现在是一个 [程式语言] 专家，我有一段程式码 [附上程式码]，请帮我写一个测试，请至少提供五个测试案例，同时要包含到极端的状况，让我能够确定这段程式码的输出是正确的。



6、你现在是一个 Regex 专家，请帮我写一个 Regex ，它能够把 [需求]



你现在是一个 Regex 专家，请帮我写一个 Regex ，它能够把输入一个字串，把这个字串中的所有数字都取出来



### 学习知识的提示例子

1、详细的说明 [填入想了解的知识]



详细的说明如何制造一台电脑



2、你扮演 [科目老师] 的角色， 我需要理解 [理论]。请用 [方式] 方式描述。



你扮演数学老师的角色， 我需要理解一元二次方程式。请用浅显易懂方式描述。



3、你是一个 [SEO] 专家，你要教我深度的 [SEO] 知识



你是一个 SEO 专家，你要教我深度的 SEO 知识。



4、教我 [二次方程式]，最后给我一个测验



教我 一元二次方程式，最后给我一个测验



### 英语学习的提示例子

1、用 [中文/英文] 解释以下英文单字：[填入一个或多个单字]。请用表格的方式呈现，并且表格内须包含单字、词性、解释与例句。



用中文解释以下英文单字：apple, orange, doctor, car, run。请用表格的方式呈现，并且表格内须包含单字、词性、解释与例句。



2、解释英文单字 [英文单字]，并且给我 [数字] 个常用句子



解释英文单字 divest，并且给我 5 个常用句子。



3、英语对话



Can we have a conversation about 话题?



Can we have a conversation about machine learning?



4、校阅英文文法



Can you check the spelling and grammar in the following text? [附上英文文字]



5、英文作文修改与解释



校阅以下英文文章，并用表格的方式呈现，要有三个栏位，分别是原文、修正后的版本，以及用中文详解为什么要这样修改：附上英文文章



6、纠正文法和拼字错误



Please correct my grammar and spelling mistakes in the text above: 附上英文文字



Please correct my grammar and spelling mistakes in the text above: I love eat fooded



### 写邮件的提示例子

1、回复 Email



你是一名 [职业]，我会给你一封电子邮件，你要回复这封电子邮件。电子邮件：[附上内容]



你是一名产品经理，我会给你一封电子邮件，你要回覆这封电子邮件。电子邮件：[附上内容]



### 写作帮手的提示例子

1、撰写标题



写出 数字 个有关 主题 的 社群平台 风格标题，要遵守以下规则：规则 1、规则 2、其他规则。



写出 5 个有关日本迪士尼旅游心得的 Instagram 风格标题，要遵守以下规则：标题不超过 20 字、标题要加上适当表情符号。



2、撰写文章大纲



提供 [某主题] 主题的文章大纲



提供美国留学主题的文章大纲



3、文章撰写



针对 [主题] 这个主题生成一篇文章



针对使用 ChatGPT 小诀窍这个主题生成一篇文章



4、产品文案



将以下产品关键字生成 数字 句的产品文案。产品关键字：附上关键字…



将以下产品关键字生成 10 句的产品文案。产品关键字：球鞋、春季最新款、多种颜色、适合慢跑



### 日常生活的提示例子

1、食谱生成



提供给我一个食谱，食材包含 食材 1、食材 2、食材…。



提供给我一个食谱，食材包含鸡腿肉、鸡蛋、起司。



2、提供食谱



请列出这份食谱的采买清单和步骤：数字 人份的 食谱。



请列出这份食谱的采买清单和步骤：1 人份的蕃茄炒蛋。



3、活动计划清单



你扮演一位专业的活动企划，请生成 活动 活动计划清单，包括重要任务和截止日期。



你扮演一位专业的活动企划，请生成运动会活动计划清单，包括重要任务和截止日期。



4、提供点子



提供 [数字] 个 [想法] 的点子



提供 5 个情人节的点子



5、旅游计划



生成一份 数字 天的 地点 旅游计划，交通工具是 交通工具…。要遵守以下规则：填入规则



生成一份 5 天的东京旅游计画，交通工具是地铁和火车。要遵守以下规则：1. 地点要包含东京铁塔、富士山、迪士尼乐园 2. 需要包含交通如何乘坐 3. 一天不超过 3 个地点。



### 有趣好玩的提示例子

1、写歌词



大家都说我写的歌词像 人名，但我最近有点没灵感，请帮我用 人名 的风格写一首歌。歌中包含的元素要 关键字…。



大家都说我写的歌词像方文山，但我最近有点没灵感，请帮我用方文山的风格写一首歌。歌中包含的元素要有别离、思念、峰回路转。



2、写故事



写出一篇有关 故事想法，拥有 风格 风格的短篇故事



写出一篇有关工程师拯救这个世界的短篇故事



3、写 rap



你是现在最红的饶舌歌手，请创作一首 Rap，主题是 附上主题。



你是现在最红的饶舌歌手，请创作一首 Rap，主题是孤勇者。



### 角色扮演的提示例子

1、综合情境



你现在是一名 角色，你要针对我提出的问题提供建议。我的问题是：附上问题。



你现在是一名生涯教练，你要针对我提出的问题提供建议。我的问题是：我是否要出国念书？



2、面试官



你现在是一个 职位 面试官，而我是要应征 职位 的面试者。你需要遵守以下规则：1. 你只能问我有关 职位 的面试问题。2. 不需要写解释。3. 你需要向面试官一样等我回答问题，再提问下一个问题。我的第一句话是，你好。



你现在是一个产品经理面试官，而我是要应征产品经理的面试者。你需要遵守以下规则：



你需要向面试官一样等我回答问题，再提问下一个问题。我的第一句话是，你好。



### 学习提示的网站

万字干货-ChatGPT 从零完全上手实操指南！：https://zhuanlan.zhihu.com/p/623911710

ps. 用好提示词和调教AI的套路，必看好文



学习提示工程：https://learnprompting.org/zh-Hans/docs/intro

让生产力加倍的 ChatGPT 快捷指令：https://www.aishort.top/

提示工程-介绍人类该如何与LLM交互：https://www.zhihu.com/column/c_1624986864754065408



官方例子：https://platform.openai.com/examples

英文提示：https://prompts.chat/



## 第7章 ChatGPT是怎样被训练出来的？

https://www.bilibili.com/video/BV1BG4y137SH/



## 第8章 ChatGPT个人使用场景分享

https://hubeiqiao.notion.site/ChatGPT-c13f60d4adc14eb0ae73a58dca3a54af



## 第9章 用ChatGPT搞钱

想用ChatGPT搞钱？没那么简单。小心钱没赚到，反而被别人隔了韭菜。

强烈建议先看看这个视频，了解一下别人的套路。

### 我花了几百块买ChatGPT赚钱课，结果卖课的摊牌了

https://www.bilibili.com/video/BV1Fz4y1Y7KY



用ChatGPT赚钱的人确实有，属于少数，一般需要几个前提条件：动手要快、多尝试、之前有沉淀。

### 通过ChatGPT赚钱，写短篇小说赚钱很快

https://www.bilibili.com/video/BV1ZY411v7FL



### 用ChatGPT在闲鱼接单赚钱？

https://www.bilibili.com/video/BV1T24y1v7oT



### ChatGPT赚钱小工具： 自动写作 批量制作短视频 写代码整理数据

https://www.bilibili.com/video/BV1vG4y1U75R/



### 用ChatGPT薅百家号羊毛

https://www.bilibili.com/video/BV12d4y1Y7Hv/



### ChatGPT 搞钱思路分享

https://www.bilibili.com/video/BV1qR4y1z7kC



### 盗版致富？套壳ChatGPT有多赚钱！

https://www.bilibili.com/video/BV1zs4y1Z7WA



## 第10章 ChatGPT能做的49件事

![](https://img2023.cnblogs.com/blog/1950148/202304/1950148-20230428121238969-1498347093.png)



## 第11章 ChatGPT改变人的阅读方式

https://learningprompt.wiki/docs/insight/AI%20%E6%9C%89%E5%8F%AF%E8%83%BD%E6%94%B9%E5%8F%98%E4%BA%BA%E7%9A%84%E5%AD%A6%E4%B9%A0%E6%96%B9%E5%BC%8F%E5%90%97%EF%BC%9F/%E6%9C%89%E5%8F%AF%E8%83%BD%E6%94%B9%E5%8F%98%E4%BA%BA%E7%9A%84%E9%98%85%E8%AF%BB%E6%96%B9%E5%BC%8F%E5%90%97%EF%BC%9F



## 第12章 用ChatGPT改简历、提高面试邀请率

下面是一名外国兄弟的经历：

我一直用ChatGPT来申请工作，我会把我的简历和JD（Job Description）发给它，然后要求ChatGPT根据我的简历和工作经验，对这个岗位进行量身定制。

我要求它为每个可能的问题提供出色的回答，这些回答必须来自我的简历和经验，以便证明我完美地适合这个岗位。

同时，要使用STAR框架为每个问题提供例子。

注：“STAR”是situation（背景）、task（任务）、action（行动）和result(结果)这四个英文单词的首字母缩写，是标准化面试中的重要方法。

我要求它让我的申请令人惊叹，脱颖而出，让面试官印象深刻。

然后，我随意地找了一些招聘需求，发了申请，你猜结果怎么样？

对于一些我自己都觉得没法胜任的工作，我居然收到了大量的面试邀请！

对于大多数情况，我收到的反馈都是“非常出色”，并表示“我们对您的申请及您提供的例子印象非常深刻”，每次看到这些反馈，我都忍不住发笑。

悲催的是，我在真正的面试中表现很糟糕，我非常的焦虑和慌乱，是表现最差的人。

————————

看样子，这个外国兄弟的简历被ChatGPT给过度美化了，不过他的这个思路可以借鉴。



## 第13章 如何让GPT4写出更生动的故事

![](https://img2023.cnblogs.com/blog/1950148/202304/1950148-20230428121343717-661541890.png)



## 第14章 用ChatGPT创作歌曲

用ChatGPT模仿李荣浩写一首歌：https://www.bilibili.com/video/BV1k24y1W7FK

直接用ChatGPT写的歌原来是这样的：https://www.bilibili.com/video/BV13A411z7qy

五分钟教你用AI创作音乐！：https://www.bilibili.com/video/BV1He4y1F7DU



## 第15章 重度使用ChatGPT心得

https://twitter.com/0x_Todd/status/1640710775697444866

ps. 内容是中文的，放心。



## 第16章 用ChatGPT辅助做Codeforces

https://zhuanlan.zhihu.com/p/614608835



## 第17章 提高阅读PDF的效率

ChatPDF——上传pdf，然后你就可以基于pdf的内容去提问了：https://www.chatpdf.com/



## 第18章 用ChatGPT画流程图

https://zhuanlan.zhihu.com/p/623026095



## 第19章 用ChatGPT制作PPT

https://zhuanlan.zhihu.com/p/618679097



## 第20章 用ChatGPT快速批量生成短视频

https://zhuanlan.zhihu.com/p/618796883



## 第21章 Chrome上5款好用的ChatGPT插件

https://www.youtube.com/watch?v=JTPzbP_q4W0

ps. 中文视频



## 第22章 基于ChatGPT的有意思小产品

https://www.bilibili.com/video/BV1Dd4y1e76j/

视频相关内容： 

1. VSCode扩展: https://github.com/mpociot/chatgpt-vscode
2. B 站评论自动回复，基于Python ChatGPT Lib : https://github.com/acheong08/ChatGPT
3. Mac上的菜单栏: https://github.com/vincelwt/chatgpt-mac
4. 微信机器人：https://github.com/fuergaosi233/wechat-chatgpt
5. 生成推荐域名网站：https://smartynames.com/
6. Google搜索自动显示：https://github.com/wong2/chat-gpt-google-extension
7. 和ChatGPT语音对话: https://huggingface.co/spaces/sanchit-gandhi/chatGPT



## 第23章 ChatGPT API Demo

ChatGPT API 由 OpenAI 广受欢迎的 ChatGPT 背后的相同人工智能模型提供支持，该模型被称为“gpt-3.5-turbo”。
GPT-3.5是 OpenAI 目前通过其 API 套件提供的最强大的文本生成模型；“turbo”绰号指的是GPT-3.5 的优化、响应速度更快的版本，OpenAI 一直在为 ChatGPT 悄悄测试它。
价格为每 1,000 个令牌 0.002 美元，或大约 750 个单词，OpenAI 称该 API 可以推动一系列体验，包括“非聊天”应用程序。Snap、Quizlet、Instacart 和 Shopify 是早期采用者。

使用新的官方 ChatGPT API 在 huggingface 上构建了一个简单的聊天机器人演示：

https://huggingface.co/spaces/anzorq/chatgpt-demo



## 第24章 体验评测

体验了一把MiniGPT-4，一言难尽：https://mp.weixin.qq.com/s?__biz=Mzg2MTU5ODg2Nw==&mid=2247483696&idx=1&sn=996e9b80268f5689ff496b072dd25e4a&chksm=ce15e4ccf9626dda4c2520bf6dc14554b84e931b61cda4d3ff4a7b0af11023353b36f098150d#rd

来自微软和浙大的Jarvis：ChatGPT也有队友了：https://mp.weixin.qq.com/s?__biz=Mzg2MTU5ODg2Nw==&mid=2247483714&idx=1&sn=0b9b0f88c6b391d87e1a6d497ff8387e&chksm=ce15e4bef9626da88b80809d36b0f609011474fb6c14a6a3943c21aa35096e2c142ccfdf641e&token=338987574&lang=zh_CN#rd



## 第25章 深度文章

AI大模型创业的生死5问：https://mp.weixin.qq.com/s/awbpnSJfJFtnPdhdC0OAjw

ChatGPT在做什么...为什么它能够成功：https://zhuanlan.zhihu.com/p/607601817

万字长文，探讨关于ChatGPT的五个最核心问题：https://zhuanlan.zhihu.com/p/612028498



## 第26章 Midjourney 学习导航

https://learningprompt.wiki/docs/midjourney-learning-path



## 第27章 AI工具资源

### AI工具导航

All Things AI：https://allthingsai.com/

AI Tools：https://doc.clickup.com/37456139/d/h/13q28b-164/972da0c0d0a4eb8



### 编程工具列表

1. Tabnine: https://www.tabnine.com/
2. OpenAI Codex: https://openai.com/blog/openai-codex/
3. GitHub Copilot: https://github.com/features/copilot
4. AI Commit: https://github.com/abi/autocommit
5. DeepCode: https://www.deepcode.ai/
6. AI2Sql: https://www.ai2sql.io/
7. Replit: https://replit.com/site/ghostwriter
8. Akkio: https://www.akkio.com/
9. Httpie: https://httpie.io/blog/ai
10. Mutable: https://mutable.ai/
11. Sheetplus: https://sheetplus.ai/
12. ExcelFormulaBot: https://excelformulabot.com/



### 日常办公工具列表

1. Notion AI: https://www.notion.so/product/ai
2. Craft: https://www.craft.do/
3. Mem: https://mem.ai/
4. Taskade: https://www.taskade.com/
5. You: https://you.com/
6. Todoist: https://todoist.com/integrations/apps/ai-assistant



### 写作工具列表

1. Copy AI : https://www.copy.ai/
2. Jasper: https://www.jasper.ai/
3. WriteSonic: https://writesonic.com/
4. ChatGPT3: https://chat.openai.com/
5. Headlime: https://headlime.com/
6. PepperType: https://peppertype.ai/
7. MarkCopy: https://www.markcopy.ai/
8. Quillbot: https://quillbot.com/
9. Rytr: https://rytr.me/
10. MoonBeam: https://www.gomoonbeam.com/
11. Simplified : https://simplified.com/ai-writer/
12. Lex Page: https://lex.page/
13. Copy Smith: https://copysmith.ai/
14. Subtxt: https://subtxt.app/
15. Ellie Email Assistant: https://tryellie.com/
16. Wordtune: https://www.wordtune.com/
17. Sudowrite: https://www.sudowrite.com/
18. Novel: https://novelai.net/
19. Compose: https://www.compose.ai/



### 图像生成处理工具列表

1. Profile Picture: https://www.profilepicture.ai/
2. Photosonic: https://photosonic.writesonic.com/
3. Remove BG: https://www.remove.bg/
4. Artbreeder: https://www.artbreeder.com/
5. Magiceraser: https://magicstudio.com/magiceraser
6. Krea: https://www.krea.ai/
7. Lexica: https://lexica.art/
8. Removal: https://removal.ai/
9. Image Enlarger: https://imglarger.com/
10. Watermark Removal : https://www.watermarkremover.io/
11. Rodebudai: https://www.rosebudai.com/
12. Hypotenuse: https://www.hypotenuse.ai/
13. Nyx: https://nyx.gallery/
14. AI Avatar: https://avatarai.me/
15. Cutout Pro: https://www.cutout.pro/
16. Passport Photo: https://passphoto.ai/
17. Picso: https://picso.ai/
18. Playground: https://www.playgroundai.com/
19. Runway: https://runwayml.com/
20. Profile Pic Maker: https://pfpmaker.com/
21. HotPot: https://hotpot.ai/
22. Mage: https://www.mage.space/



### 市场营销工具列表

1. Frase: https://www.frase.io/
2. Bertha: https://bertha.ai/
3. ContentEdge: https://www.contentedge.com/
4. Hemingwayapp: https://hemingwayapp.com/
5. Surfer SEO: https://surferseo.com/
6. Ponzu: https://www.ponzu.ai/
7. Jasper: https://www.jasper.ai/
8. Copy Smith: https://copysmith.ai/
9. PepperType: https://peppertype.ai/
10. Scalenut: https://www.scalenut.com/
11. Mutiny: https://www.mutinyhq.com/
12. Simplified : https://simplified.com/ai-writer/
13. MoonBeam: https://www.gomoonbeam.com/
14. Smartly: https://www.smartly.io/
15. Seventh Sense: https://www.theseventhsense.com/
16. Copy AI : https://www.copy.ai/
17. MarketMuse: https://www.marketmuse.com/
18. WriteSonic: https://writesonic.com/
19. Phrasee: https://phrasee.co/



### 销售工具列表

1. Creatext: https://www.creatext.ai/
2. Exceed: https://exceed.ai/
3. Creaitor: https://www.creaitor.ai/
4. Twain: https://www.usetwain.com/
5. Lavender: https://www.lavender.ai/
6. Regie: https://www.regie.ai/
7. People: http://people.ai/
8. Smartwriter: https://www.smartwriter.ai/
9. Octane: https://www.octaneai.com/
10. Warmer: http://warmer.ai/



### 演讲工具列表

1. Resemble: https://www.resemble.ai/
2. Broadn: https://www.broadn.io/
3. Podcast: https://podcast.ai/
4. Fliki: https://fliki.ai/
5. Wellsaidlabs: https://wellsaidlabs.com/
6. Voicemod: https://www.voicemod.net/ai-voices/
7. Otter: https://otter.ai/
8. TLDR This: https://tldrthis.com/
9. Glasp AI: https://glasp.co/ai-summary
10. Sembly: https://www.sembly.ai/
11. Summari: https://www.summari.com/products/chrome
12. Coqui: https://coqui.ai/



### 设计工具列表

1. Diagram: https://diagram.com/
2. Vizcom: https://www.vizcom.ai/
3. Namelix: https://namelix.com/
4. Aragon: https://www.aragon.ai/
5. Interior Design: https://interiorai.com/
6. Visualize: https://visualise.ai/
7. Lexica: https://lexica.art/
8. Poly: https://poly.ai/
9. Looka: https://looka.com/
10. Stock AI: https://stockimg.ai/



### 聊天机器人工具列表

1. Landbot: https://landbot.io/
2. Cresta: https://cresta.com/
3. Kaizan: https://kaizan.ai/
4. WotNot: https://wotnot.io/
5. Cohere: https://cohere.ai/
6. Tidio: https://www.tidio.com/
7. Typewise: https://www.typewise.app/
8. Quickchat: https://www.quickchat.ai/



欢迎扫码关注，了解AI相关的优质学习资源、第一手使用体验。

![](https://img2023.cnblogs.com/blog/1950148/202304/1950148-20230428121433353-264080666.png)