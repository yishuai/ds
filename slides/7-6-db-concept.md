class: middle, center

# 数据库概念

---
# 数据库原理

- 为什么用数据库？
- 数据库设计的四个阶段
- 需求工程
- 实体关系模型
- 逻辑和物理建模

---
# 为什么用数据库？
- 可扩展
  - 可以处理更大规模的数据
  - 现代数据库管理系统 (DBMS) 可以处理数百 TB 数据（并且还在不断增长）存储的数十亿条记录
- 数据分布在 DBMS管理的许多（100-1000）节点上
  - 有复杂的算法，管理存在硬盘上的数据
- Pandas 处理不过来

---
# 为什么用数据库？
- 完整
  - 数据一致，没有不必要的重复，格式统一
  - 数据恢复机制
  - 如果计算机在 SQL 操作过程中崩溃，数据库系统可以恢复尽可能多的数据
- 易于更新和访问
  - 能够有效地添加、删除、更新和访问记录，同时保持完整性
- 允许多个用户并发访问
- 各种组织都在使用 SQL 数据库

---
# 数据库设计的四个阶段

- 需求工程
  - 理解需求
- 概念建模
  - 实体关系（ER）模型
- 逻辑和物理建模
  - 逻辑设计（Schema、表名、数据类型）
  - 物理设计（索引、提示、内存组织）
- 数据访问和分析
  - 提出和回答问题（Query）
  - 从 DBMS 中提取信息（View）
  - SQL 和关系代数

---
# 需求工程

- 职责簿：Book of Duty
- 对数据库系统总体以及所需的访问/交互方式的描述
  - 描述可以是非正式的，但应该详细
  - 描述信息要求

---
# 职责簿

- 记录的条目（Item）
  - 如：商品、销售记录
- 包括的概念
  - 如：物品、存储设施、学生、课程
- 概念的属性
  - 如：价格、颜色、姓名，年级

---
# 职责簿

- 属性的类型和范围
  - 如：字母、整数、日期
- 如何识别/引用对象？
  - 如：ID、DOI、身份证号码
- 概念之间的关系
  - 如：与“书“有关的概念及关系：作者、制造商、分销商、出版商……

???
- 基数：系统预计管理多少项目？
  - 例如。 # 学生大学数据库、# 商品在线商店、# 流媒体平台上的电影数量；
  - 估计值而不是精确值：作为指导有意义
- 发行版
  - 如：班级中的成绩分布、一天中的订单请求数量
- 工作量
  - 读/写频率
- 优先级和服务水平协议
  - 是否存在不同层次的用户？
  - 服务上应有哪些保障？
  - 用户和记录的隐私

---
# 概念建模

- 实体 - 关系（ER）模型
  - 将 DBMS 视为一组表
  - 每个表称为一个关系

???

Brown Entity-Relationship (ER) model PPT
https://static.us.edusercontent.com/files/KY0L3oeXWDyehguFptxYuOsM

---
# 逻辑和物理建模

- 逻辑设计
  - Schema、表、数据类型
- 物理设计
  - 索引、提示、存储组织

---
# Schema

- 表的结构
- 每一列是一个属性
- PRIMARY 属性
  - 不能为空
  - 取值唯一


    CREATE TABLE company
      (id INT PRIMARY KEY NOT NULL,
       name TEXT NOT NULL);

---
# 数据类型
- 数字
  - INT、FLOAT、REAL、DOUBLE
- 字符串：
  - CHAR(n)、VARCHAR(n)、CLOB(大小)
    - CHAR：字段长度是固定。无论存储字符串长度多少，CHAR(10) 都会占用 10 个字符的空间，剩余空间用空格填充，适用于存储长度固定的数据，例如国家代码、邮政编码等
    - VARCHAR：长度不固定
    - CLOB(2MB)：用于大型对象，例如文档/网页

---
# 数据类型
- 位串
  - BIT(n)、BIT VARYING(n)、BLOB
    - BLOB(20MB) 例如图像
- 布尔值
- 日期
  - DATE, TIME, TIMESTAMP, TIME WITH TIME ZONE
- 正确选择数据类型可以提高性能和内存利用率

---
# 数据访问和分析

- 提出和回答问题（Query）
- 从 DBMS 中提取信息（Views）
- SQL 和关系代数

---
# 小结

- 为什么用数据库？
- 数据库设计的四个阶段
- 需求工程
- 实体关系模型
- 逻辑和物理建模

---
class: middle, center

# 作业

