class: middle, center

# 数据科学生命周期

---
# 内容

- 目的和学习内容
- 生命周期
- 小节

---
# 概览
- 目的：从 messy 数据中，获得 insight，帮助决策
- 方法：统计，计算机科学
- 学习：在具体问题（Problem）的上下文（Context）下思考

---
# 发现规律
- 把发现的规律，趋势，推而广之，到更多数据，场合去验证，看它是不是通用的
- 预测
    - 置信区间
    - 预测间隔，训练集-测试集
- 推理（ inference ）
    - 从 sample 到 population
    - A/B 测试

---
# 典型问题
- 有效性问题
  - 疫苗是否有效？
- 可信性问题
  - 新闻是否可信？
- 变化趋势问题
  - 气候如何变化？
- 合理性问题
  - 政策是否合理？

---
class: middle, center
# 数据科学工作流程

.center[.width-80[![](./fig/1-ds-lifecycle.svg)]]

四步：问问题、获得数据、理解数据、理解世界

输出：报告、决策、解决方案

---
# 问题/问题表述

- 想知道什么？
- 要解决什么问题？
- 想测试什么假设？
- 衡量成功的标准是什么？

???
Question/Problem Formulation

- What do we want to know?
- What problems are we trying to solve?
- What hypotheses do we want to test?
- What are our metrics for success?

---
# 核心：提出好的问题
- 四种问题
  - 描述性：房价最近怎么样？
  - 探索性：房价和哪些因素有关？
  - 推理性：房价为什么会跌？
  - 预测性：房价还会再跌吗？

---
# 各个领域的问题
- 社会科学
  - 研究什么现象？
  - 某种人群的特征？
  - 社会行为？
- 自然科学
  - 物理模型？

---
# 好的问题
- 能被数据回答
- 清晰（clear）
- 聚焦（focused）
- 有意义

---
# 数据收集和清洗

- 有哪些数据?
- 需要哪些数据？
- 如何采样更多数据？
- 数据代表我们想要研究的人群吗？

???
- What data do we have and what data do we need?
- How will we sample more data?
- Is our data representative of the population we want to study?

---
# 数据收集和清洗

- 咨询参与研究的人
- 找出要测量什么
- 设计数据收集方法

---
# 探索性数据分析和可视化

- 数据包含什么？是如何组织的?
- 已经有相关数据了吗？
- 数据有哪些偏差、异常或其他问题？
- 如何转换数据以实现有效的分析？

???
- How is our data organized and what does it contain?
- Do we already have relevant data?
- What are the biases, anomalies, or other issues with the data?
- How do we transform the data to enable effective analysis?

---
# 探索性数据分析和可视化

- 这是找到研究思路的关键
- 可视化，发现有趣的模式，趋势，总结数据
    - 描述性分析
    - 探索性的数据分析
- 寻找数据的不足
- 不断迭代
    - 理解数据，回过头来 清洗数据，获得更多数据
    - 基于数据的限制，调整 研究问题

---
# 预测和推理

- 这些数据说明了世界的什么情况？
- 它是否回答了我们的问题，或者准确地解决了问题？
- 我们的结论有多可靠？可以相信这些预测吗？

???
- What does the data say about the world?
- Does it answer our questions or accurately solve the problem?
- How robust are our conclusions and can we trust the predictions? 

---
# 参考材料

- DS100 课堂讲义，Lec01, Note1
- 课本第 1 章