# 通用知识体系深度解析 Prompt 模板

---

## 📋 Prompt 正文

```
请帮我深入解析【{知识领域} 中的 {核心概念}】，要求如下：

## 输出格式
- 使用 Markdown 格式输出完整文档
- 所有架构图、流程图、对比图必须使用内嵌 SVG 格式（放在 ```svg 代码块中）
- SVG 风格要求：深色背景（#0f1117）、配色分层清晰、字体 'Segoe UI'/Arial、圆角矩形卡片风格

## 文档结构（按顺序输出以下章节）

### 一、概念定义
- 用一句话定义该概念的本质
- 说明它在整个【{知识领域}】体系中的地位和作用
- 给出一个直观的类比帮助理解

### 二、整体架构全景图（SVG）
- 绘制该概念的完整架构图，展示所有子模块/组成部分
- 图中需标注各模块的名称、关系和数据/控制流方向
- 使用分层布局（左到右 或 上到下），颜色区分不同模块类别

### 三、核心子概念逐一详解
- 对架构图中每个主要子模块单独展开
- 每个子概念包含：定义 + 关键特性 + 代码示例（如适用）
- 至少包含 1 张子概念的局部 SVG 流程图或示意图

### 四、工作原理 / 执行流程图（SVG）
- 绘制该概念的完整执行流程或生命周期图
- 使用带箭头的流程图，标注每个阶段的关键操作
- 标注关键决策点（菱形判断框）和数据变换节点

### 五、核心分类对比（SVG + 表格）
- 如果该概念有多个变体/类型，绘制 SVG 对比图
- 同时用 Markdown 表格列出：类型 | 特点 | 适用场景 | 优缺点

### 六、与其他概念的关联关系
- 说明该概念与【{知识领域}】中其他重要概念的关联
- 给出典型的组合使用示例（代码或伪代码）

### 七、进阶特性与底层原理
- 深入讲解 2~3 个高级特性或底层实现原理
- 每个特性配合代码片段或 SVG 原理图
- 重点揭示"为什么这样设计"的思路

### 八、生产实践 / 调优指南
- 列出常见问题及解决方案（表格形式）
- 给出 3~5 条最佳实践建议
- 提供关键配置参数说明

### 九、完整生命周期图（SVG）
- 绘制该概念从创建到销毁的完整生命周期
- 标注每个阶段对应的 API 方法或操作

### 十、总结与学习路线
- 用树形结构（文本）展示从入门到进阶的学习路径
- 列出 5~8 条核心记忆要点（重点加粗）
- 附官方文档或参考资料链接

## SVG 绘制规范
1. 背景色：fill="#0f1117"，圆角：rx="10"~rx="12"
2. 卡片容器：fill="#1e293b"，边框：stroke="#334155"
3. 主色调按模块类别区分：
   - 蓝色系（#1d4ed8 / #0ea5e9）：输入/基础层
   - 绿色系（#065f46 / #34d399）：处理/核心层
   - 紫色系（#5b21b6 / #a78bfa）：高级/扩展层
   - 橙色系（#d97706 / #fbbf24）：输出/结果层
   - 红色系（#7f1d1d / #f87171）：异常/警告
4. 文字颜色：标题 #e2e8f0，说明 #94a3b8，标注 #64748b
5. 箭头：使用 <marker> 定义箭头，颜色与连线一致
6. 每张 SVG 必须有标题文字，viewBox 宽度建议 720~900

## 代码示例规范
- 语言：优先使用【{知识领域}】的主流语言
- 每段代码不超过 30 行，聚焦核心逻辑
- 关键行加注释说明

