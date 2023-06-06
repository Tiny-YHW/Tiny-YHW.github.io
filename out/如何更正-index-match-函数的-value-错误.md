---
title: '如何更正 INDEX/MATCH 函数的 #VALUE! 错误'
date: Thu, 14 May 2020 07:58:26 +0000
draft: false
tags: ['Excel+VBA']
---

本主题介绍在一个公式中结合使用 INDEX 和 MATCH 函数时出现 #VALUE! 错误的常见情况。 结合使用 INDEX 和 MATCH 的一个最常见原因是：想要查找一个值，但 VLOOKUP 不起作用（例如，查找的值超过 255 个字符）。

问题：公式尚未作为数组输入
-------------

如果将 INDEX 作为数组公式与 MATCH 配合使用来检索值，需要将公式转换为数组公式，否则会出现 #VALUE! 错误。

**解决方案：**INDEX 和 MATCH 应用作数组公式，这意味着需要按 Ctrl+Shift+Enter。 公式将自动包含在大括号 {} 内。 如果尝试自己输入，Excel 会将公式作为文本显示。![如果在查找值大于 255 个字符时使用 INDEX/MATCH，需要以数组公式的形式输入该值。  单元格 F3 中的公式为 =INDEX(B2:B4,MATCH(TRUE,A2:A4=F2,0),0)，是通过按 Ctrl+Shift+Enter 输入的](https://support.content.office.net/zh-cn/media/a1f388a8-cb26-42d4-a0f6-3b7ff39a6db2.png)

**注意:** 如果您有最新版本的[Microsoft 365](https://products.office.com/en-us/buy/compare-microsoft-office-products)，则只需在输出单元格中输入公式，然后按**enter**将公式确认为动态数组公式。 否则，必须首先选择输出单元格，在输出单元格中输入公式，然后按**CTRL + SHIFT + ENTER**确认该公式，然后才能将公式作为旧数组公式输入。 Excel 将使用括号将公式括起来。 有关数组公式的详细信息，请参阅[数组公式指南和示例](https://support.office.com/zh-cn/article/%E6%95%B0%E7%BB%84%E5%85%AC%E5%BC%8F%E6%8C%87%E5%8D%97%E5%92%8C%E7%A4%BA%E4%BE%8B-7d94a64e-3ff3-4686-9372-ecfd5caa57c7)。