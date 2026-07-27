# Cortex 公开知识资产观测台

`Jainlee/cortex-view-7m23` 是私有仓库 `Jainlee/cortex` 的**公开静态看板投影**。

它用于发布经过确认的 Cortex 知识资产观测页面，不是知识库源头、项目总控、动态 State 或生成逻辑仓库。

## 仓库定位

```text
私有 Jainlee/cortex
= 知识资产、统计快照、人工判断、生成器和治理规则的当前权威

公开 Jainlee/cortex-view-7m23
= 经验证后发布的静态网页快照
```

本仓库当前保持最小结构：

```text
index.html
= 已发布的单文件静态看板

.nojekyll
= GitHub Pages 静态发布标记

AGENTS.md
= 公开投影仓库的写入与发布纪律

README.md
= 仓库身份和权威边界
```

本仓库不建立独立项目总控和动态 State，避免与私有 Cortex 形成平行事实源。

## 页面性质

页面是一个**受版本控制的生成式事实快照**：

- 不是自动实时联网报表；
- 页面中的事实指标来自私有 Cortex 的 Dashboard snapshot；
- 当前阶段、NEXT MOVE、WHY NOW、BLOCKER 和 ACTION 来自人工维护的 judgement；
- 公开页面不得独立修改或反向覆盖私有源；
- 页面保留 `noindex, nofollow, noarchive`，不作为搜索引擎公开索引页面。

当前页面入口：`index.html`。

## 权威来源

私有 Cortex 中的主要权威资产：

| 内容 | 私有源位置 |
|---|---|
| 自动事实和指标 | `_dashboard/cortex_asset_snapshot.json` |
| 人工阶段与行动判断 | `_dashboard/cortex_asset_judgement.json` |
| 已确认事实基线 | `_dashboard/cortex_asset_baseline.json` |
| 页面源文件 | `_dashboard/cortex_asset_dashboard.html` |
| 生成与验证逻辑 | `_tools/build_cortex_asset_dashboard.py` |
| 刷新流程和统计口径 | `_dashboard/README.md` |

公开仓库中的 `index.html` 只是这些权威资产经过生成、验证和公开范围检查后的发布结果。

## 标准发布边界

```text
私有 Cortex 更新
→ Lint / check / apply / validate
→ 用户确认必要判断和公开范围
→ 发布生成后的 index.html
→ 检查无私有资料和临时文件
→ 提交公开仓库
```

不得直接在公开仓库：

- 发明或修正统计事实；
- 维护独立的阶段判断；
- 上传原始笔记、永久笔记正文、私有 JSON、附件或 Vault；
- 复制一套新的统计与生成逻辑；
- 未经授权改变公开范围、视觉、动效或 noindex 设置。

具体执行纪律见 [AGENTS.md](AGENTS.md)。

## 当前维护原则

该仓库属于 Cortex 的发布端，不是新的独立项目。因此本轮只建立必要的 README 与 Agent 边界，不机械增加 State、Skill、Evals、Tools 或项目总控文件。
