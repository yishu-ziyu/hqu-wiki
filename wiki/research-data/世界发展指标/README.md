# 世界发展指标（World Development Indicators, WDI）

> 来源：世界银行公开数据库，2019 年 9 月版

## 数据说明

WDI 是世界银行最大的公开发展数据库，覆盖 1960–2018 年约 200 多个经济体的 1,400+ 指标。

### 文件结构

| 文件 | 大小 | 说明 |
|------|------|------|
| `wdi-csv-2019.zip` | 64 MB | 全部 6 个 CSV 压缩包（解压后 ~254 MB） |
| `WDIData.csv` | 203 MB | 主数据表（各国 × 指标 × 年份，宽表格式） |
| `WDISeries.csv` | 3.7 MB | 指标元数据（名称、定义、来源、单位） |
| `WDIFootNote.csv` | 47 MB | 脚注数据 |
| `WDICountry.csv` | 166 KB | 国家元数据 |
| `WDICountry-Series.csv` | 768 KB | 国家-指标对应关系 |

## 数据结构

`WDIData.csv` 格式：

```
Country Name | Country Code | Indicator Name | Indicator Code | 1960 | 1961 | ... | 2018
```

- **Country Code**：3 位 ISO 代码（如 CHN、USA、IND）
- **Indicator Code**：点分隔代码（如 `NY.GDP.MKTP.KD` = GDP 不变价）
- 空值 = 该年该指标无数据

## 常见指标代码速查

| 代码 | 名称 |
|------|------|
| `NY.GDP.MKTP.KD` | GDP（不变价美元） |
| `NY.GDP.PCAP.KD` | 人均 GDP |
| `SP.POP.TOTL` | 总人口 |
| `SP.DYN.LE00.IN` | 预期寿命 |
| `SE.PRM.ENRR` | 小学入学率 |
| `EN.ATM.CO2E.KT` | CO₂ 排放量（千吨） |
| `SL.UEM.TOTL.ZS` | 失业率（占劳动力 %） |
| `FP.CPI.TOTL` | 消费者物价指数 |

完整列表见 `WDISeries.csv`。

## 典型用法

适合做：
- **跨国回归**：GDP、教育、健康、环境的跨截面 / 面板分析
- **增长收敛**：人均 GDP 趋同检验
- **发展指标聚类**：按多维指标对国家分组
- **长期趋势**：1960 年至今的指标时序

## 注意事项

- 解压 zip 后总大小 ~254 MB，内存吃紧时用 `pandas.read_csv(chunksize=...)` 分块读
- `WDIData.csv` 是宽表（年份做列），分析前通常要 melt 成长表格式
- 2019 版数据截止到 2018 年，如需更新去世界银行官网下载最新版
- 指标定义和口径可能跨年份变动，注意脚注（`WDIFootNote.csv`）
