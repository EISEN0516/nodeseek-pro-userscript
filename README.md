# Nodeseek Max-iSen (低等级过滤增强版)

> 本脚本为针对 **NodeSeek / DeepFlood** 论坛的体验增强油猴脚本，在保留原版全部能力的基础上，**重点重构并强化了「低等级内容屏蔽」功能**，支持按真实作者等级与关键词双模式智能过滤。

---

## 🚀 安装链接

* **[👉 点击直接安装 / 更新本增强版脚本](https://raw.githubusercontent.com/tonly6679-star/nodeseek-pro-userscript/main/Nodeseek%20Pro.user.js)**
* **[📦 GitHub Releases 页面](https://github.com/tonly6679-star/nodeseek-pro-userscript/releases)**
* **[💻 GitHub 仓库主页](https://github.com/tonly6679-star/nodeseek-pro-userscript)**

> [!TIP]
> 本版本已独立设置命名空间与更新源，可与原版独立共存或单独使用，不用担心被原版自动更新覆盖。

---

## 📢 开源声明与致谢

- 本项目基于原作者 **EISEN0516** 的优秀开源项目 [EISEN0516/nodeseek-pro-userscript](https://github.com/EISEN0516/nodeseek-pro-userscript) 进行二次开发与增强。
- 原版仓库地址：[https://github.com/EISEN0516/nodeseek-pro-userscript](https://github.com/EISEN0516/nodeseek-pro-userscript)
- 原版 GreasyFork 地址：[https://greasyfork.org/zh-CN/scripts/588182-nodeseek-max-isen](https://greasyfork.org/zh-CN/scripts/588182-nodeseek-max-isen)
- 本项目所修改的增强功能已向原作者提交合并请求：[Pull Request #1](https://github.com/EISEN0516/nodeseek-pro-userscript/pull/1)。

---

## ✨ 本版本新增与重构重点

### 🚫 全新「低等级内容屏蔽」（按发帖/回帖真实等级过滤）

原版的“低等级内容屏蔽”实质上是检测带锁权限帖的门槛，无法过滤低等级新手、小号灌水发帖与回复。本版本进行了彻底重构：

#### 1. 真实作者账号等级识别
- 自动识别列表页发帖者、详情页主帖及每个楼层回帖者的真实等级（Lv.0 ~ Lv.6）。
- **多级智能缓存**：内置本地 `localStorage` 缓存（有效时间 7 天）与内存即时缓存，遇到过的用户**毫秒级瞬间隐藏，零网络开销与界面闪烁**。
- **后台平滑限速**：遇到新用户加入后台排队限速请求，避免短时间向论坛发出突发请求造成卡顿或限流。
- **白名单机制**：自动识别当前登录账号，**绝对不会误屏蔽你自己的发言**。

#### 2. 双列联动控制面板
进入设置面板 **「06 🚫 过滤设置」 -> 「低等级内容屏蔽」** 即可直观配置：

| 配置项 | 选项 / 功能说明 |
| :--- | :--- |
| **屏蔽目标等级** | 自由选择屏蔽阈值：<br>• `屏蔽 1 级及以下 (Lv.0 ~ Lv.1)`<br>• `屏蔽 2 级及以下 (Lv.0 ~ Lv.2)`<br>• `屏蔽 3 级及以下 (Lv.0 ~ Lv.3)` |
| **屏蔽触发模式** | • **屏蔽全局**：目标等级的所有发帖与回帖无条件彻底隐藏。<br>• **屏蔽关键词**：仅当目标等级用户发布的内容**命中关键词**时才拦截，正常交流讨论不误杀。 |
| **匹配关键词** | 自定义输入拦截词（中英文逗号隔开）；**留空时自动继承【关键字管理】里的屏蔽词**，无需重复录入。 |
| **细分范围控制** | 支持分别开关「作用于发帖 (主题列表)」与「作用于回复 (评论楼层)」。 |
| **即时热重载** | 设置面板修改保存后，无需刷新浏览器，页面内容**即时重新过滤生效**。 |

---

## 🛠️ 继承的原版主要功能

除上述重构的等级过滤外，本脚本完整保留并继承原版的全部优秀特性：

- **🎁 抽奖参与状态与提醒**：自动识别抽奖贴参与状态，支持临近开奖提醒与多渠道推送通知（Telegram、邮件、微信推送等）。
- **💬 楼中楼折叠与层级树**：针对帖内 @ 回复构建优雅嵌套层级，支持展开/收起。
- **👣 回帖足迹**：自动记录并标记自己曾回复过的帖子与对应楼层。
- **🧹 链接净化**：去除重定向跳转与推广/跟踪参数。
- **🖼️ 多图床上传**：内置 NodeImage 及多种可选图床上传支持。
- **🎨 视觉与体验优化**：时间中文化、已读变灰、代码高亮复制、移动端适配优化。

---

## 📥 安装与使用步骤

1. 安装浏览器脚本管理器扩展（如 [Tampermonkey 篡改猴](https://www.tampermonkey.net/) 或 ScriptCat）。
2. 点击 **[直接安装脚本](https://raw.githubusercontent.com/tonly6679-star/nodeseek-pro-userscript/main/Nodeseek%20Pro.user.js)**，并在弹出的管理器页面中点击“安装”。
3. 访问 [NodeSeek 论坛](https://www.nodeseek.com/)，在右上角悬浮球或菜单中打开设置。
4. 切换到 **「06 过滤设置」**，根据需要配置等级与关键词过滤规则即可！
