# 前端开发规则集
*适用于React/Vue/Angular等现代前端框架项目*

**重要**：本规则完全服从个人开发规则。当两者有任何冲突时，以个人规则为准。前端规则只是在个人规则基础上的具体技术补充。

# 组件设计原则

### 组件创建优先级
1. **优先标准化**：使用标准HTML标签和现有组件，避免创建自定义标签
2. **条件渲染优于多组件**：通过属性判断渲染不同内容，而不是创建多个相似组件
3. **向后兼容性**：新功能必须保证现有功能不受影响

### 技术方案选择优先级
```
扩展现有组件功能 > 创建新的自定义组件
单一组件内条件判断 > 多个专用组件
标准HTML/框架组件 > 自定义标签
类型兼容 > 强制类型转换
```

## Hook/Composable 设计原则

### 完整性设计思维
1. **完整封装思维**：创建hook时必须一次性考虑所有相关的逻辑、配置和常量
2. **封装边界清晰**：相关的配置、常量、状态和逻辑都应该封装在同一个hook内
3. **避免分步遗漏**：不要分步骤处理相关功能，防止遗漏应该一起封装的部分

### 实践指导
```javascript
// ❌ 分散的hook设计
const useDataFetch = () => { /* 只处理数据获取 */ };
const useDataFormat = () => { /* 只处理数据格式化 */ };

// ✅ 完整的hook设计
const useDataManagement = () => {
  const DATA_CONSTANTS = { /* 相关常量封装在内 */ };
  const fetchData = () => { /* 数据获取逻辑 */ };
  const formatData = () => { /* 数据格式化逻辑 */ };
  return { fetchData, formatData, constants: DATA_CONSTANTS };
};
```

## 数据流处理规则

### 数据流问题调试策略
**避免局部思维，必须进行完整数据流追踪**

#### 调试流程
1. **对比原始数据结构** - 确认期望的完整字段
2. **追踪完整数据流** - API → 中间处理组件 → 目标组件
3. **找出数据丢失的具体环节** - 在哪一步过滤掉了需要的字段
4. **从根源修复问题** - 在数据丢失的环节修复，而不是在最后一环补救

### 对象操作最佳实践
```javascript
// ❌ 手动枚举重复属性
const processedData = data.map(item => ({
  id: item.id,
  name: item.name,
  // ...20个其他原有属性
  newField: 'newValue'
}));

// ✅ 使用展开运算符
const processedData = data.map(item => ({
  ...item,
  newField: 'newValue'
}));
```

## Import路径规范

### 路径使用规则
1. **跨目录引用**：使用`@/`绝对路径别名，避免复杂的相对路径
2. **同级文件引用**：使用相对路径（如`./`、`../`）

```javascript
// ✅ 绝对路径场景
import { queryAPI } from '@/services/api';
import { Button } from '@/components/UI/Button';

// ✅ 相对路径场景
import styles from './index.module.less';
import SubComponent from './SubComponent';
```

### 判断标准
- 当前目录或相邻目录（1-2层）→ 相对路径
- 跨越多个目录层级 → `@/`绝对路径
- 样式文件(.less, .css) → 相对路径
- 服务层、工具函数、类型定义 → 绝对路径

