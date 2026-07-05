# 阶段执行方案模板

> 按六阶段生命周期拆解项目任务，输出可执行的阶段方案。

---

# 📊 {project_name} 执行方案

**编制日期**：{date}
**负责人**：{tech_lead}
**项目目标**：{one_line_objective}

---

## 一、项目现状

### 1.1 项目环境
- **市场现状**：{market_context}
- **技术现状**：{tech_context}
- **竞争现状**：{competition_context}

### 1.2 项目目标
- **底线目标**（必须达成）：{minimum_success}
- **理想目标**（争取达成）：{ideal_success}
- **不可接受**（必须避免）：{unacceptable_outcome}

### 1.3 团队编排
| 角色 | 人员 | 职责范围（三八线） |
|------|------|------------------|
| {role_1} | {person} | {scope} |
| {role_2} | {person} | {scope} |

---

## 二、侧翼登陆点（关键杠杆）

> 识别项目中的杠杆点——一个决策或技术突破可以改变全局走向。

**切入点**：{leverage_point}
**选择理由**：{why_this_is_the_leverage}
**前置条件**：{prerequisites}
**预期效果**：{expected_impact}
**备选切入点**：{alternative}

---

## 三、阶段计划

### Phase 0: 立项研判（{date_range}）

| 任务 | 负责人 | 产出 | 完成标准 |
|------|--------|------|--------|
| 需求可行性评估 | {owner} | {deliverable} | {criteria} |
| 技术方案评审 | {owner} | {deliverable} | {criteria} |
| 资源与时间评估 | {owner} | {deliverable} | {criteria} |

**出口门禁**：
- [ ] {gate_1}
- [ ] {gate_2}

---

### Phase 1: 迭代冲刺（{date_range}）

#### 第一迭代：MVP 首版（{date_range}）
- **核心方向**：{main_objective}
- **关键交付**：{deliverables}
- **迭代节奏**：每日站会 + 周五交付清点

#### 第二迭代：核心突破（{date_range}）
- **核心方向**：{main_objective}
- **长津湖聚焦**：{集中力量突破的难点}
- **关键交付**：{deliverables}

#### 第三迭代：功能扩展（{date_range}）
- **核心方向**：{main_objective}
- **推进目标**：{deliverables}

#### 第四迭代：回撤重整（{date_range}）
- **技术债务清理**：{debt_items}
- **架构优化**：{optimization_items}
- **性能基线**：{baseline_target}

#### 第五迭代：集成稳定（{date_range}）
- **集成测试**：{test_scope}
- **性能验证**：{perf_target}
- **全链路稳定**：{stability_criteria}

**出口门禁**：
- [ ] 迭代目标达成
- [ ] 性能基线已建立
- [ ] 技术债务清单已排期

---

### Phase 2: 反绞杀（{date_range}）

**关键链路清单**：
| 链路 | 脆弱点 | 冗余方案 | 负责人 |
|------|--------|---------|--------|
| {path_1} | {weakness} | {redundancy} | {owner} |
| {path_2} | {weakness} | {redundancy} | {owner} |

**故障注入演练计划**：
- 故障注入范围：{scope}
- 预期 RTO：{rto_target}
- 预期 RPO：{rpo_target}

**出口门禁**：
- [ ] 核心链路无单点
- [ ] 故障注入测试通过
- [ ] 监控覆盖率 > 90%

---

### Phase 3: 上甘岭（{date_range}）

**质量基线清单**：
| 基线项 | 指标 | 底线值 | 负责人 |
|--------|------|--------|--------|
| 功能正确性 | 测试通过率 | ≥ 98% | {owner} |
| 性能 | P99 延迟 | < {target}ms | {owner} |
| 安全 | 高危漏洞 | = 0 | {owner} |
| 可用性 | SLA | ≥ {target}% | {owner} |

**压力测试计划**：
- 全链路压测：{target_qps} QPS
- 安全渗透：{scope}
- 异常场景：{scenarios}

**出口门禁**：
- [ ] 所有基线指标达标
- [ ] 安全审计通过
- [ ] 质量基线文档化

---

### Phase 4: 边打边谈（{date_range}）

**需求分级**：
| 类型 | 需求项 | 处理方式 |
|------|--------|--------|
| 🔒 冻结需求（不可变） | {frozen_items} | 不接受变更 |
| 🤝 待协商需求（需评审） | {negotiable_items} | PM 评审决策 |
| ⚙️ 灵活需求（可调整） | {flexible_items} | 开发自行决定 |

**迭代节奏**：每2周交付 → 需求评审 → 下一轮迭代

---

### Phase 5: 金城（{date_range}）

**预发布验证**（D-7 ~ D-3）：
- 全链路压测：{date}
- 灰度 10%：{date}
- 预发布环境验收：{date}

**正式发布**（D-Day）：
- 正式发布：{date}
- 实时监控：{monitoring_plan}

**全量推进**（D+1 ~ D+3）：
- 全量放开：{date}
- 72小时值班护航：{on_call_plan}

**交付协议**：
- 项目复盘：{date}
- 文档归档：{date}
- 运维交接：{date}

---

## 四、风险预案

| 风险场景 | 触发条件 | 预案 | 决策人 |
|---------|---------|------|--------|
| {risk_1} | {trigger} | {contingency} | {owner} |
| {risk_2} | {trigger} | {contingency} | {owner} |

---

## 五、里程碑总览

```
{date} ─── Phase 0 完成（立项研判通过）
{date} ─── 第一迭代完成（MVP 可用）
{date} ─── 第三迭代完成（功能完备）
{date} ─── Phase 2 完成（韧性验证通过）
{date} ─── Phase 3 完成（质量基线达标）
{date} ─── Phase 5 D-Day（正式上线）
{date} ─── 项目收尾（交付协议签署）
```
