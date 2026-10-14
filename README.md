[README.md](https://github.com/user-attachments/files/33415344/README.md)
<div align="center">

![Life as a World · 把生活变成一个世界](docs/preview-world.png)

<a id="chinese"></a>

# 把生活变成一个世界

### Life as a World

**把散落在相册、备忘录、聊天框和文件夹里的碎片，  
变成一座可以走进去、并随你的记录持续生长的岛屿世界。**

![在线体验](https://img.shields.io/badge/在线体验-进入世界-8F7CFF?style=for-the-badge)

![零依赖](https://img.shields.io/badge/依赖-0-FFD166?style=for-the-badge)

![纯前端](https://img.shields.io/badge/架构-纯前端-6fdcae?style=for-the-badge)

[**简体中文**](#chinese) · [English](#english)

</div>

---

## 目录

- [这是什么](#这是什么)
- [世界构成](#世界构成)
- [五种记录类型](#五种记录类型)
- [功能一览](#功能一览)
- [快速开始](#快速开始)
- [项目结构](#项目结构)
- [技术实现](#技术实现)
- [浏览器支持](#浏览器支持)
- [数据与隐私](#数据与隐私)
- [路线图](#路线图)
- [许可](#许可)

---

## 这是什么

一个**纯前端的 2D 像素风互动网页应用**。它不是一个用来展示的静态页面，而是以「记录进入世界、世界随时间生长」为核心的使用闭环：

```
    ┌──────────────────────────────────────────────┐
    │                                              │
    ▼                                              │
  记录  ──▶  世界生长  ──▶  探索  ──▶  分享  ──▶  ─┘
 写一条      岛上多一个      走进去看    好友可见
             真实的物体
```

你写下一条记忆，岛上就亮起一颗星；你完成一个目标，岛上就长出一棵树。世界不是背景板，而是你生活的一份投影。

> [!NOTE]  
> 整个项目**没有一张下载来的图片素材**。海洋的每一道浪、岛屿的每一条海岸线、树、灯塔、码头、藏书塔、画室、火箭……全部由 Canvas 在运行时绘制。换一台电脑打开，它会重新画一遍，但画出来的是同一个世界。

![主世界](docs/preview-world.png)

*在世界地图上总览：中央为温暖港湾，四周由金色道路与浮桥接驳。*

---

## 世界构成

### 六座内置岛

| 岛屿          | 承载的内容             | 主题色       |
| :---------- | :---------------- | :-------- |
| 🏡 **温暖港湾** | 朋友、家庭、值得纪念的时刻     | `#ffb26b` |
| 📚 **知识岛**  | 课程、比赛、项目、学习经历     | `#6fb4ff` |
| 🌳 **回忆森林** | 照片、重要时刻、个人故事      | `#6fdcae` |
| 🎨 **创作岛**  | 绘画、音乐、摄影、设计作品     | `#ff9ad5` |
| 🚀 **未来之岛** | 梦想、计划、想完成的事情      | `#b79cff` |
| 🎵 **爱乐之城** | 导入你喜欢的音乐，让旋律在岛上流淌 | `#ffd166` |

### 自建岛（无上限）

除了六座内置岛，你可以随时添加自己的岛：命名、挑选超链接图标、选择它长在哪座岛旁边、选择它的主题形态。

自建岛提供五种成套的视觉主题：

| 主题       | 岛上的样子           |
| :------- | :-------------- |
| `garden` | 花园 · 木屋、画架、花丛   |
| `valley` | 山谷 · 石塔、书堆、松林   |
| `market` | 灯市 · 连排小屋、码头、街灯 |
| `star`   | 星光台 · 穹顶、尖塔、光环  |
| `grove`  | 幽林 · 空心树、蘑菇、藤灯  |

世界尺寸会随自建岛数量自动向外扩张，新岛按同心环依次落位，并自动避开已有岛屿。

---

## 五种记录类型

每种记录类型都会在世界里留下**不同的痕迹**，而不是同一种图标换个颜色。

| 类型                 | 在世界里的变化                       |
| :----------------- | :---------------------------- |
| ⭐ **记忆** `memory`  | 岛上亮起一颗星星，悬浮在记忆落点上方，自带一圈柔和光晕   |
| 🌱 **目标** `goal`   | 岛上长出一棵成长树。树只增不减——目标完成与否，都留在岛上 |
| 🏔 **旅行** `travel` | 按顺序解锁新风景：石拱门 → 热气球 → 瀑布 ……    |
| 🎵 **音乐** `music`  | 化作悬浮音符与旋转黑胶唱片，点击即可播放          |
| ✦ **回顾** `recall`  | 重新点亮一颗已有的星星，让旧记忆回到眼前          |

---

## 功能一览

### 📝 记录与编辑

- 选岛、起标题、写正文（可当日记写，多行长文不限）
- 从相册直接导入图片，自动压缩后存入本地
- 保存即入世界——新记忆会立刻成为岛上可点击的物体

![记录编辑器](docs/preview-editor.png)

### 🎮 世界探索

点击任意一座岛即可切换进**探索视角**：画面放大、显示岛上道路与记忆物体，并生成一个可操控的角色。

- **360° 自由方向盘**——不再是固定在屏幕角落的十字键，而是半透明、跟着手指走的方向盘：你在哪里按下，哪里就是控制中心，朝任意角度拖动即可控制方向
- 同时保留键盘方向键与点击地面移动
- 靠近带链接的物体时**自动弹出详情卡**，离开后关闭，再次靠近可重新触发
- 移动端全程支持触摸操作

![岛屿探索](docs/preview-explore.png)

### 🎵 爱乐之城

- 支持批量导入本地音频（MP3 / WAV / M4A / OGG / FLAC 等）
- 每条音乐成为岛上一个可点击的记忆点，视觉上是音符或旋转黑胶
- 点播时**环境背景音自动暂停**，单曲结束后恢复
- 较大的音频优先存入 IndexedDB，降低本地存储压力
- 主世界最多显示 7 枚独立音符，更多音乐聚合为「旋律匣 · N 首」，点击进入音乐区域，**所有音乐仍可完整播放**

![爱乐之城](docs/preview-music.png)

### 👥 账号与社交

- 注册、登录、退出与本机会话维持
- 账号创建后自动生成一串**专属 ID**，作为好友系统的唯一索引
- 支持输入好友 ID 或通过邀请链接建立关系，**双向写入**——双方的好友列表里都会出现对方
- 进入好友世界时顶部显示只读横幅，可随时「刷新最新」或「返回我的世界」
- 打开好友的某条记忆，可以分别**点赞**与**评论**，互动结果对双方及相关好友可见；详情页约每 7 秒自动重新读取一次，因此不必手动刷新

### 🏝 岛屿特色

每座岛都有一个可以点下去的发光物件，触发后给出三层反馈：随机内容提示、粒子特效，以及一声清脆的音效。

| 岛屿   | 特色功能 | 点下去会发生什么                                |
| :--- | :--- | :-------------------------------------- |
| 温暖港湾 | 港湾灯语 | 灯塔把最早的一段陪伴照出来                           |
| 知识岛  | 知识星图 | 从两段学习内容里寻找同一颗词星                         |
| 回忆森林 | 回声萤火 | 同一月份、不同年份的两段记忆发生一次短暂回声                  |
| 创作岛  | 灵感棱镜 | 把最近的作品放进棱镜，折出一张原创灵感卡                    |
| 未来之岛 | 未来信箱 | 给未来的自己写一句话，封存 1 个月 / 半年 / 1 年 / 3 年后再开启 |
| 爱乐之城 | 节拍花园 | 挑一段旋律，让音乐暂时接管这片海                        |
| 自建岛  | 主题空间 | 按所选主题显示花语温室、山谷回铃、灯市长街、星光甲板或幽林树洞         |

每座岛还有一个「发现彩蛋」按钮——彩蛋是围绕该岛主题**原创写成**的短句，不复刻任何已有作品的角色、名称或世界观。

### 🐛 岛屿生态

岛屿生态不是预先摆好的装饰。系统按每座岛上**真实记录的数量**换算出居民只数（`0 → 1 → 2 → 4 → 7 → 10`），写得越多，岛上越热闹。

八种居民全部为原创设定：

| 居民      | 栖息地  | 设定                   |
| :------ | :--- | :------------------- |
| 🦀 港灯小蟹 | 温暖港湾 | 天亮以前，它替你守着港湾的那盏灯     |
| 🐛 页栖灯虫 | 知识岛  | 书页翻得越多，纸缝里越容易亮起一小盏光  |
| ✦ 苔背铃兽  | 回忆森林 | 它把旧时光背在背上，走得很慢，铃铛很轻  |
| 🪶 墨羽织匠 | 创作岛  | 把你写完的句子，一根一根织成羽毛     |
| ✨ 星砂引路兽 | 未来之岛 | 它踏过的地方，会留下会发光的星砂     |
| 🐋 音潮鲸  | 爱乐之城 | 旋律沉进海湾，海面上会浮起一枚星形的呼吸 |
| 🐬 和声跃豚 | 爱乐之城 | 节奏轻快的时候，会有小豚从浪里跃出来   |
| 🫧 微光浮灵 | 自建岛  | 新岛上的第一户小居民，靠微光生活     |

### 📚 世界档案与导出

档案**只读取已有记忆，不修改原始数据结构**——同一个世界可以被重新读五遍：

| 视图    | 回答的问题                  |
| :---- | :--------------------- |
| 总览    | 有多少座岛、多少条记录、分布在哪些年份    |
| 时光长河  | 所有内容按时间排成一条河，看见自己的节奏   |
| 记忆星图  | 把记忆铺开成一张星图，相近的内容自然靠在一起 |
| 今日回声  | 把今天和往年同一天放在一起          |
| 世界编年史 | 按年或按岛，重新编排整段生活         |

- **世界编年史**支持按年份 / 按岛屿两种维度重排，并导出 **PNG 长图**与 **PDF**
- 日期统一为完整中文格式（「十月十日」而不是「1010 月」），页面、长图与 PDF 三处保持一致
- **相关旧碎片**：导入新内容时，系统会自动寻找来源不同却彼此相关的旧记录，例如同一天里另一段音乐、日记里提到过的那本书、同一地点不同年份拍下的照片
- 支持导出整份世界数据，也可以重置为示例世界（重置前会提醒保留副本）

![世界档案](docs/preview-archive.png)

---

## 快速开始

### 方式一：单文件版（最简单）

下载仓库根目录的 `life-as-a-world-polished.html`，双击用浏览器打开即可。所有代码、样式与逻辑都在这一个文件里。

### 方式二：部署 `web/` 目录

`web/` 是一个纯静态站点，可直接上传到任意静态托管平台（GitHub Pages / Netlify / Vercel / Cloudflare Pages / Ship.page 等）。

```bash
# 以 GitHub Pages 为例
git add web
git commit -m "deploy: life as a world"
git push origin main
# 然后在仓库 Settings → Pages 中选择分支与目录：/web
```

### 方式三：本地预览

因为使用了 `localStorage` 与 `IndexedDB`，建议通过 HTTP 服务打开，而不是直接双击 `index.html`：

```bash
cd web
python -m http.server 8080
# 打开 http://localhost:8080
```

或者：

```bash
npx serve web
```

---

## 项目结构

```
.
├── life-as-a-world-polished.html    # 单文件版（约 408 KB，含全部代码）
├── docs/                            # README 展示截图
│   ├── preview-world.png
│   ├── preview-explore.png
│   ├── preview-editor.png
│   ├── preview-music.png
│   └── preview-archive.png
└── web/                             # 站点目录（三文件结构）
    ├── index.html                   # 页面结构（254 行）
    ├── style.css                    # 视觉与响应式（693 行）
    └── app.js                       # 全部逻辑（6599 行）
```

---

## 技术实现

### 零素材

| 指标          | 数值                                              |
| :---------- | :---------------------------------------------- |
| 外部图片素材      | **0 张**                                         |
| 外部字体 / 图标文件 | **0 个**                                         |
| 第三方运行时依赖    | **0 个**                                         |
| 程序化像素精灵     | **约 40 种**（树、房屋、灯塔、码头、小船、藏书塔、空心树、画室、尖塔、穹顶、火箭……） |
| 地形分带        | **6 层**（深海 / 浅海 / 泡沫 / 沙滩 / 草地 / 核心区）           |

海洋贴图采用**周期无缝平铺**，因此世界在视觉上没有边界。1 个艺术像素等于 3 个 CSS 像素（`PX = 3`），世界初始尺寸为 `340 × 460` 艺术像素，随自建岛数量自动扩张。

### 技术栈

| 层面    | 实现                                             |
| :---- | :--------------------------------------------- |
| 渲染    | Canvas 2D，程序化生成地形、海岸线与全部像素精灵                   |
| 音效    | Web Audio API 实时合成——环境音、风铃、庆祝音阶、旋律，**无外部音频文件** |
| 结构与样式 | 原生 HTML + CSS，无框架、无构建步骤                        |
| 本地存储  | `localStorage`（世界数据） + `IndexedDB`（大音频文件）      |
| 云端同步  | 可选的账号与好友同步服务（WorkBuddy 托管后端）                   |
| 导出    | Canvas 合成 PNG 长图；按页面分片生成 PDF                   |

### 数据存储

| 键 / 库                       | 用途                           |
| :-------------------------- | :--------------------------- |
| `lifeWorld.v1`              | 当前世界的完整数据（名称、岛屿、记忆）          |
| `lifeWorld.uid`             | 记录上次登录的账号 ID                 |
| `lifeWorldAudio`（IndexedDB） | 大体积音频 Blob，避免撑爆 localStorage |

写入 `localStorage` 前会先做一次快照处理：把已存入 IndexedDB 的音频从数据里剔除，只保留条目信息。

### 代码模块索引

`web/app.js` 按功能分段组织，便于按需定位：

| 段落               | 职责                         |
| :--------------- | :------------------------- |
| `0. 工具`          | 通用辅助函数                     |
| `1. 世界配置`        | 岛屿定义、自建岛主题、世界尺寸            |
| `2 / 2b. 贴图`     | 深海无缝贴图、地形贴图生成              |
| `3. 桥梁 / 小径层`    | 岛屿间的道路与浮桥                  |
| `4. 像素精灵工厂`      | 全部精灵的程序化绘制                 |
| `5. 场景物件布置`      | 树木、装饰物、建筑落位                |
| `6. 岛屿地标 & 视觉配置` | 每座岛的视觉参数                   |
| `7. 状态与存储`       | `state` 管理、localStorage 读写 |
| `8. 相机与输入`       | 缩放、拖拽、键盘与触摸                |
| `9. 渲染`          | 主渲染循环                      |
| `10 / 10b / 10c` | UI、记录完成演出、小地图              |
| `11 / 11b / 11c` | 环境音、账号与云服务、音乐导入播放          |
| `12 / 12e`       | 启动、世界档案、岛屿生态与编年史           |

---

## 浏览器支持

| 浏览器           | 支持            |
| :------------ | :------------ |
| Chrome / Edge | ✅ 推荐          |
| Safari（含 iOS） | ✅             |
| Firefox       | ✅             |
| 移动端浏览器        | ✅ 已适配触摸操作与安全区 |

音频播放依赖浏览器的自动播放策略，首次播放需要一次用户点击。

---

## 数据与隐私

- 世界数据默认保存在**你自己的浏览器本地**，不上传到任何服务器
- 只有当你创建账号并使用好友功能时，公开世界与互动数据才会通过同步服务交换
- 上传到好友世界的照片、日记和音乐，请确认对方可以查看；必要时先做脱敏处理
- 不同域名或不同浏览器之间的本地数据**不会自动互通**

---

## 路线图

- [ ] 世界数据备份与恢复
- [ ] 好友动态通知
- [ ] 记忆导出相册
- [ ] 更多原创生态居民
- [ ] 编年史模板
- [ ] 好友共同记忆册
- [ ] 更明确的隐私权限控制

---

## 许可

本项目暂未指定开源许可。如需开源，建议在仓库根目录添加 `LICENSE` 文件（例如 [MIT](https://choosealicense.com/licenses/mit/)）。

如果你想在作品或文章中使用本项目，欢迎注明出处。

---

  


<a id="english"></a>

<div align="center">

# Life as a World

**Turn the fragments scattered across your photo album, notes, chats and folders  
into an island world you can walk into — one that keeps growing with every entry you write.**

[简体中文](#chinese) · [**English**](#english)

</div>

---

## Table of Contents

- [What Is This](#what-is-this)
- [The World](#the-world)
- [Five Entry Types](#five-entry-types)
- [Features](#features)
- [Getting Started](#getting-started)
- [Project Structure](#project-structure)
- [Under the Hood](#under-the-hood)
- [Browser Support](#browser-support)
- [Data & Privacy](#data--privacy)
- [Roadmap](#roadmap)
- [License](#license)

---

## What Is This

A **pure front-end, 2D pixel-art interactive web app**. It is not a static showcase page — its whole design revolves around one loop: *entries go in, the world grows out.*

```
    ┌──────────────────────────────────────────────┐
    │                                              │
    ▼                                              │
 Write  ──▶  World grows  ──▶  Explore  ──▶  Share ─┘
 an entry     a real object      walk in      friends
              appears           and look     can see
```

Write down a memory and a star lights up on your island. Finish a goal and a tree grows. The world is not a backdrop — it is a projection of your own life.

> [!NOTE]  
> This project contains **zero downloaded image assets**. Every wave, every coastline, every tree, lighthouse, dock, library tower, studio and rocket is drawn by Canvas at runtime. Open it on another computer and it will draw itself again — the same world, from the same code.

![Main world](docs/preview-world.png)

*World overview: the Warm Harbor sits at the center, connected to the surrounding islands by golden roads and floating bridges.*

---

## The World

### Six Built-in Islands

| Island                   | What it holds                                           | Accent    |
| :----------------------- | :------------------------------------------------------ | :-------- |
| 🏡 **Warm Harbor**       | Friends, family, moments worth remembering              | `#ffb26b` |
| 📚 **Isle of Knowledge** | Courses, competitions, projects, learning               | `#6fb4ff` |
| 🌳 **Memory Forest**     | Photos, milestones, personal stories                    | `#6fdcae` |
| 🎨 **Creation Isle**     | Drawing, music, photography, design                     | `#ff9ad5` |
| 🚀 **Isle of Futures**   | Dreams, plans, things you want to finish                | `#b79cff` |
| 🎵 **Music City**        | Import your own music and let it flow across the island | `#ffd166` |

### Custom Islands (Unlimited)

Beyond the six built-in islands, you can add as many of your own as you like — name it, pick a hyperlink icon, choose which island it grows next to, and choose its theme.

Five complete visual themes are available:

| Theme    | What it looks like                                   |
| :------- | :--------------------------------------------------- |
| `garden` | Garden · cottages, an easel, flower beds             |
| `valley` | Valley · a stone tower, book stacks, pines           |
| `market` | Lamp Market · rows of cottages, a dock, street lamps |
| `star`   | Star Deck · a dome, spires, light rings              |
| `grove`  | Deep Grove · a hollow tree, mushrooms, vine lamps    |


The world canvas expands outward automatically as you add islands. New islands are placed along concentric rings and never overlap existing ones.

---

## Five Entry Types

Each type leaves a **different trace** in the world — not the same icon in a different color.

| Type | What happens in the world |
| :--- | :--- |
| ⭐ **Memory** `memory` | A star lights up above the spot where the memory landed, wrapped in a soft halo |
| 🌱 **Goal** `goal` | A growth tree appears. It only ever grows — finished or not, it stays on the island |
| 🏔 **Travel** `travel` | Unlocks new scenery in order: stone arch → hot-air balloon → waterfall → … |
| 🎵 **Music** `music` | Becomes a floating note and a spinning vinyl record — click to play |
| ✦ **Recall** `recall` | Re-lights a star you wrote before, bringing an old memory back into view |

---

## Features

### 📝 Writing & Editing

- Choose an island, give it a title, write the body (treat it as a diary — long, multi-line entries are fine)
- Import images straight from your photo album; they are compressed and stored locally
- Save and it is in the world — the new entry immediately becomes a clickable object on the island

![Editor](docs/preview-editor.png)

### 🎮 Exploring the World

Click any island to switch into **explore mode**: the camera zooms in, roads and memory objects appear, and a controllable character is spawned.

- **360° free joystick** — no longer a D-pad pinned to a corner, but a semi-transparent stick that follows your finger: wherever you press becomes the control center, and you drag in any direction
- Keyboard arrow keys and click-to-move are still supported
- Approaching an object with a link **automatically opens its detail card**; move away and it closes, come back and it triggers again
- Fully touch-ready on mobile

![Explore mode](docs/preview-explore.png)

### 🎵 Music City

- Batch-import local audio (MP3 / WAV / M4A / OGG / FLAC, and more)
- Each track becomes a clickable point of interest on the island, shown as a note or a spinning vinyl
- Playback **automatically pauses the ambient background sound** and restores it when the track ends
- Larger files are kept in IndexedDB to relieve local storage pressure
- The main world shows up to 7 individual notes; beyond that they are grouped into a "Melody Box · N tracks" that opens the music area — **no track is ever lost or restricted**

![Music City](docs/preview-music.png)

### 👥 Accounts & Social

- Register, log in, log out, and stay signed in across sessions
- Every account gets an auto-generated **unique ID** that acts as the single index for the friend system
- Add friends by ID or invite link; the relation is written **both ways** — each side appears in the other's friend list
- Entering a friend's world shows a read-only banner at the top, with "Refresh" and "Back to my world" always available
- Open any memory in a friend's world to **like** and **comment** on it; results are visible to both sides and to mutual friends. The detail view re-reads the interaction document roughly every 7 seconds, so no manual refresh is needed

### 🏝 Island Specials

Every island has one glowing object you can click. Triggering it gives three layers of feedback: a random content hint, particle effects, and a crisp sound.

| Island | Special | What happens when you click it |
| :--- | :--- | :--- |
| Warm Harbor | Harbor Light | The lighthouse shines on your earliest memory of company |
| Isle of Knowledge | Knowledge Star Map | Finds a shared keyword between two pieces of learning |
| Memory Forest | Echo Fireflies | Two memories from the same month in different years briefly echo |
| Creation Isle | Inspiration Prism | Drops your latest work through a prism to refract an original idea card |
| Isle of Futures | Future Mailbox | Writes a line to your future self, sealed for 1 month / 6 months / 1 year / 3 years |
| Music City | Beat Garden | Picks a melody and lets it briefly take over the sea |
| Custom Island | Theme Space | Shows the matching theme space: flower greenhouse, valley chimes, lamp market, star deck, or hollow grove |

Each island also has a **"Discover the Easter egg"** button — every egg is a short line **written originally** for that island, copying no existing work's characters, names or worldbuilding.

### 🐛 Island Ecology

The ecology is not pre-placed decoration. The system derives the number of residents from **how many entries each island actually holds** (`0 → 1 → 2 → 4 → 7 → 10`). Write more, and the island gets livelier.

All eight residents are original creations:

| Resident | Habitat | Lore |
| :--- | :--- | :--- |
| 🦀 Harbor Crab | Warm Harbor | Before dawn, it keeps the harbor light for you |
| 🐛 Page Moth | Isle of Knowledge | The more pages turn, the more likely a small light flickers between them |
| ✦ Mossback Bellbeast | Memory Forest | It carries old times on its back — walks slowly, rings softly |
| 🪶 Inkfeather Weaver | Creation Isle | Weaves the sentences you finish, one by one, into feathers |
| ✨ Stardust Guide | Isle of Futures | Wherever it steps, it leaves glowing stardust |
| 🐋 Tidewhale | Music City | When a melody sinks into the bay, a star-shaped breath rises to the surface |
| 🐬 Harmony Dolphin | Music City | When the rhythm quickens, small dolphins leap out of the waves |
| 🫧 Glimmer Wisp | Custom Island | The first little resident of a new island — it lives on faint light |

### 📚 World Archive & Export

The archive is **read-only**: it reorganizes existing entries without ever changing the underlying data. The same world can be read five different ways:

| View | The question it answers |
| :--- | :--- |
| Overview | How many islands, how many entries, spread across which years |
| River of Time | Every entry laid out along a timeline — see your own rhythm |
| Memory Star Map | Entries spread into a star map, related ones naturally clustering |
| Echo of Today | Today, side by side with the same day in past years |
| World Chronicle | Re-arranged by year or by island |

- The **World Chronicle** can be reorganized by year or by island and exported as a **PNG long image** or a **PDF**
- Dates are normalized to full written form (never a mangled "month 1010"), consistent across the page, the long image and the PDF
- **Related old fragments**: when you import something new, the system automatically surfaces older entries from different sources that relate to it — another track from the same day, a book mentioned in a diary, photos of the same place in different years
- The full world data can be exported, or reset to a sample world (with a reminder to keep a copy first)

![World Archive](docs/preview-archive.png)

---

## Getting Started

### Option 1 — Single file (easiest)

Download `life-as-a-world-polished.html` from the repository root and open it in a browser. All code, styles and logic live in that one file.

### Option 2 — Deploy the `web/` folder

`web/` is a plain static site. Upload it to any static host (GitHub Pages / Netlify / Vercel / Cloudflare Pages / Ship.page, …).

```bash
# Example: GitHub Pages
git add web
git commit -m "deploy: life as a world"
git push origin main
# Then set Settings → Pages to serve the /web folder on your branch
```

### Option 3 — Local preview

Because the app uses `localStorage` and `IndexedDB`, serve it over HTTP rather than opening `index.html` directly from disk:

```bash
cd web
python -m http.server 8080
# open http://localhost:8080
```

Or:

```bash
npx serve web
```

---

## Project Structure

```
.
├── life-as-a-world-polished.html    # Single-file build (~408 KB, everything inlined)
├── docs/                            # Screenshots used by this README
│   ├── preview-world.png
│   ├── preview-explore.png
│   ├── preview-editor.png
│   ├── preview-music.png
│   └── preview-archive.png
└── web/                             # Site folder (three-file structure)
    ├── index.html                   # Markup (254 lines)
    ├── style.css                    # Visuals & responsive layout (693 lines)
    └── app.js                       # All logic (6,599 lines)
```

---

## Under the Hood

### Zero assets

| Metric | Value |
| :--- | :--- |
| External image assets | **0** |
| External font / icon files | **0** |
| Third-party runtime dependencies | **0** |
| Procedural pixel sprites | **~40** (trees, houses, lighthouse, dock, boat, library tower, hollow tree, studio, spire, dome, rocket, …) |
| Terrain bands | **6** (deep sea / shallow sea / foam / sand / grass / core) |

The ocean texture tiles **seamlessly**, so the world has no visible boundary. One art pixel equals 3 CSS pixels (`PX = 3`); the world starts at `340 × 460` art pixels and expands automatically as custom islands are added.

### Stack

| Layer | Implementation |
| :--- | :--- |
| Rendering | Canvas 2D — terrain, coastlines and every sprite generated procedurally |
| Audio | Web Audio API synthesis — ambient sound, wind chimes, celebration scales and melodies, **with no external audio files** |
| Structure & style | Vanilla HTML + CSS, no framework, no build step |
| Local storage | `localStorage` (world data) + `IndexedDB` (large audio blobs) |
| Cloud sync | Optional account & friend sync service (WorkBuddy hosted backend) |
| Export | Canvas-composited PNG long image; paged PDF generation |

### Storage keys

| Key / Store | Purpose |
| :--- | :--- |
| `lifeWorld.v1` | Full current world data (name, islands, entries) |
| `lifeWorld.uid` | ID of the last signed-in account |
| `lifeWorldAudio` (IndexedDB) | Large audio blobs, kept out of localStorage |

Before writing to `localStorage`, the app takes a snapshot: any audio already persisted in IndexedDB is stripped from the data, leaving only the entry metadata.

### Module map

`web/app.js` is organized into labeled sections so you can jump straight to what you need:

| Section | Responsibility |
| :--- | :--- |
| `0. Utils` | Shared helpers |
| `1. World config` | Island definitions, custom-island themes, world size |
| `2 / 2b. Textures` | Seamless deep-sea texture, terrain textures |
| `3. Bridges / paths` | Roads and floating bridges between islands |
| `4. Sprite factory` | Procedural drawing of every sprite |
| `5. Scene placement` | Trees, decorations and buildings |
| `6. Landmarks & visuals` | Per-island visual parameters |
| `7. State & storage` | `state` management, localStorage read/write |
| `8. Camera & input` | Zoom, drag, keyboard and touch |
| `9. Rendering` | Main render loop |
| `10 / 10b / 10c` | UI, post-save full-screen sequence, minimap |
| `11 / 11b / 11c` | Ambient audio, accounts & cloud, music import & playback |
| `12 / 12e` | Boot, world archive, island ecology & chronicle |

---

## Browser Support

| Browser | Support |
| :--- | :--- |
| Chrome / Edge | ✅ Recommended |
| Safari (incl. iOS) | ✅ |
| Firefox | ✅ |
| Mobile browsers | ✅ Touch controls and safe-area insets handled |

Audio playback follows each browser's autoplay policy — the first play requires a user gesture.

---

## Data & Privacy

- World data lives **in your own browser by default** and is not uploaded anywhere
- Only when you create an account and use the friend features does public-world and interaction data travel through the sync service
- Photos, diary entries and music you upload to a friend's world should be things you are comfortable sharing — desensitize first if needed
- Local data does **not** carry over between different domains or different browsers

---

## Roadmap

- [ ] World data backup & restore
- [ ] Friend activity notifications
- [ ] Memory export as an album
- [ ] More original ecology residents
- [ ] Chronicle templates
- [ ] Shared memory book for friends
- [ ] Finer-grained privacy controls

---

## License

No open-source license has been assigned yet. If you intend to open-source this project, add a `LICENSE` file at the repository root (for example [MIT](https://choosealicense.com/licenses/mit/)).

If you use this project in your own work or writing, a credit back to the repository is appreciated.

---

<div align="center">

**把生活变成一个世界 · Life as a World**

*写下的每一条，都在世界里留下了痕迹。*

</div>
