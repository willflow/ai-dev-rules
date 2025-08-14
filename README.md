# AI开发规则集


## 🏗️ 项目结构

```
ai-dev-rules/
├── README.md                           # 项目说明文档
├── getting-good-results-from-claude-code.md  # 通用开发指导原则
├── frontend-development-rules.md       # 前端专用开发规范
├── commands/                           # Claude Code 命令集合
│   ├── explore-plan-code-test.md       # 探索-计划-编码-测试工作流
│   ├── git-commit.md                   # Git提交规范和自动化
│   ├── gogogo.md                       # 继续未完成任务
│   ├── ooda-cycle.md                   # OODA循环工作流程
│   └── simplify.md                     # 代码简化分析命令
└── agents/                             # OODA循环智能体集合
    ├── observe.md                      # 观察阶段 - 信息收集
    ├── orient.md                       # 定向阶段 - 分析理解  
    ├── decide.md                       # 决策阶段 - 方案选择
    ├── act.md                          # 行动阶段 - 精确执行
    └── simplify.md                     # 简化智能体 - 复杂度控制
```


## 📚 文档说明

### 核心文档

#### [`getting-good-results-from-claude-code.md`](./getting-good-results-from-claude-code.md)
**通用开发指导原则**

包含完整的开发流程、技术标准和质量控制方法：
- 📋 **规划与分阶段** - 3-5阶段的工作分解方法
- 🔄 **实施流程** - 理解→设计→实施→验证→重构→提交
- 🚫 **困难处理** - 最多3次尝试的原则和替代方案策略
- 🏗️ **架构原则** - 组合优于继承，接口优于单例
- ✅ **质量门槛** - 提交标准和验证指南

#### [`frontend-development-rules.md`](./frontend-development-rules.md) 
**前端专用开发规范**

针对React/Vue/Angular等现代前端框架的专门化指导：
- 🧩 **组件设计** - 优先级：标准化 > 条件渲染 > 自定义组件
- 🎣 **Hook/Composable设计** - 完整性封装思维，避免分散式设计
- 📊 **数据流处理** - 完整数据流追踪，对象操作最佳实践
- 📁 **导入路径规范** - 绝对路径vs相对路径的使用标准

### Claude Code 命令集合

为Claude Code定制的专用命令，提供高效的开发工作流程：

#### [`commands/explore-plan-code-test.md`](./commands/explore-plan-code-test.md) - 完整开发流程
**探索-计划-编码-测试工作流**
- 🔍 **探索阶段** - 并行子代理查找相关文件和信息
- 📋 **计划阶段** - 详细实施方案，包含测试和文档
- 💻 **编码阶段** - 遵循代码库风格，自动格式化
- 🧪 **测试阶段** - 并行测试验证，UX功能检查

#### [`commands/git-commit.md`](./commands/git-commit.md) - Git提交规范
**标准化提交流程和格式**
- 📝 **格式标准** - type(scope): description 格式
- 🏷️ **类型规范** - feat, fix, refactor, docs等标准类型
- 📋 **详细描述** - 结构化的变更列表格式
- ✅ **自动化** - 快速提交当前所有修改

#### [`commands/gogogo.md`](./commands/gogogo.md) - 任务续行
**智能任务恢复机制**
- 🔄 **状态检查** - 自动检查TODO列表和工作状态
- ⚡ **快速恢复** - 识别in_progress和pending任务
- 🎯 **智能续行** - 从中断点精确恢复工作
- 📝 **别名支持** - go, continue, 继续等多种调用方式

#### [`commands/ooda-cycle.md`](./commands/ooda-cycle.md) - OODA工作流
**系统化问题解决框架**
- 👁️ **观察** - 使用observe agent全面收集信息
- 🧭 **定向** - 使用orient agent分析理解上下文
- 🎯 **决策** - 使用decide agent评估方案选择
- ⚡ **行动** - 使用act agent精确执行验证

#### [`commands/simplify.md`](./commands/simplify.md) - 代码简化分析
**过度工程化检测工具**
- 🔍 **复杂性分析** - 识别过度工程化问题
- 🎯 **简化建议** - 提供具体的代码简化方案
- 👨‍💻 **开发体验** - 改善代码维护性和可读性
- 📊 **优先级评估** - 按影响程度排序改进建议

### OODA循环智能体

基于军事战略中的OODA循环(Observe-Orient-Decide-Act)，为复杂问题提供系统化解决框架：

#### [`agents/observe.md`](./agents/observe.md) - 观察阶段
**信息收集专家**
- 🔍 系统性收集所有相关数据
- 📝 发现上下文和模式识别
- 📋 全面覆盖，确保无遗漏
- 🎯 纯观察，不做判断

#### [`agents/orient.md`](./agents/orient.md) - 定向阶段  
**分析理解专家**
- 🧠 上下文分析和模式综合
- 🔗 关系映射和依赖理解
- ⚖️ 优先级评估和假设识别
- 🎯 提供洞察，不做决策

#### [`agents/decide.md`](./agents/decide.md) - 决策阶段
**方案评估专家**
- 💡 生成多种可行方案
- ⚖️ 权衡分析和风险评估
- 🎯 可行性评估和推荐形成
- 📋 明确的实施策略

#### [`agents/act.md`](./agents/act.md) - 行动阶段
**精确执行专家**
- ⚡ 精确实施和代码质量保证
- 🧪 全面测试和验证结果
- 📚 文档更新和质量检查
- ✅ 确认完成度

#### [`agents/simplify.md`](./agents/simplify.md) - 简化智能体
**复杂度控制专家**
- 🔍 过度工程检测
- 🎯 需求对齐验证
- 🧹 样板代码清理
- ⚡ 开发者体验优化
