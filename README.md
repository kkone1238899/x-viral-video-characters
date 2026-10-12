# 人物构建

> 视频里人物前后长得不一样？这个库收集角色一致性构建的方法，每条都写清楚能帮你解决什么、怎么用它搞钱。
>
> A curated collection of character building & consistency prompts & skills for viral short videos, gathered from practitioners sharing on X.
> 
> Each entry answers two questions: what problem it solves (and who it's for), and how to make money with it.
> 
> Star counts verified via GitHub API on 2026-10-10. Continuously updated.

## 方法条目

角色一致性是 AI 视频最大的坑，下面三条是 X 实战派验证过的方法（每条注明出处）：

### 方法 1：定妆照身份锚

- **核心提炼**：2 人物 + 1 场景各拍一张定妆照，每镜生成必传这三张，否则外形跑偏。定妆照是"身份锚"不是参考图——锚定住，模型才不敢乱发挥
- **适用场景**：多镜连续短剧 / 漫剧，人物换镜就变脸
- **怎么用它搞钱**：稳定量产是接商单的前提，"人物不崩"本身就是溢价点
- **来源**：[@AI_DVD6](https://x.com/AI_DVD6/status/2106718752624541784)（完整 SOP 见 [scripts 库](https://github.com/kkone1238899/x-viral-video-scripts)）

### 方法 2：首帧母图全程沿用

- **核心提炼**：人物特征一次定死（年龄 / 发型 / 服装 / 配饰写全），第一帧做"母图"全程沿用，不每镜重新生成；道具提示词照着画面写，防前后矛盾
- **适用场景**：单人物短片，追求零崩坏
- **怎么用它搞钱**：一条片子一次过，不烧额度就是利润；拿"一次成片"当案例去谈客户
- **来源**：[@yangleiocx3](https://x.com/yangleiocx3/status/2108757102512472453)（完整流程见 [scripts 库](https://github.com/kkone1238899/x-viral-video-scripts)）

### 方法 3：Character Identity Lock

- **核心提炼**：先生成单人肖像锁定身份（Character Identity Lock），再做多视角参考表（正面 / 侧面 / 背面 / 表情）；同一角色换造型 / 受伤状态时，为同一角色 ID 另建状态参考，绝不静默重新设计
- **适用场景**：电影级 AI 短片，多造型、多情绪的复杂角色
- **怎么用它搞钱**：高端定制短片的门槛项，会这套才能接品牌单
- **来源**：[@meAsifAi](https://x.com/meAsifAi/status/2109235626440786388)（20 步制片蓝图见 [scripts 库](https://github.com/kkone1238899/x-viral-video-scripts)）

## 开源项目

| 项目 | Star | 一句话（解决什么问题 / 适合谁用） | 怎么用它搞钱 |
|---|---|---|---|
| [HBAI-Ltd/Toonflow-app](https://github.com/HBAI-Ltd/Toonflow-app) | 16,998 | AI 创作平台：智能分镜 + 短剧，角色一致性 | 动漫解说 / 漫剧账号 |

## 收录标准

- 来源：X 博主实战分享（原帖 / 评论区 / 引用链）及 GitHub 高星项目
- 每条格式：一句话（解决什么问题 / 适合谁用）+ 一条「怎么用它搞钱」
- Star 数为 2026-10-10 经 GitHub API 核验；持续收录中
- 去重：同一项目只收录一次，不堆 raw 链接

## 相关分类

- 总索引：[x-viral-video-skills](https://github.com/kkone1238899/x-viral-video-skills) —— 13 个分类导航
- [x-viral-video-scripts](https://github.com/kkone1238899/x-viral-video-scripts) —— 编剧 / 脚本
- [x-viral-video-hooks](https://github.com/kkone1238899/x-viral-video-hooks) —— 标题 / 5 秒钩子
- [x-viral-video-creative-direction](https://github.com/kkone1238899/x-viral-video-creative-direction) —— 创意总监
- [x-viral-video-directing](https://github.com/kkone1238899/x-viral-video-directing) —— 导演
- [x-viral-video-replication](https://github.com/kkone1238899/x-viral-video-replication) —— 复制爆款
- [x-viral-video-breakdown](https://github.com/kkone1238899/x-viral-video-breakdown) —— 拉片
- [x-viral-video-pipeline](https://github.com/kkone1238899/x-viral-video-pipeline) —— 流水线 / 生产管线
- [x-viral-video-de-ai](https://github.com/kkone1238899/x-viral-video-de-ai) —— 去 AI 味
- [x-viral-video-editing](https://github.com/kkone1238899/x-viral-video-editing) —— 视听剪辑技巧
- [x-viral-video-prompt-opt](https://github.com/kkone1238899/x-viral-video-prompt-opt) —— 提示词优化
- [x-viral-video-copywriting](https://github.com/kkone1238899/x-viral-video-copywriting) —— 文案
- [x-viral-video-showcase](https://github.com/kkone1238899/x-viral-video-showcase) —— X 病毒视频合集

## 投稿

发现好的人物构建 prompt / skill，欢迎提 Issue 或 PR（格式见 CONTRIBUTING.md）。

## 更新日志

- 2026-10-12：新增 3 条角色一致性方法
- 2026-10-11：首版，1 个项目，持续收录中
