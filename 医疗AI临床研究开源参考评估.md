# 医疗 AI 临床研究与开源参考评估

更新：2026-11-12

这份评估服务于网站重构，不把开源项目直接复制到生产系统。选择标准为：GitHub Star、最近更新时间、许可证、技术栈匹配度、部署难度，以及能否为“患者管理—临床研究—辅助决策”三条责任链提供可复用的流程结构。

## 结论

最值得参考的三个项目不是同一种产品：

1. [OpenClinica/OpenClinica](https://github.com/OpenClinica/OpenClinica)：最适合拆解 EDC/CDM 的研究对象、eCRF、访视、审计和角色权限。
2. [reliatec-gmbh/LibreClinica](https://github.com/reliatec-gmbh/LibreClinica)：最适合观察开源自部署、数据库和 Docker 化的研究基础设施，但 API 与生态风险更明显。
3. [Cohort-Study-Kit/cohort-study-kit](https://github.com/Cohort-Study-Kit/cohort-study-kit)：最适合拆解长期队列、表单、访视和参与者生命周期，不适合作为临床试验合规底座。

## 对比矩阵

| 项目 | GitHub 信号 | 许可证 | 技术栈 | 部署难度 | 能直接复用 | 需要二次开发 / 风险 |
|---|---:|---|---|---|---|---|
| OpenClinica | 519 stars；页面显示最新提交 2025-10-28 | GNU LGPL（仓库 README 关联 OpenClinica LGPL 说明） | Java；core/web/ws；Maven | 中高 | 研究、eCRF、访视、审计追踪、RBAC 的信息架构 | 生产验证、合规、供应链、安全和本地化；商业开源边界需法务核验 |
| LibreClinica | 84 stars；页面显示约 10 天前更新 | LGPL-3.0 / GPL-3.0 | Java、Tomcat、PostgreSQL、Docker | 中高 | EDC/CDM 数据模型、自托管部署思路、研究对象流程 | README 明确提示 SOAP API legacy、未测试且不活跃；社区与人才规模有限，许可证组合需核验 |
| Cohort Study Kit | 0 stars；最新提交页面显示 2026-10-19 | LGPL-3.0 | Python/Django、MariaDB、JavaScript、Bootstrap | 低—中 | 队列表单、访视排程、参与者记录、角色和数据导出 | 无公开 Release、贡献者少；缺少多中心、临床试验验证、审计和生产运维证据 |

## 对网站设计的影响

- 临床研究板块不能只放“AI 招募”和“病例搜索”，必须展示方案、队列、访视、EDC/CTMS、审计和分析之间的链路。
- “可复用”应优先指信息架构、数据对象和验证问题，不应暗示代码可直接用于医院或药企生产环境。
- 评估产品时，把“模型能力”和“研究基础设施能力”分开：前者解决局部任务，后者决定可追溯、可复现和可交付。

## 来源

- [OpenClinica GitHub README](https://github.com/OpenClinica/OpenClinica)：EDC/CDM、eCRF、访视、审计、电子签名、RBAC、导入导出和许可证说明。
- [LibreClinica GitHub README](https://github.com/reliatec-gmbh/LibreClinica)：继承关系、技术栈、版本要求、SOAP API 风险、LGPL/GPL 信息。
- [Cohort Study Kit GitHub README](https://github.com/Cohort-Study-Kit/cohort-study-kit)：纵向队列、表单、访视、参与者记录、技术栈和 LGPL 说明。

> GitHub Star、更新时间和贡献者数量是公开活跃度信号，不是临床质量、合规性或商业成功的替代指标。