---
# 作业 I：职场练习

- 你心仪的职位接触的数据量多大？需不需要数据库？为什么？
- 你心仪的职位可能接触到什么数据库？请给出该数据库的设计方案，包括需求工程、实体关系模型和逻辑/物理建模
- 基于上述内容，按 STAR 原则，写作 50 字的简历内容。简历内容需要言简意赅，很有吸引力。具体要求请参见《AI 帮工作 1：求职和申请》教程的 7-11 页，[链接](https://yishuai.github.io/talk/ai-career/index.html?p=4-1-apply.md#7)
- 作业提交链接：[【腾讯文档】作业：数据库设计](https://docs.qq.com/form/page/DT2R0alJ1V0NUaFlF)
- 提示：请全程由 AI 辅助

???

Brown Database design and SQL PPT, (https://static.us.edusercontent.com/files/XBgBfPoOnMn8NnjwQZNluB6a)

Database design principles

- Why databases?
- Four main phases of database design
- Book of duty
- Entity relation model
- Physical layer

Why databases?

- Scalability: Modern database need to handle efficiently tens of billions of records
    - Modern Data Base Management Systems (DBMSs) need to handle billions of records stored using hundreds of terabytes of data (and growing)
    - Data must be distributed over many (100s-1000s) of nodes managed by (DBMSs)

- Integrity: Consistent data, no unwanted repetitions, uniform formatting
- Ease of update & of access: It must be possible to add, remove, update and access record efficiently and while preserving integrity
- Allow for concurrent accesses by multiple users

Four main phases of database design

- Requirement Engineering
  - “Book of duty”
  - Understand and model the “world” of interest

- Conceptual Modeling
  - Conceptual DB design
  - Entity Relations (ER) method

- Logical an Physical Modeling
  - Logical design (schema, table names, data types)
  - Physical design (index, hints, memory organization)

- Data access and analysis
  - Asking and answering questions (queries) 
  - Extract information form the DBMS (views)
  - SQL and relational algebra

Requirement Engineering

- “Book of duty”
- Understand and model the “world” of interest

Book of duty

A description of the population of the database system and the desired mean of access/interaction

- Description can be informal but should be detailed
- Describe information requirements 

Book of duty

- What are the items in the populations
  - Eg., items for sale, records of sale, entries in a transcript
- Which are the concepts that should be represented?
  - E.g., items, storage facilities, students, courses
- What are the attributes of the concepts
  - E.g., price, color, availability, grade
- What are the domains of attributes of objects?
  - E.g., letters, integer numbers, dates
- How are objects identified/referenced?
  - E.g., BannerID, DOI, SSN
- Are there relationships between concepts? What is their nature?
  - E.g., authorship, manufacturer, distributor, publisher,...

Describe processing requirements 
- Cardinalities: how many items is the system expected to manage?
  - E.g. students university database, items online shop, number movies on a streaming platform;
  - Estimates rather than exact values: meaningful as guidelines
- Distributions
  - E.g., grade distributions in a class, number of order request through the day
- Workload 
  - Read/write frequency
- Priorities and service level agreements
  - Are there different tiers of users?
  - What guarantees on the service should be ensured?
  - Privacy of users and records

Conceptual Modeling

- Conceptual DB design
- Entity Relations (ER) method
    - Think of DBMS as a set of tables
    - Each table is called a relation

???

Brown Entity-Relationship (ER) model PPT
https://static.us.edusercontent.com/files/KY0L3oeXWDyehguFptxYuOsM

Logical and Physical Modeling

- Logical design (schema, table names, data types)
- Physical design (index, hints, memory organization)

Schema

每一列是这个关系的一个属性

PRIMARY

- Some attributes can be marked as PRIMARY
  - Forces records to have the corresponding attribute 
  - have NON NULL and unique value

Data Types
- Numeric: INT, FLOAT, REAL, DOUBLE 
- Character Strings: CHAR(n), VARCHAR(n), CLOB(size)
    - CHAR is fixed with, VARCHAR is not
    - CLOB(2MB) for large objects e.g. documents/web pages
- Bit Strings: BIT(n), BIT VARYING(n), BLOB
    - BLOB(20MB) e.g. for images
- Boolean
- Dates: DATE, TIME, TIMESTAMP, TIME WITH TIME ZONE
- Opportune choice of data type leads to improved performance and better memory utilization

Data access and analysis

- Asking and answering questions (queries)
- Extract information form the DBMS (views)
- SQL and relational algebra
