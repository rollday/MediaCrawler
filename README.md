# 🔥 MediaCrawler - 多平台社交媒体爬虫 🕷️

<div align="center">

<a href="https://trendshift.io/repositories/8291" target="_blank">
  <img src="https://trendshift.io/api/badge/repositories/8291" alt="NanmiCoder%2FMediaCrawler | Trendshift" style="width: 250px; height: 55px;" width="250" height="55"/>
</a>

[![GitHub Stars](https://img.shields.io/github/stars/NanmiCoder/MediaCrawler?style=social)](https://github.com/NanmiCoder/MediaCrawler/stargazers)
[![GitHub Forks](https://img.shields.io/github/forks/NanmiCoder/MediaCrawler?style=social)](https://github.com/NanmiCoder/MediaCrawler/network/members)
[![GitHub Issues](https://img.shields.io/github/issues/NanmiCoder/MediaCrawler)](https://github.com/NanmiCoder/MediaCrawler/issues)
[![GitHub Pull Requests](https://img.shields.io/github/issues-pr/NanmiCoder/MediaCrawler)](https://github.com/NanmiCoder/MediaCrawler/pulls)
[![License](https://img.shields.io/github/license/NanmiCoder/MediaCrawler)](https://github.com/NanmiCoder/MediaCrawler/blob/main/LICENSE)
[![中文](https://img.shields.io/badge/🇨🇳_中文-当前-blue)](README.md)
[![English](https://img.shields.io/badge/🇺🇸_English-Available-green)](README_en.md)
[![Español](https://img.shields.io/badge/🇪🇸_Español-Available-green)](README_es.md)

</div>

---

## 🚨 重要提醒

> **⚠️ 仅限学习研究使用 ⚠️**
> 
> 本项目仅供学习和技术研究使用，严禁用于商业用途或违法行为。
> 
> 📚 [爬虫违法违规案例集](https://github.com/HiddenStrawberry/Crawler_Illegal_Cases_In_China) | 📖 [详细免责声明](#disclaimer)

---

## 📖 项目概述

**MediaCrawler** 是一个功能强大、易于使用的**多平台社交媒体数据采集工具**，专为学习和研究目的而设计。

### 🎯 核心特性

- **🔧 零逆向工程**：基于 Playwright 浏览器自动化，无需复杂的JS逆向
- **🌐 多平台支持**：支持7大主流社交媒体平台
- **⚡ 高效稳定**：智能登录态管理，稳定的数据采集
- **📊 灵活存储**：支持多种数据存储格式（MySQL、CSV、JSON）
- **🔄 代理支持**：内置IP代理池，提升采集稳定性

### 🏗️ 技术架构

- **核心框架**：基于 [Playwright](https://playwright.dev/) 浏览器自动化
- **编程语言**：Python 3.9+
- **架构设计**：异步爬虫 + 企业级代码架构
- **登录方式**：二维码登录、手机号登录、Cookie登录

## 📱 支持平台

<div align="center">

| 平台 | 关键词搜索 | 指定帖子爬取 | 评论抓取 | 创作者主页 | 登录态缓存 | IP代理池 | 词云图生成 |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| **小红书** | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| **抖音** | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| **快手** | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| **哔哩哔哩** | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| **微博** | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| **百度贴吧** | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| **知乎** | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |

</div>

---

## 🚀 快速开始

> 💡 **如果这个项目对您有帮助，请给个 ⭐ Star 支持一下！**

### 📋 环境要求

#### 🐍 Python 环境
- **版本要求**：Python 3.9 或更高版本
- **推荐工具**：[uv](https://docs.astral.sh/uv/getting-started/installation) (现代Python包管理器)

#### 🟢 Node.js 环境
- **版本要求**：Node.js >= 16.0.0
- **下载地址**：https://nodejs.org/

### 🛠️ 安装步骤

#### 1️⃣ 克隆项目
```bash
git clone https://github.com/NanmiCoder/MediaCrawler.git
cd MediaCrawler
```

#### 2️⃣ 安装依赖（推荐使用 uv）
```bash
# 使用 uv 同步所有依赖
uv sync
```

<details>
<summary>💡 使用传统方式安装（不推荐）</summary>

```bash
# 创建虚拟环境
python -m venv venv

# 激活虚拟环境
# Windows:
venv\Scripts\activate
# macOS/Linux:
source venv/bin/activate

# 安装依赖
pip install -r requirements.txt
```
</details>

#### 3️⃣ 安装浏览器驱动
```bash
# 安装 Playwright 浏览器驱动
uv run playwright install
```

### 🚀 运行示例

```bash
# 爬取小红书关键词搜索结果
uv run main.py --platform xhs --lt qrcode --type search

# 爬取指定帖子详情
uv run main.py --platform xhs --lt qrcode --type detail

# 查看所有支持的平台和参数
uv run main.py --help
```

### 📝 配置说明

主要配置文件位于 `config/base_config.py`：

```python
# 平台选择
PLATFORM = "xhs"  # 支持: xhs, dy, ks, bili, wb, tieba, zhihu

# 搜索关键词
KEYWORDS = "编程副业,编程兼职"

# 登录方式
LOGIN_TYPE = "qrcode"  # 支持: qrcode, phone, cookie

# 爬取类型
CRAWLER_TYPE = "search"  # 支持: search, detail, creator

# 是否启用评论抓取
ENABLE_GET_COMMENTS = True

# 是否启用代理
ENABLE_IP_PROXY = False
```

---

## 📊 数据存储

MediaCrawler 支持多种数据存储方式，满足不同需求：

### 💾 存储选项

| 存储方式 | 说明 | 优势 | 配置 |
|:---:|:---|:---|:---|
| **MySQL** | 关系型数据库存储 | 结构化查询、数据关联 | 需要预先创建数据库 |
| **CSV** | 表格文件存储 | 易于导入Excel分析 | 保存到 `data/` 目录 |
| **JSON** | 结构化文件存储 | 保持数据完整结构 | 保存到 `data/` 目录 |

### 🔧 数据库初始化
```bash
# 首次使用 MySQL 存储时，需要初始化数据库表结构
python db.py
```

---

## 📖 详细文档

### 📚 完整指南
- 🌐 **[在线文档](https://nanmicoder.github.io/MediaCrawler/)**：完整的使用指南和FAQ
- 📖 **[爬虫教程](https://github.com/NanmiCoder/CrawlerTutorial)**：免费的爬虫学习教程

### 🛠️ 高级功能
- 🔧 **[CDP模式使用指南](docs/CDP模式使用指南.md)**：连接本地浏览器
- 🌐 **[代理使用说明](docs/代理使用.md)**：IP代理池配置
- ☁️ **[词云图生成](docs/词云图使用配置.md)**：评论数据可视化

---

## 🔥 MediaCrawlerPro 企业版

<div align="center">

### 🚀 更强大的功能，更优雅的架构！

<a href="https://github.com/MediaCrawlerPro">
<img src="https://img.shields.io/badge/MediaCrawlerPro-企业级版本-red?style=for-the-badge&logo=github" alt="MediaCrawlerPro"/>
</a>

</div>

#### 🎯 核心功能升级
- ✅ **断点续爬功能** - 支持中断恢复
- ✅ **多账号 + IP代理池** - 企业级反爬方案  
- ✅ **去除 Playwright 依赖** - 更轻量级
- ✅ **完整 Linux 环境支持** - 服务器部署友好

#### 🏗️ 架构设计优化
- ✅ **企业级代码质量** - 适合大型项目
- ✅ **高扩展性设计** - 易于二次开发
- ✅ **解耦 JS 签名逻辑** - 更易维护

#### 🎁 额外功能
- ✅ **桌面端视频下载器** - 全栈项目学习
- ✅ **多平台信息流推荐** - HomeFeed功能
- 🔄 **AI Agent 开发中** - 智能化数据处理

**👉 [了解更多 MediaCrawlerPro](https://github.com/MediaCrawlerPro)**

---

## 🤝 社区与支持

### 💬 加入社区
<div align="center">

[![微信交流群](https://img.shields.io/badge/💬_微信群-加入讨论-07C160?style=for-the-badge)](https://nanmicoder.github.io/MediaCrawler/%E5%BE%AE%E4%BF%A1%E4%BA%A4%E6%B5%81%E7%BE%A4.html)
[![在线文档](https://img.shields.io/badge/📖_文档-查看指南-blue?style=for-the-badge)](https://nanmicoder.github.io/MediaCrawler/)

</div>

### 📚 学习资源
- 🎓 **[知识付费栏目](https://nanmicoder.github.io/MediaCrawler/%E7%9F%A5%E8%AF%86%E4%BB%98%E8%B4%B9%E4%BB%8B%E7%BB%8D.html)**：深度学习项目架构和爬虫技术
- 📖 **[作者介绍](docs/作者介绍.md)**：了解项目创作者
- 🔧 **[开发者咨询](docs/开发者咨询.md)**：技术咨询服务

---

## ⭐ Star 趋势

<div align="center">

如果这个项目对您有帮助，请给个 ⭐ **Star** 支持一下！

[![Star History Chart](https://api.star-history.com/svg?repos=NanmiCoder/MediaCrawler&type=Date)](https://star-history.com/#NanmiCoder/MediaCrawler&Date)

</div>

---

## 🎉 赞助商

### 💰 赞助展示

<div align="center">

<a href="https://www.swiftproxy.net/?ref=nanmi">
<img src="docs/static/images/img_5.png" alt="SwiftProxy" width="600"/>
<br/>
<b>SwiftProxy</b> - 90M+ 全球高质量纯净住宅IP，注册即享500MB免费流量
<br/>
<code>专属折扣码：GHB5 享受九折优惠！</code>
</a>

---

<a href="https://www.tkyds.com/?=MediaCrawler">
<img src="docs/static/images/img_6.png" alt="TK云大师" width="600"/>
<br/>
<b>TK云大师</b> - 专业TikTok矩阵系统，AI赋能自动化，轻松管理上万账号！
</a>

---

<a href="https://sider.ai/ad-land-redirect?source=github&p1=mi&p2=kk">
<b>🤖 Sider - 全网最火的 ChatGPT 插件，AI体验拉满！</b>
</a>

</div>

### 🤝 成为赞助者

**成为赞助者，您的产品将在这里展示，每天获得大量曝光机会！**

**📞 联系方式**：
- 💬 微信：`yzglan`
- 📧 邮箱：`relakkes@gmail.com`

---

## 📚 参考致谢

### 🛠️ 技术参考
- **[ReaJason/xhs](https://github.com/ReaJason/xhs)** - 小红书客户端参考
- **[SmsForwarder](https://github.com/pppscn/SmsForwarder)** - 短信转发功能
- **[ngrok](https://ngrok.com/docs/)** - 内网穿透工具

### 💖 特别感谢

<div align="center">

<a href="https://www.jetbrains.com/?from=MediaCrawler">
    <img src="https://www.jetbrains.com/company/brand/img/jetbrains_logo.png" width="200" alt="JetBrains" />
    <br/>
    <b>感谢 JetBrains 为本项目提供免费开源许可证支持！</b>
</a>

</div>


# 免责声明
<div id="disclaimer"> 

## 1. 项目目的与性质
本项目（以下简称“本项目”）是作为一个技术研究与学习工具而创建的，旨在探索和学习网络数据采集技术。本项目专注于自媒体平台的数据爬取技术研究，旨在提供给学习者和研究者作为技术交流之用。

## 2. 法律合规性声明
本项目开发者（以下简称“开发者”）郑重提醒用户在下载、安装和使用本项目时，严格遵守中华人民共和国相关法律法规，包括但不限于《中华人民共和国网络安全法》、《中华人民共和国反间谍法》等所有适用的国家法律和政策。用户应自行承担一切因使用本项目而可能引起的法律责任。

## 3. 使用目的限制
本项目严禁用于任何非法目的或非学习、非研究的商业行为。本项目不得用于任何形式的非法侵入他人计算机系统，不得用于任何侵犯他人知识产权或其他合法权益的行为。用户应保证其使用本项目的目的纯属个人学习和技术研究，不得用于任何形式的非法活动。

## 4. 免责声明
开发者已尽最大努力确保本项目的正当性及安全性，但不对用户使用本项目可能引起的任何形式的直接或间接损失承担责任。包括但不限于由于使用本项目而导致的任何数据丢失、设备损坏、法律诉讼等。

## 5. 知识产权声明
本项目的知识产权归开发者所有。本项目受到著作权法和国际著作权条约以及其他知识产权法律和条约的保护。用户在遵守本声明及相关法律法规的前提下，可以下载和使用本项目。

## 6. 最终解释权
关于本项目的最终解释权归开发者所有。开发者保留随时更改或更新本免责声明的权利，恕不另行通知。
</div>

---

<div align="center">

**🌟 如果本项目对您有帮助，请给个 Star 支持！🌟**

<a href="https://github.com/NanmiCoder/MediaCrawler">
<img src="https://img.shields.io/github/stars/NanmiCoder/MediaCrawler?style=social" alt="GitHub stars"/>
</a>

**MediaCrawler - 让数据采集更简单！**

---

© 2024 MediaCrawler | [许可证](LICENSE) | [在线文档](https://nanmicoder.github.io/MediaCrawler/)

</div>
