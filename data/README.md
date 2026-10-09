# 数据层说明

本目录是从前端打包文件中抽取的**结构化源数据**，供研究协作与版本管理使用。

## 文件

| 文件 | 内容 |
|---|---|
| `routes.geojson` | 35 条高风险野线（GeoJSON FeatureCollection，WGS84） |
| `zones.json` | 4 个地质地貌分区：成因叙事、攀爬特征、风险清单、所辖线路 |

## routes.geojson 字段

- `id` 线路编号（sm=思明, ta=同安, jm=集美, hc=海沧, xa=翔安）
- `name` / `district` / `category` / `typeLabel` 基本信息
- `difficulty` 难度 1–5（14 条官方未公布，为 `null`）
- `distanceKm` / `ascent` / `descent` 里程与累计爬升（米）
- `risk` 官方风险描述；`banned` 禁入人群
- `zoneId` 所属地质分区（对应 `zones.json` 的 `id`）
- `note` 备注

## zones.json 字段

- `rock` 岩性；`formation` 地质形成过程（分步叙述）
- `climbFeatures` 攀爬/通行特征；`risks` 区域风险清单
- `routeIds` 所辖线路编号

## 已知数据问题（v1）

1. 数据源为厦门市体育局 2026-03 公告的二手整理，**原始公告文号与链接待补**；
2. 坐标精度约 ±100 m（3 位小数），野外导航前需实测校准；
3. 14 条难度、13 条里程缺失，不做臆测填充，保持 `null`；
4. 封禁线路（文少谷、杉际内）仅保留记录，不包含进入指引。

> 本项目同时是《厦门山野地质图谱》研究的基础数据集（一手地质验证数据将陆续补充至 `observations/`）。
