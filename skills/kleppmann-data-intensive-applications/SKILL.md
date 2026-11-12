---
name: kleppmann-data-intensive-applications
description: "数据密集型系统设计：可靠性、数据模型、索引、复制、分区、事务、一致性、批流处理与正确性；用于逐章学习及架构权衡。回答前读取相关章节，区分书中观点、案例与应用推演。"
---

# Designing Data-Intensive Applications

作者：Martin Kleppmann。基于用户提供的本地OCR文本，共12章。优先用本技能做逐章学习、概念自测与项目诊断。

## 调用规则

1. 任何具体问题先读对应章节；跨主题读最相关的2–3章，并查看术语表或方法库。
2. 逐章学习采用“解释一个判断→重构一个例子→提问检查理解→给一个练习”的节奏；等待用户作答再给反馈。
3. 原句、数值、故事细节、代码或争议观点必须用[原文读取工具](scripts/read_source.py)按章节行号核对。工具需要本机匹配的原始OCR；无法访问时明确说明不能核验。
4. 区分作者观点、书中引用/案例、本技能推演、今天的事实。OCR图像未读取，不能声称已核对图表或印刷页码。
5. 面对现实项目，以用户目标和现有证据开始；信息不足时标注假设，提出一个可验证的下一步。

## 核心框架

- **可靠性/扩展性/维护性**：先明确负载和故障场景；对峰值、尾延迟与运营复杂度分开评估。 [第1章](chapters/ch01.md)
- **数据模型与存储**：关系、文档、图、B树、LSM树、列式存储分别服务不同查询和写入模式。 [第2章](chapters/ch02.md)–[第3章](chapters/ch03.md)
- **模式演进**：编码格式与新旧版本并存影响持久数据和服务通信。[第4章](chapters/ch04.md)
- **分布式权衡**：复制、分区提升可用性和容量，但带来冲突、热点、故障与一致性问题。 [第5章](chapters/ch05.md)–[第9章](chapters/ch09.md)
- **事务与共识**：明确应用需要避免哪类并发异常，再选择隔离级别和协调机制。 [第7章](chapters/ch07.md)–[第9章](chapters/ch09.md)
- **派生数据**：批处理、流处理和端到端正确性决定数据变化怎样可靠传递。 [第10章](chapters/ch10.md)–[第12章](chapters/ch12.md)

## 章节导航

|章|主题|关键判断|
|---|---|---|
|[01](chapters/ch01.md)|Reliable, Scalable, and Maintainable Applications|可靠性、可伸缩性、可维护性是数据系统的不同目标。|
|[02](chapters/ch02.md)|Data Models and Query Languages|关系、文档、图等数据模型适配不同关系和查询需求。|
|[03](chapters/ch03.md)|Storage and Retrieval|B树、LSM树和列式存储针对读写与分析负载有不同代价。|
|[04](chapters/ch04.md)|Encoding and Evolution|编码与模式演进决定新旧程序和持久数据能否兼容。|
|[05](chapters/ch05.md)|Replication|复制提升可用性与读取能力，同时引入滞后和冲突。|
|[06](chapters/ch06.md)|Partitioning|分区扩大容量，也使热点、二级索引和再平衡更复杂。|
|[07](chapters/ch07.md)|Transactions|事务是对多个读写提供有意义的安全保证。|
|[08](chapters/ch08.md)|The Trouble with Distributed Systems|分布式系统必须面对不可靠网络、时钟和进程暂停。|
|[09](chapters/ch09.md)|Consistency and Consensus|一致性和共识用于在故障下协调顺序与决策。|
|[10](chapters/ch10.md)|Batch Processing|批处理适合对有界数据集做可重算的衍生视图。|
|[11](chapters/ch11.md)|Stream Processing|流处理面向持续事件与时间语义。|
|[12](chapters/ch12.md)|The Future of Data Systems|未来的数据系统应重视正确性、可演进的数据流与人的权利。|

## 资料

- [核心框架细读](references/deep-frameworks.md)
- [术语表](glossary.md)
- [方法库](patterns.md)
- [决策速查](cheatsheet.md)
- [来源质量](references/source-quality.md)
- [章段与哈希清单](references/source-manifest.json)

不同书籍间的内容不可混用作者、命名或案例。若只问“从头学习”，从第1章开始。
