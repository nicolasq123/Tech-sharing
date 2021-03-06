# 微服务设计

## 微服务
1. 什么是微服务
    - 很小，专注做好一件事
    - 自治性（独立实体）

2. 主要好处
    - 技术异构型
    - 弹性
    - 扩展
    - 简化部署
    - 与组织结构相匹配
    - 可组合
    - 对可替代性的优化

## 演化式架构
1. 架构的演化
    - 随着外在条件不断演化
2. 一个原则性的方法
    - 战略目标
    - 原则
        - 原则和限制
    - 原则实践相结合
3. 要求的标准
    - 监控
    - 接口
    - 架构安全性
4. 代码治理
    - 范例
    - 模板
    - ci
5. 技术债务
    - 温和的指导，定期回顾

## 如何建模服务
1. 什么样的服务是好服务
    - 松耦合
    - 高内聚
2. 业务功能
    - 从业务功能的角度考虑问题，而非数据共享角度
3. 限界上下文
    - 模块和服务
        - 服务的边界和领域的限界上下文 （然而在几乎所有这种规模的组织中，整个业务模型太大且过于复杂以至于难以管理，甚至很难把它作为一个整体来理解。我们必须把系统分解为较小的组成部分，无论在概念还是在实现上。   有时，企业系统会集成各种不同来源的子系统，或者包含诸多属于完全不同领域的应用程序。要把这些不同部分中隐含的模型统一起来是不可能的。通过为每个模型显式地定义一个限界上下文，然后在必要的情况下定义它与其他上下文的关系，建模人员就可以避免模型变得混乱。 -- 《领域驱动设计》）
    - 过早划分
4. 逐步划分上下文
    - 从粗粒度的边界到细粒度的边界
5. 技术边界
    - 技术对服务边界进行建模也并不总是对的（业务划分等）

## 集成
1. 寻找理想的集成技术
    - 避免破坏性修改（向上兼容）
    - API技术无关性
    - 服务易于使用
    - 隐藏细节
2. 为用户创建接口
    - client调用
3. 共享数据库
4. 同步与异步
    - 场景
5. 编排与协同
    - 通过编排处理
6. RPC
    - 技术的耦合
    - 本地调用与远程调用并不同
    - 脆弱性
        - 编解码消耗
        - 接口同步
7. REST
    - REST和HTTP
8. 实现基于事件的异步协作方式
    - 技术选择
        - broker等
    - 异步架构复杂性
9. 服务即状态机
10. 版本管理

## 分解单块系统
1. 分解单块系统原因
    - 变化
    - 安全
    - 技术
2. 找到问题的关键
    - 系统各模块的关系等
3. 打破外键关系
4. 重构数据库
    - 合并表
    - 分离表
    - 拒绝不合时宜的设计
5. 数据导出
    - 冗余表
    - 单独服务处理

## 部署
1. CI（Continuous Integration）
2. 持续集成映射到微服务
    - 不同服务不同CI
3. 特定构建物
4. 镜像
5. 环境
6. 服务
7. 自动化

## 测试
1. 测试范围
    - 单元测试
    - 服务测试
        - 针对服务的测试
    - 端到端测试


## 监控
1. 服务与服务器
    - 1对多 多对1  多对多 1对1
2. 日志
    - ELK
3. 指标
    - metics
4. 综合监控
5. 关联标识
6. 级联故障

## 安全
1. 验证与授权
    - 单点登录
    - 网关
    - 细粒度授权
2. 服务间的验证和授权

## 规模化微服务
1. 故障无处不在
2. 功能降级
    - 功能拒绝
    - 限流限量
3. 反脆弱的组织
    - 超时
        - 接口超时处理
    - 隔离
        - 物理隔离
        - 技术隔离
        - 业务隔离
4. 幂等
    - GET/PUT
5. 扩展
    - 分散风险
    - 负载均衡
6. 扩展DB/缓存
7. CAP定理
    - 一致性、可用性、分区容忍性
8. 服务注册与发现

## 总结
1. 微服务的原则
    - 围绕业务概念建模
    - 接受自动化
    - 隐藏内部细节
    - 去中心化
    - 独立部署
    - 隔离失败
        - 了解故障模式
        - 相应故障计划
    - 高度可观察
2. 什么时候不应该使用微服务
    - 服务的界限划分错误，可能会导致不得不频繁更改服务间的协作

