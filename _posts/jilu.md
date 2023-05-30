---
layout: post
title: 记录一些测试结果
categories: [java]
description: 记录一些测试结果description。
keywords: java, GitHub Copilot
mermaid: false
sequence: false
flow: false
mathjax: false
mindmap: false
mindmap2: false
---

测试文本

如何新建一篇文章
在_post文件夹内新建md文件即可生成一个新的文章

格式要求
貌似.md文件名禁止使用中文

文章基本信息怎么定义
title:这里代表文章标题


选择Preferences-Package Settings-LiveReload-Plugins-enable


##标题
#一级标题
## 二级标题
### 三级标题
###### 六级标题




```java
public void error(String format, Object... arguments);
```

经过分析及实际运行验证：

- AI 生成的代码可以按期望效果打印；
- 如果有比占位符多的非 Throwable 类型参数，会被忽略掉。