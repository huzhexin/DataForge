# DataForge 仓库

本仓库包含两个互补的数据生产项目：

## [DATA_FORGE/](DATA_FORGE/) —— 弱点驱动的数据生产框架

从基准测试的失败信号中挖掘模型弱点（探针→挖掘→知识库），再让 LLM 按弱点
合成全新领域的难题（五道门 + 剥离），产出"生产者自己解不出"的可验证数据。
详见 [DATA_FORGE/README.md](DATA_FORGE/README.md)。

## [tb_variant_forge/](tb_variant_forge/) —— Terminal-Bench 3.0 任务变体生成器

把 TB 3.0 的 74 道评测题"改头换面"成训练用变体（换皮/改机制两种模式），
**四层质检**：静态五门 → Docker 真跑参考解必须满分 → 空解必须 0 分 →
多模型实测解题打难度分（0.0-1.0 连续标注，不拦截），
不污染原评测集。详见 [tb_variant_forge/README.md](tb_variant_forge/README.md)。

## 两者的关系

DATA_FORGE 回答"该造什么题"（从失败信号定位弱点）；
tb_variant_forge 回答"怎么把已有题改造成新题"（变体 + 四层验证 + 难度标注）。
一个自底向上挖弱点，一个自顶向下改任务，是同一条数据生产流水线的两种打法。
