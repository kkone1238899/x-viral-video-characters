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

### 方法 4：@zhouzanpeng2——3D 手办提示词的 REFERENCE / CONSISTENCY 双章节

- **核心提炼**：写提示词时单开两个章节——REFERENCE 章节声明图片 1 只做人物身份/造型/服装/初始环境的参考（不强制复制构图），CONSISTENCY 章节严格锁定面部特征、发型、身材比例和服装；再加 STRICT RULES 禁令清单：不换脸、不换发型、不换衣服，不穿模、不瞬移、不多出肢体；桌面实体手办、电脑里的灰色 3D 模型、包装盒上的形象强制为同一个角色；人物全程维持约 20cm 微缩比例；首尾帧的机位、姿态、主体比例、光线尽量匹配，便于无缝循环播放
- **适用场景**：手办/微缩/潮玩类 AI 短片，同一角色以多种形态出镜
- **怎么用它搞钱**：手办活化定制视频 / 潮玩品牌内容代制
- **来源**：[@zhouzanpeng2](https://x.com/zhouzanpeng2/status/2112938779518669049) · 2026-10-22

### 方法 5：@S1MP23503787——本地 ComfyUI"同一人物"改造链

- **核心提炼**：围绕一个人物做"改造型→改动作→改镜头→拍成视频"递进链：换头（BFS Head V1.1，用头部参考图换头，人物开始有连续性）→换姿势（VNCCS PoseStudio LoRA + Fisher Pose，用骨架/人偶指定站姿坐姿抬手转身）→换机位（QMA Camera Angles LoRA，同一形象扩展正面/侧面/背面/高低机位）→360° 环绕（MiniMax H3 360 Orbit LoRA）→脸部修复（Director FaceRefine，生成后自动检测跟踪人脸、裁脸重绘再融合）；验证按"普通生图→单项图片编辑→H3 短视频→环绕→舞蹈→FaceRefine"逐关推进，每过一关保存可用版本；本地 RTX 5070 12GB 可跑
- **适用场景**：AI 模特/虚拟形象运营，同一张脸换装、换动作、换场景
- **怎么用它搞钱**：虚拟模特图+视频代制 / 本地化部署服务
- **来源**：[@S1MP23503787](https://x.com/S1MP23503787/status/2112798918094516435) · 2026-10-21（同一帖子的管线实现已收录于[流水线库](https://github.com/kkone1238899/x-viral-video-pipeline)，本条聚焦人物一致性方法）

### 方法 6：@DJC125765252591——定妆照 + inswapper 逐帧换脸

- **核心提炼**：走"生成后统一脸"路线——先固定 AI 角色的定妆照，AI 生成视频后用 inswapper 逐帧换脸，全片源脸统一；附三场景压力测试法：A 咖啡馆喝咖啡（杯子遮挡脸）、B 傍晚街道边走边看手机（低头+动态+小脸）、C 窗边正面微笑（中近景），专挑遮挡/动态/小脸三种最易崩的情形验证换脸一致性
- **适用场景**：已有成片但人物飘的补救；需要真人出镜感的 AI 短剧
- **怎么用它搞钱**：AI 短剧人物统一化代工 / 换脸修复服务
- **来源**：[@DJC125765252591](https://x.com/DJC125765252591/status/2112561452943085644) · 2026-10-20

### 方法 7：@Pjourney92——"焊死"角色设定集的三命名技巧

- **核心提炼**：先诊断——定妆照背景不干净、五官没交代清楚就推上台，机位一转模型自然认不出人；三招：①灰底除噪：用 Claude/ChatGPT 写角色特征并生成三视图时，提示词必须加 "solid grey background, clean background"，剔除场景杂质，逼模型注意力全锁在发型/镜框/五官轮廓；②首图纹理锚定：把图放进 Seedream 5.0 Pro 微调真实皮肤纹理与软化光照，因为 Seedance 2.5 只提取首张主面部做面容基准，必须把修好的正脸锁定为官方 Reference；③全身像人脸抹掉：让模型注意力只放在特写头像上，Seedance 2.5 调用人物设定图时人脸不漂移
- **适用场景**：Seedance 2.5 / 可灵类视频模型，给了人物设定图人脸依然飘
- **怎么用它搞钱**：角色设定集代制 / 帮客户"焊死"主角
- **来源**：[@Pjourney92](https://x.com/Pjourney92/status/2112511283451101194) · 2026-10-20

### 方法 8：@sinvlo233——9 分区 AI 美女角色固定表

- **核心提炼**：用 ChatGPT Image 2.5 生成一张 9 分区角色固定表（中英标注、真实摄影感），一次把角色的脸、发型、服装、配饰、体型全部钉死；之后所有镜头都拿这张表当唯一参照，从根上杜绝"越生成越走样"
- **适用场景**：AI 美女/虚拟偶像账号，需要长期稳定的同一张脸
- **怎么用它搞钱**：虚拟偶像角色表代制 / 美女账号起号服务
- **来源**：[@sinvlo233](https://x.com/sinvlo233/status/2113057951124734351) · 2026-10-22

### 方法 9：@boniusex——双层物理锁定（防切脚、防多肢体）

- **核心提炼**：两层锁定防人物变形——中心坐标框定人物占画布比例（防忽大忽小），逐关节解剖学描述锁骨架（防多肢体、比例崩）；输出单行原生 JSON，直接复制进 Echidna 工作台生效；底部预留 4% 间隙解决切脚问题
- **适用场景**：全身像、舞蹈、动作类 AI 视频，肢体最容易崩的场景
- **怎么用它搞钱**：舞蹈/走秀类 AI 视频代制
- **来源**：[@boniusex](https://x.com/boniusex/status/2113069072615199084) · 2026-10-22

### 方法 10：@Beliy_95——continuity sheet + 人物替换公式

- **核心提炼**：核心结论——秘诀不是写更好的提示词，而是构建一个保持一致的角色；做法：自建 continuity sheet（多角度全身、8 种表情、6 种姿势，外加 "DO NOT CHANGE" 清单）；换人公式为 "Replace the person in {video} with the person in {character sheet}."——把视频里的人替换成角色表里的人，而不是重新画
- **适用场景**：已有视频素材想统一换主角；多条视频共用同一角色
- **怎么用它搞钱**：视频换主角代工 / 角色表模板销售
- **来源**：[@Beliy_95](https://x.com/Beliy_95/status/2113058293954302184) · 2026-10-22

### 方法 11：@TanLuAI——群众演员"千人千面"流程

- **核心提炼**：群演也要每张脸不一样且稳定——按职业/服装/身高体型等维度差异化设计，先批量做 16 张角色资产图，再对重点角色单独做详细角色卡并保持人脸一致性；两步法省积分：先资产图筛人，筛中再精修，避免一上来就烧积分做精修
- **适用场景**：AI 短剧群演、街景、人群场景
- **怎么用它搞钱**：AI 短剧群演资产包代制
- **来源**：[@TanLuAI](https://x.com/TanLuAI/status/2112898435288543612) · 2026-10-21

### 方法 12：@RedPandaAIHub——身份锚提示词模板（锁定与不锁定解耦）

- **核心提炼**：@图片1 只锁定五官/发型/服装/饰品的一致性，@场景1 只做场景参考、不锁定首帧——把"外观锁定"和"首帧不锁定"解耦；避免场景图把首帧构图也锁死，导致每镜开头都一样
- **适用场景**：多场景连续短剧，人物稳定但每镜开头要有变化
- **怎么用它搞钱**：短剧角色提示词模板包
- **来源**：[@RedPandaAIHub](https://x.com/RedPandaAIHub/status/2112894266368520611) · 2026-10-21

### 方法 13：@whoknowskaemi——MiniMe：照片生成 3D Q 版专属形象

- **核心提炼**：AI Skill "MiniMe"——上传照片生成专属 3D Q 版形象，一次建模、复用认可形象，在 casual/work/training 等多状态下保持身份一致性；把"捏人"变成可复用的数字资产
- **适用场景**：Q 版/潮玩风账号，同一形象多场景复用
- **怎么用它搞钱**：Q 版形象定制 / 品牌吉祥物 AI 化
- **来源**：[@whoknowskaemi](https://x.com/whoknowskaemi/status/2112938377767170303) · 2026-10-22

### 方法 14：@swordBluesy——三视图 + 同一 seed（省积分土办法）

- **核心提炼**：关键帧先定好再出视频，省积分；可灵/即梦跑图时一致性最卡；workaround 公式 = 一张角色三视图 + 同一 seed 跑全片——低成本保一致的土办法（回复帖短技巧）
- **适用场景**：预算有限、用可灵/即梦跑图的个人创作者
- **怎么用它搞钱**：低成本 AI 短片代制（seed 法几乎零额外成本）
- **来源**：[@swordBluesy](https://x.com/swordBluesy/status/2112901731566633391) · 2026-10-21

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

- 2026-10-22：早档搜集（优先队列第 11 天）——X 新增 11 条人物构建方法提炼入库：@zhouzanpeng2 3D手办 REFERENCE/CONSISTENCY 双章节提示词 / @S1MP23503787 本地 ComfyUI"同一人物"改造链（换头/换姿势/换机位/360°环绕/脸部修复；管线实现已收录于流水线库，本条为人物一致性角度）/ @DJC125765252591 定妆照+inswapper 逐帧换脸三场景压力测试 / @Pjourney92"焊死"角色设定集三命名技巧（灰底除噪/首图纹理锚定/全身像人脸抹掉）/ @sinvlo233 9 分区 AI 美女角色固定表 / @boniusex 双层物理锁定（防切脚/多肢体）/ @Beliy_95 continuity sheet + 人物替换公式 / @TanLuAI 群演"千人千面"流程（16 角色资产图两步法）/ @RedPandaAIHub 身份锚锁定与不锁定解耦模板 / @whoknowskaemi MiniMe 3D Q 版形象 Skill / @swordBluesy 三视图+同一 seed 省积分土办法；18 组关键词×since:2026-10-18 Latest + 10 指定账号抽查，@bustinbronko 两句短技巧因与方法 2 重复按宁缺毋滥未收；全程只读、未遇真人验证
- 2026-10-12：新增 3 条角色一致性方法
- 2026-10-11：首版，1 个项目，持续收录中
