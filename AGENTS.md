# AGENTS.md

## 1. 仓库身份

本仓库 `Jainlee/cortex-view-7m23` 是 Cortex 知识资产看板的**公开静态投影仓库**。

它不是 Cortex 的知识源、项目总控、动态 State 或生成逻辑权威。

```text
Jainlee/cortex
= 私有源仓库与当前权威

Jainlee/cortex-view-7m23
= 经确认后发布的静态网页投影
```

当前页面采用单文件静态站点：

- `index.html`：发布后的看板页面；
- `.nojekyll`：GitHub Pages 静态发布标记；
- `README.md`：仓库身份、权威边界和发布说明；
- `AGENTS.md`：本仓库写入纪律。

本仓库不需要独立项目总控、独立动态 State、Skill、Evals 或历史档案。相关职责由私有 `Jainlee/cortex` 承担。

## 2. 固定权威来源

涉及事实、判断、统计口径、页面结构或生成逻辑时，必须回到私有 `Jainlee/cortex`：

| 问题 | 当前权威位置 |
|---|---|
| 自动事实、指标、最新批次、主题热度和来源口径 | `_dashboard/cortex_asset_snapshot.json` |
| 当前阶段、NEXT MOVE、WHY NOW、BLOCKER 和 ACTION | `_dashboard/cortex_asset_judgement.json` |
| 已人工接受的事实基线 | `_dashboard/cortex_asset_baseline.json` |
| 页面结构、视觉、标记区和动效 | `_dashboard/cortex_asset_dashboard.html` |
| 统计、应用和验证逻辑 | `_tools/build_cortex_asset_dashboard.py` |
| 日常刷新和基线接受流程 | `_dashboard/README.md` |
| Cortex 项目权限、边界和发布纪律 | 私有仓库 `AGENTS.md` |

本仓库中的 `index.html` 是发布结果，不得反向覆盖以上权威来源。

## 3. 最小加载规则

处理本仓库任务时，至少读取：

1. 本文件；
2. `README.md`；
3. 当前 `index.html`；
4. 私有 Cortex 中与任务直接相关的权威文件；
5. 用户当前明确授权或正式任务书。

不得默认加载、复制或发布整个 Cortex Vault、原始笔记、私有 JSON、内部索引或其他不属于公开投影的资产。

## 4. 允许的工作

在明确授权下可以：

- 发布已经在私有 Cortex 完成生成和验证的 `index.html`；
- 修正 README、AGENTS 或静态发布配置；
- 检查页面是否仍包含必要的 `noindex` 元信息；
- 检查生成日期、指标、人工判断和页脚来源是否与私有源一致；
- 检查公开仓库中是否意外包含私有资料、源 JSON、临时文件或一次性发布文件；
- 在视觉、结构或脚本任务已经先在私有 Cortex 形成权威修改时，同步发布对应产物。

## 5. 禁止事项

不得：

- 在本仓库中独立维护 Cortex 当前 State；
- 直接根据印象、旧对话或文件时间修改统计数字；
- 在 `index.html` 中独立修改当前阶段、NEXT MOVE、WHY NOW、BLOCKER 或 ACTION；
- 把公开投影当作私有 Cortex 的备份或事实源；
- 上传原始笔记、永久笔记正文、私有 JSON、Vault 目录、附件、图片库、凭据或真实 `.env`；
- 为了刷新页面而在本仓库重新实现一套统计或判断逻辑；
- 未经授权移除 `<meta name="robots" content="noindex, nofollow, noarchive" />`；
- 未经明确授权改变页面视觉、布局、动效、统计口径或公开范围；
- 保留已经完成的一次性工作流、临时发布片段或中间文件；
- 建立与私有 Cortex 平行的 README 事实、项目总控或发布规则。

## 6. 标准发布链

```text
私有 Cortex 知识资产变化
→ 运行永久笔记 Lint
→ Dashboard --check
→ 必要时由用户接受新基线
→ Dashboard --apply
→ Dashboard --validate
→ 人工检查公开范围和敏感信息
→ 将生成后的静态页面发布到本仓库
→ 检查仓库只保留必要公开文件
→ commit / push
```

私有 Cortex 的普通刷新命令以 `_dashboard/README.md` 为准。本仓库不复制并维护另一套命令权威。

## 7. 发布验收

每次发布至少确认：

- [ ] `index.html` 来自已经验证的私有 Cortex 产物；
- [ ] 自动事实与 snapshot 一致；
- [ ] 人工判断与 judgement 一致；
- [ ] 页面保留 `noindex, nofollow, noarchive`；
- [ ] 未包含原始笔记、私有 JSON、附件、凭据或内部路径内容；
- [ ] 未残留 `.publish-*`、一次性工作流或临时文件；
- [ ] 页面可以作为静态文件正常加载；
- [ ] Git diff 只包含本次授权范围；
- [ ] 发布提交说明清楚标明快照或修正范围。

## 8. 单一写入者

同一时间只允许一个主体写入本仓库。

```text
ChatGPT 正在写
→ Codex 和人工不写

Codex 或发布工作流正在执行
→ ChatGPT 不写

发现来源不明的新提交或未完成发布任务
→ 停止并对账
```

涉及私有 Cortex 和本公开仓库的双仓库任务时，先完成并验证私有源，再更新公开投影。不得先改投影、后补源头。

## 9. 停止条件

遇到以下情况必须停止并交还用户：

- 私有源与公开页面的事实或判断不一致；
- 无法确认某项内容是否适合公开；
- 需要扩大公开范围或移除 noindex；
- 需要修改统计口径、生成器、视觉或交互；
- 需要删除历史发布内容但缺少明确授权；
- 私有 Cortex 或本仓库存在并行写入；
- 生成、验证或公开范围检查未通过。
