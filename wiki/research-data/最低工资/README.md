# 最低工资与专利创新数据

> 来源：用户整理面板数据，基于美国劳工部最低工资数据 + USPTO 专利数据

## 数据说明

| 文件 | 说明 |
|------|------|
| `Minimum Wage Data.csv` | 1968–2020 年美国各州名义/实际最低工资（2020 年不变价） |
| `merged_panel_data.csv` | 2002–2020 年各州面板：最低工资 + 专利数 + 差分项 + 滞后变量 |
| `patent_by_state.csv` | 2002–2020 年各州专利数（USPTO） |
| `minimum_wage_patent_analysis.py` | 分析脚本（Stata / Python） |
| `minimum_wage_trends.png` | 最低工资时序趋势图 |
| `minimum_wage_patent_results.png` | 专利与最低工资关系分析图 |

## 变量说明

- `State.Minimum.Wage` — 州最低工资（名义，美元/小时）
- `State.Minimum.Wage.2020.Dollars` — 实际最低工资（2020 年不变价）
- `Federal.Minimum.Wage` — 联邦最低工资
- `Effective.Minimum.Wage` — 有效最低工资（取州/联邦较高值）
- `Patents` — 该州当年授权专利数
- `D_MinWage` — 最低工资一阶差分
- `D_MinWage_Positive` — 最低工资是否上升
- `D_Patents` — 专利数一阶差分
- `D_Patents_Pct` — 专利数变化率
- `D_MinWage_L1/L2/L3` — 最低工资滞后差分
- `D_Patents_L1/L2/L3` — 专利滞后差分

## 典型用法

适合做：
- **DID / event study**：最低工资上调对创新的影响
- **面板回归**：固定效应模型，控制州级异质性
- **工具变量**：用联邦最低工资变化做州最低工资的 IV

## 注意事项

- 数据为州级面板，非国家级，跨国比较不可用
- 部分州早期数据缺失（有效最低工资为 0 表示该州无州法）
- 专利数为授权量，非申请量