## 其他要求
- 文档总长度不少于 3000 字
- 专业术语首次出现时给出中英文对照
- 避免泛泛而谈，每个结论都要有具体支撑
- 语言风格：技术严谨，但通俗易懂，适合有一定基础的开发者进阶学习
```

---

## 🔧 使用说明

将上方 Prompt 中的占位符替换为实际内容：

| 占位符 | 说明 | 示例 |
|--------|------|------|
| `{知识领域}` | 技术领域或框架名称 | Apache Flink、Kubernetes、React |
| `{核心概念}` | 要深入学习的具体概念 | 算子、Pod 调度、Hooks |

### 替换示例

| 场景 | 替换后效果 |
|------|-----------|
| 学习 Kubernetes 调度 | `【Kubernetes 中的 调度器（Scheduler）】` |
| 学习 React 状态管理 | `【React 中的 Hooks 机制】` |
| 学习 MySQL 索引 | `【MySQL 中的 索引（Index）】` |
| 学习 Kafka 架构 | `【Kafka 中的 分区（Partition）机制】` |
| 学习 Redis 数据结构 | `【Redis 中的 跳表（Skip List）】` |
| 学习 JVM 内存模型 | `【JVM 中的 垃圾回收（GC）机制】` |

---

## 💡 进阶变体 Prompt

### 变体一：对比学习型
在基础 Prompt 末尾追加：
```
额外要求：在文档末尾新增【与同类技术对比】章节，
横向对比 {概念A} 和 {概念B} 在设计理念、性能、适用场景上的差异，
用 SVG 绘制双列对比卡片图。
```

### 变体二：问题驱动型
在基础 Prompt 开头追加：
```
请以"解决 {具体业务问题}" 为切入点，
带着这个问题逐步展开 {核心概念} 的知识体系，
让读者在理解问题的同时自然地学习到该概念。
```

### 变体三：源码解析型
在基础 Prompt 末尾追加：
```
在【进阶特性与底层原理】章节中，
结合 {框架名称} 的源码（核心类：{ClassName}）
分析底层实现，给出简化版伪代码还原核心逻辑。
```

---

## 📐 SVG 色板速查

```svg
<svg viewBox="0 0 700 200" xmlns="http://www.w3.org/2000/svg" font-family="'Segoe UI', Arial, sans-serif">
  <rect width="700" height="200" fill="#0f1117" rx="10"/>
  <text x="350" y="28" text-anchor="middle" fill="#e2e8f0" font-size="13" font-weight="bold">SVG 标准色板</text>

  <!-- 蓝色系 -->
  <rect x="20" y="45" width="90" height="40" fill="#1d4ed8" rx="6"/>
  <text x="65" y="70" text-anchor="middle" fill="white" font-size="10">#1d4ed8</text>
  <rect x="120" y="45" width="90" height="40" fill="#0ea5e9" rx="6"/>
  <text x="165" y="70" text-anchor="middle" fill="white" font-size="10">#0ea5e9</text>
  <text x="105" y="100" text-anchor="middle" fill="#60a5fa" font-size="10">蓝色系 · 输入/基础</text>

  <!-- 绿色系 -->
  <rect x="230" y="45" width="90" height="40" fill="#065f46" rx="6"/>
  <text x="275" y="70" text-anchor="middle" fill="white" font-size="10">#065f46</text>
  <rect x="330" y="45" width="90" height="40" fill="#34d399" rx="6"/>
  <text x="375" y="70" text-anchor="middle" fill="white" font-size="10">#34d399</text>
  <text x="310" y="100" text-anchor="middle" fill="#34d399" font-size="10">绿色系 · 处理/核心</text>

  <!-- 紫色系 -->
  <rect x="20" y="115" width="90" height="40" fill="#5b21b6" rx="6"/>
  <text x="65" y="140" text-anchor="middle" fill="white" font-size="10">#5b21b6</text>
  <rect x="120" y="115" width="90" height="40" fill="#a78bfa" rx="6"/>
  <text x="165" y="140" text-anchor="middle" fill="white" font-size="10">#a78bfa</text>
  <text x="105" y="170" text-anchor="middle" fill="#a78bfa" font-size="10">紫色系 · 高级/扩展</text>

  <!-- 橙色系 -->
  <rect x="230" y="115" width="90" height="40" fill="#d97706" rx="6"/>
  <text x="275" y="140" text-anchor="middle" fill="white" font-size="10">#d97706</text>
  <rect x="330" y="115" width="90" height="40" fill="#fbbf24" rx="6"/>
  <text x="375" y="140" text-anchor="middle" fill="white" font-size="10">#fbbf24</text>
  <text x="310" y="170" text-anchor="middle" fill="#fbbf24" font-size="10">橙色系 · 输出/结果</text>

  <!-- 中性/警告 -->
  <rect x="440" y="45" width="90" height="40" fill="#1e293b" rx="6" stroke="#334155" stroke-width="1.5"/>
  <text x="485" y="70" text-anchor="middle" fill="#94a3b8" font-size="10">#1e293b</text>
  <rect x="540" y="45" width="90" height="40" fill="#7f1d1d" rx="6"/>
  <text x="585" y="70" text-anchor="middle" fill="white" font-size="10">#7f1d1d</text>
  <text x="515" y="100" text-anchor="middle" fill="#94a3b8" font-size="10">容器背景 · 红色警告</text>

  <rect x="440" y="115" width="90" height="40" fill="#0f1117" rx="6" stroke="#64748b" stroke-width="1"/>
  <text x="485" y="140" text-anchor="middle" fill="#94a3b8" font-size="10">#0f1117</text>
  <rect x="540" y="115" width="90" height="40" fill="#334155" rx="6"/>
  <text x="585" y="140" text-anchor="middle" fill="white" font-size="10">#334155</text>
  <text x="515" y="170" text-anchor="middle" fill="#64748b" font-size="10">页面背景 · 边框色</text>
</svg>
```

---

> 💬 **使用技巧**：首次使用时，建议完整复制 Prompt 正文并填入占位符；
> 如果输出内容较长，可分两次请求：第一次输出前五章，第二次从第六章继续。
