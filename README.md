# AHS Agentrix · 时空本体 4D 数字孪生 · 跨行业认知操作系统

> **AHS (AiHuaShen) Agentrix** 是一个基于时空本体（Spatio-Temporal Ontology）的 4D 数字孪生认知操作系统演示平台。它将多行业场景抽象为统一的"感知→诊断→规划→执行→审计"五阶段 Agent 管线，以 OWL/SHACL/SWRL 推理引擎为认知内核，实现跨行业的故障自愈、漏损管控、客流调度、反欺诈穿透和城市服务治理。

## 在线演示

**作品链接**: <https://noble-quartz-en5e.here.now/>

> 匿名发布，24 小时内有效。如需永久保留，请访问 [claim 链接](https://here.now/claim?slug=noble-quartz-en5e&token=7b01d1d951664fb1515106c814ed99755305aee7a2be5233ba5756ed9d31d618) 认领。

## 核心架构

```
┌─────────────────────────────────────────────────────────┐
│                    TOP BAR (面包屑导航)                    │
├──────────┬──────────────────────────────┬───────────────┤
│  LEFT    │         CANVAS (3D)          │  RIGHT PANEL  │
│ SIDEBAR  │   Three.js 4D 时空孪生场景    │   详情面板     │
│ 行业模板  │   · 行业 3D 场景渲染          │   · KPI 指标  │
│ 5 大行业  │   · 数据流粒子动画            │   · 架构度量  │
│          │   · Agent 管线可视化          │   · SHACL 校验│
│          │                              │   · 动作清单  │
│          │                              │   · PROV 谱系 │
│          │                              │   · 本体三元组│
├──────────┴──────────────────────────────┴───────────────┤
│              AGENT PIPELINE (五阶段认知管线)               │
│  [观察者] → [诊断者] → [规划者] → [执行者] → [审计者]      │
├─────────────────────────────────────────────────────────┤
│              FOOTER (健康状态 · 迭代计数 · FPS)            │
└─────────────────────────────────────────────────────────┘
```

## 五大行业场景

| 编号 | 场景 | 标签 | 数字孪生 | 核心能力 |
|------|------|------|----------|----------|
| 01 | **能源·电力调度智能体** | 能源 · 电网调度 | 调度自愈孪生 | FLISR 故障自愈、负荷转供、源荷储协同 |
| 02 | **水务治理智能体** | 水务 · DMA 分区 | 爆管漏损孪生 | 爆管定位 ±50m、最小停水隔离、漏损管控 |
| 03 | **交通·轨道调度智能体** | 交通 · 轨道线网 | 客流调度孪生 | 行车调度、客流预测、最小行车间优化 |
| 04 | **金融·风控反欺诈智能体** | 金融 · 风控反欺诈 | 反欺诈穿透孪生 | 关系图谱穿透、团伙识别、实时拦截 |
| 05 | **城市服务·环卫人车智能体** | 城市服务 · 环卫人车 | 环卫人车孪生 | 垃圾处理路线优化、人车调度、作业合规 |

## Agent 认知管线 (五阶段)

| 阶段 | Agent | 职责 | 典型延迟 |
|------|-------|------|----------|
| Phase 0 | **观察者** Observer | 消费事件流 · 识别状态偏离 | 18-48ms |
| Phase 1 | **诊断者** Diagnoser | 沿图谱与谱系链回溯根因 | 28-178ms |
| Phase 2 | **规划者** Planner | 生成候选动作 · 约束/策略检查 | 42-220ms |
| Phase 3 | **执行者** Executor | 幂等回写外部业务系统 | 36-680ms |
| Phase 4 | **审计者** Auditor | PROV 谱系沉淀 · 效果回评 | 32-42ms |

每个周期 (cycle) 自动推进，迭代计数实时显示在管线区域。

## 技术栈

- **3D 渲染**: Three.js r128 (CDN)
- **数据导出**: SheetJS (xlsx.full.min.js) — 支持 Excel 导出
- **字体**: Space Grotesk / JetBrains Mono / Inter / Noto Sans SC
- **本体语言**: OWL Turtle (内嵌 `@prefix ahs:` 命名空间)
- **约束校验**: SHACL shapes
- **推理规则**: SWRL 规则
- **谱系追踪**: W3C PROV-O

## 本体模型

每个行业场景内嵌完整的 OWL Turtle 本体片段，包含：

```
@prefix ahs:  <http://ahs.ai/agentrix/{industry}#> .
@prefix sosa: <http://www.w3.org/ns/sosa/> .
@prefix prov: <http://www.w3.org/ns/prov#> .
```

**对象 (Object)**: 行业实体类（如 Feeder, Switch, Pipe, Valve, Train, Account...）
**状态 (State)**: 实时观测属性（电压、压力、客流、交易特征...）
**事件 (Event)**: 异常/业务事件（过流、爆管、拥堵、欺诈...）
**约束 (Constraint)**: SHACL 约束（N-1 安全、最小服务压力、抢修响应时效...）
**动作 (Action)**: Agent 决策输出（分合闸、关阀、调度、拦截...）

## 数据导出

- **Excel 导出**: 右侧面板支持一键导出 KPI / 动作清单 / PROV 谱系为 .xlsx
- **本体查看**: 右侧面板展示当前场景的 Turtle 本体三元组

## 导入向导 (三步)

1. **R2RML 映射**: 关系数据库 → RDF 三元组映射
2. **语义对齐**: 水位线对齐 (Waterline Alignment) — 异构数据源语义对齐
3. **实例挂载**: 将对齐后的实例挂载到本体类层次结构

## 项目阶段

底部阶段栏展示项目生命周期：
- `pilot` — 试点验证
- `poc` — 概念验证
- `scale` — 规模化推广

## 快速开始

### 本地运行

直接用浏览器打开 `index.html` 即可，无需后端服务。

```bash
# 克隆仓库
git clone https://github.com/AiHuaShen/ahs-agentrix-cognitive-os.git
cd ahs-agentrix-cognitive-os

# 直接打开
open index.html        # macOS
xdg-open index.html    # Linux
start index.html       # Windows

# 或用本地服务器
python3 -m http.server 8080
# 访问 http://localhost:8080
```

### 在线访问

直接访问作品链接: <https://noble-quartz-en5e.here.now/>

## 文件结构

```
ahs-agentrix-cognitive-os/
├── index.html          # 主应用 (单文件，202KB，内联 CSS/JS)
├── README.md           # 本说明文档
└── LICENSE             # 许可证
```

## 应用说明

### 操作流程

1. **选择行业模板**: 左侧边栏点击五大行业之一
2. **观察 3D 场景**: 中央 Canvas 展示该行业的数字孪生 3D 场景
3. **查看 KPI**: 右侧面板顶部显示关键指标和趋势
4. **架构度量**: 推理速率、节点数、规则数、FPS、ACK 率
5. **SHACL 校验**: 显示当前场景的约束合规状态
6. **动作清单**: Agent 管线输出的决策动作列表（含幂等键）
7. **PROV 谱系**: 事件→规则→诊断→规划→决策→动作的完整追溯链
8. **本体三元组**: 当前场景的 OWL Turtle 本体定义
9. **Agent 管线**: 底部五阶段自动循环推进，可视化每个 Agent 的工作状态
10. **Excel 导出**: 点击导出按钮将面板数据导出为 .xlsx

### 交互特性

- **场景切换**: 点击左侧行业卡片，3D 场景平滑过渡
- **管线循环**: Agent 管线自动推进，每轮完成 感知→诊断→规划→执行→审计 全流程
- **数据流动画**: Canvas 中粒子流动表示实时数据流
- **事件爆发**: 异常事件触发视觉爆发效果
- **命令光束**: Agent 决策下发时产生光束动画
- **健康状态**: 底部状态栏实时显示系统健康度

## 关于 AHS 本体体系

本演示基于爱化身 (AiHuaShen) 管理本体 v1.7：
- 7 域 / 63 对象 / 22 AT / 31 SWRL / 5 SHACL
- DL 声明：传递、对称、不相交、逆属性、属性链、基数
- owlrl 推理：498 → 1661 三元组 (+1043)
- Neo4j：1175 节点 / 239 AHS 实例 / 7 客户

## License

© 2026 AiHuaShen (爱化身). All rights reserved.
