# AI开发规则集


## 🏗️ 项目结构

```
ai-dev-rules/
├── README.md                           # 项目说明文档
├── getting-good-results-from-claude-code.md  # 通用开发指导原则
├── frontend-development-rules.md       # 前端专用开发规范
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
