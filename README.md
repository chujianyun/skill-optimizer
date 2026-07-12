# skill-optimizer

作者：悟鸣

`skill-optimizer` 用于审查和优化已有 Skill，重点看触发语义、工作流门槛、资源组织、安全边界、依赖可安装性，以及 README / SKILL 的职责分层。

## 为什么需要 Skill Optimizer

现在很多 Skill 都是由 AI 生成的，其中往往存在一些比较明显的设计原则问题，也可能包含彼此冲突的规则。

我们特别需要一个专业的 Skill 优化工具，帮助发现这些关键问题，并对专业、复杂的 Skill 进行持续打磨和优化。

Skill Optimizer 的方法论参考了 Anthropic 官方最佳实践和 Google 的 Skills 设计模式，也融合了我们在一线大厂业务，以及日常工作、生活和学习中开发 100 多个专业 Skills 所积累的经验。

这些 Skills 已经在一线大厂内部被许多同事实际使用，并为真实业务提供了切实帮助。Skill Optimizer 正是从这些反复使用、发现问题和持续改进的过程中总结出来的。

也欢迎你针对优化问题提交 Issue 或 Pull Request，和大家一起共建、完善这个项目。

## 适用场景

- 想检查一个 Skill 是否容易触发、容易误触发，或边界不清
- 想补确认门槛、异常处理、敏感操作保护
- 想优化 `references/`、`scripts/`、索引、README 等结构设计
- 想判断 Skill 粒度是否合适，是否与同级 Skill 重叠或适合合并

## 主要功能

- 先审查目标 Skill，再给出分优先级的优化计划
- 检查异常场景、敏感信息、敏感操作和外部依赖安装说明
- 判断文件多时是否需要索引，帮助渐进式加载
- 检查是否缺少 `README.md`，并区分 README 与 `SKILL.md` 的职责

## 使用方式

典型流程是：

1. 读取目标 Skill 的 `SKILL.md`
2. 按需读取 `references/`、`scripts/`、`assets/`、`README.md`
3. 输出审查结论和优化计划
4. 在用户明确确认后再实施修改
5. 校验修改结果并汇报剩余风险

## 风险与边界

- 默认先审查、后规划、再修改；没有明确确认前不应直接改目标 Skill
- 如果发现疑似敏感信息，不应在回复中回显完整内容
- 如果目标 Skill 包含删除、覆盖、部署、发送消息、付费调用等高副作用操作，应增加确认门槛或风险提示
- 如果依赖外部 CLI、服务或运行时，应补安装和校验命令，避免 Skill 只能“看懂”但不能“执行”

## README 与 SKILL 的区别

- `README.md` 面向人：说明使用场景、主要功能、风险、边界和整体认知
- `SKILL.md` 面向 AI：说明触发条件、工作流、Gotchas、确认门槛和执行规范

这两个文件应该互补，而不是大段重复。

## 联系作者

| 添加作者微信 | 关注「悟鸣AI」公众号 |
| :---: | :---: |
| <img src="https://mingmingruyue-hz.oss-cn-hangzhou.aliyuncs.com/2025/%E6%98%8E%E6%98%8E%E5%A6%82%E6%9C%88%E5%AD%A6%E9%95%BF%E5%85%AC%E4%BC%97%E5%8F%B7.jpg" alt="作者悟鸣的微信二维码" width="240"> | <img src="https://mingmingruyue-hz.oss-cn-hangzhou.aliyuncs.com/2025/%E6%82%9F%E9%B8%A3AI%E5%85%AC%E4%BC%97%E5%8F%B7%E4%BA%8C%E7%BB%B4%E7%A0%81.jpg" alt="悟鸣AI公众号二维码" width="240"> |
