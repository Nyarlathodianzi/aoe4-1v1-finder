# AoE4 1v1 Match Finder / 帝国时代4天梯 1v1 对局查询器

[中文说明](#中文说明) | [English](#english)

---

## 中文说明

### 项目简介

这是一个单文件 HTML 小工具，用来从《帝国时代4》天梯上，按「分段 + 胜方民族 + 败方民族 + 地图」筛选 1v1 对局，方便找对局学习。

- 双击 `aoe4-1v1-finder.html` 即可打开
- 不需要安装，不依赖其他文件
- 只有「抓取数据」一步需要联网，筛选完全在本地进行

### 数据范围

只收录**双方对局当时分数都在 1400 以上**的对局。

- 分数按「对局开始前」计算
- 只要有一个人当时不到 1400 分，这局就不会出现在结果里
- 目前主要覆盖「征服者」分段

### 使用方法

#### 第一步：抓取数据

1. 选择抓取深度：
   - 浅：最多 1 页/组，顺利时约 1 分钟
   - 中：最多 6 页/组，顺利时约 4 分钟（推荐先用这个）
   - 深：最多 19 页/组，顺利时约 11 分钟
2. 点击「抓取」，等待进度条完成。
3. 抓取完成后会显示本次抓取说明，包括抓取局数、覆盖时间段等。

> 数据源限制了请求频率，大约每秒最多 1 次。网络不好时工具会自动放慢并重试，可能会比较慢。

#### 第二步：筛选对局

可选的筛选条件：

- 胜方民族
- 分段：征服者 I / II / III / IV
- 范围：及以上 / 仅此段
- 败方民族
- 地图：根据已抓取的数据自动生成，并显示每张图的对局数

点击「按条件筛选」后，结果按时间从新到旧排列。每页可显示 10 / 20 / 50 / 100 / 200 条，默认 50 条。

> 改了条件后，需要重新点击「按条件筛选」，表格才会更新。

### 导入 / 导出数据

抓取一次可能需要几分钟到几十分钟，所以支持：

- **导出数据**：把本地对局库导出为 JSON 文件，可以发给别人
- **导入数据**：读取别人导出的 JSON 文件，并自动合并、去重

导入是「合并」，不是「覆盖」：

- 你原有的数据不会丢
- 文件里你没有的对局会补进来
- 两边都有的同一局只会保存一份

### 数据存储

- 数据保存在浏览器的本地存储中
- 刷新页面不会丢
- 清除浏览器缓存、换浏览器或换电脑后会丢失
- 建议定期使用「导出数据」备份

### 数据来源

对局数据来自 [aoe4world.com](https://aoe4world.com) 的公开接口。

- 本工具不做破解或越权访问
- 请求频率被刻意压低（约每秒 1 次），避免给对方服务器造成压力
- 请遵守数据源网站的使用条款

### 环境要求

- 建议使用 Chrome 或 Edge（2021 年以后版本）
- 如果双击打不开，请右键 → 打开方式 → 选择 Chrome

### 隐私说明

导出的 JSON 文件包含：

- 对局时间
- 地图
- 民族
- 玩家 ID
- 玩家昵称
- 分数

这些数据来自公开的天梯接口，但分享数据文件前请自行考虑隐私和合规问题。

### 许可证

本项目使用 [MIT License](LICENSE) 开源。

你可以自由使用、修改、分发本项目，只需保留版权声明和许可证文本。作者不对使用本工具造成的任何后果负责。

---

## English

### About

A single-file HTML tool for finding *Age of Empires IV* 1v1 ladder matches by **rank, winner civilization, loser civilization, and map**.

- Just open `aoe4-1v1-finder.html` in a browser
- No installation and no external dependencies
- Only the data-fetching step requires internet; filtering works entirely offline

### Data Scope

Only matches where **both players were rated 1400+ at the time of the match** are included.

- Ratings are taken from before the match
- If either player was below 1400, the match is excluded
- The tool mainly covers the Conqueror tier

### Usage

#### Step 1: Fetch Data

1. Choose a fetch depth:
   - Shallow: up to 1 page per group, about 1 minute in good conditions
   - Medium: up to 6 pages per group, about 4 minutes (recommended)
   - Deep: up to 19 pages per group, about 11 minutes
2. Click **Fetch** and wait for the progress bar to finish.
3. A summary will show how many matches were fetched and which time range they cover.

> The data source limits request frequency to about once per second. When the network is unstable, the tool slows down and retries automatically.

#### Step 2: Filter Matches

Available filters:

- Winner civilization
- Rank: Conqueror I / II / III / IV
- Scope: and above / this tier only
- Loser civilization
- Map: generated from fetched data, with match counts per map

Click **Filter** to show results sorted from newest to oldest. You can display 10 / 20 / 50 / 100 / 200 rows per page; the default is 50.

> After changing filters, click **Filter** again to refresh the table.

### Import / Export

Fetching can take a while, so the tool supports:

- **Export**: download your local match database as a JSON file
- **Import**: read another user's JSON file and merge it automatically

Importing **merges** data instead of overwriting it:

- Your existing data is kept
- New matches from the file are added
- Duplicate matches are stored only once

### Data Storage

- Data is stored in your browser's local storage
- Refreshing the page will not erase it
- Clearing browser data, switching browsers, or switching computers will erase it
- Use **Export** regularly to back up your data

### Data Source

Match data comes from the public API of [aoe4world.com](https://aoe4world.com).

- This tool does not bypass authentication or scrape private data
- Requests are intentionally rate-limited to about once per second
- Please follow the data source's terms of use

### Requirements

- Chrome or Edge (2021 or newer recommended)
- If double-clicking does not work, right-click the file → Open with → Chrome

### Privacy

Exported JSON files contain:

- Match time
- Map
- Civilization
- Player IDs
- Player names
- Ratings

This information comes from public ladder data, but consider privacy and compliance before sharing data files.

### License

This project is released under the [MIT License](LICENSE).

You are free to use, modify, and distribute it, as long as the copyright notice and license text are retained. The author is not liable for any consequences of using this tool.
