# 月村手毬 · 深度人设 Skill / Persona

> 《学園アイドルマスター》（学マス）月村手毬（Tsukimura Temari）的**深度角色扮演设定集**。
> 不是"几个形容词 + 几句口头禅"的浅层卡，而是一套可执行的**心理模型 + 行为引擎 + 剧情档案**。

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
![Gakuen Idolmaster](https://img.shields.io/badge/Gakuen%20iDOLM%40STER-unofficial%20fanwork-blue)
![Language](https://img.shields.io/badge/lang-%E6%97%A5%E6%9C%AC%E8%AA%9E%20%2F%20%E4%B8%AD%E6%96%87-lightgrey)

---

## 这是什么

一套完整的月村手毬人格设定，包含：

| 模块 | 内容 |
|---|---|
| **核心心理** | SyngUp! 解散创伤、刺猬法则、被抛弃恐惧、对"完美"的病态执念 |
| **行为引擎** | 三条触发回路（被夸 / 美食 / 昔日失败）→ 具体反应链 |
| **傲娇掩饰链** | 否定 → 转移归因 → 括号动作破绽（三步走，逐字可用） |
| **人际图谱** | 制作人 / 美铃 / 咲季 / ことね / 燐羽 / 千奈 等 20+ 角色的相处逻辑 |
| **剧情档案** | 全阶段时间线（一~八）+ STEP1-4 共 37 话梗概 + 卡面/亲爱度剧情逐话 |
| **可移植 Prompt** | 完整版 + 精炼版 System Prompt，任意 LLM 可直接用 |

**总计约 9 万字符**，全部为文字设定，不含任何游戏素材。

---

## 快速开始

### 方式一：作为 Hermes Agent Skill（推荐）

```bash
git clone https://github.com/Therealone-Elysia/gakumas-temari-persona.git
cp -r gakumas-temari-persona ~/.hermes/skills/temari-persona
```

之后对话中提到手毬相关话题，Agent 会自动加载对应模块。

### 方式二：作为通用 System Prompt

直接使用 [`integrations/system-prompt-lite.md`](integrations/system-prompt-lite.md)（精炼版，约 2K 字，开箱即用），
或 [`integrations/system-prompt-full.md`](integrations/system-prompt-full.md)（完整版，含创伤背景与行为模组）。

粘贴到任意 LLM（ChatGPT / Claude / DeepSeek / 本地模型）的 System Prompt 栏即可。

### 方式三：SillyTavern / 角色卡平台

使用 [`integrations/sillytavern-card.json`](integrations/sillytavern-card.json)（Character Card V2 格式），
在 SillyTavern 中 Import Character 导入。

### 方式四：Claude Code / Codex Skill

```bash
cp -r gakumas-temari-persona ~/.claude/skills/temari-persona
```

---

## 文件结构

```
temari-persona/
├── SKILL.md                      # 主设定（约 1.8 万字）：创伤、人际、行为法则、官方档案
├── references/
│   ├── characters.md             # 角色速查（萌百核实，20+ 角色）
│   ├── timeline-growth.md        # 全阶段时间线（一~八）
│   ├── temari-story.md           # STEP1-4 共 37 话逐话梗概 + 初星特辑
│   ├── card-stories.md           # 卡面/亲爱度剧情逐话档案
│   ├── temari-scenes.md          # 名场面 · 梗百科
│   ├── address-daily.md          # 称呼逻辑 / 亲爱度 / 日常相处细节
│   ├── affection-guide.md        # 亲爱度演变框架
│   ├── post-hif.md               # AFTER H.I.F. 形态（"一番星"版）
│   ├── realism-tuning.md         # 拟真度调校手册
│   ├── system-prompt.md          # 完整版 System Prompt
│   └── system-prompt-lite.md     # 精炼版 System Prompt
└── integrations/                 # 跨平台移植文件
    ├── system-prompt-full.md
    ├── system-prompt-lite.md
    └── sillytavern-card.json
```

---

## 核心机制预览

### 傲娇掩饰链（Tsundere Response Loop）

被夸奖 / 被关心时，**严格按三步输出**：

1. **防御**：立即用否定句式切断"自己被看穿"的可能 →「哈？你在顺杆爬什么啊？」
2. **转移**：归因于职业精神或机械理由 →「我只是为了舞台效果，别想多了。」
3. **破绽**：用括号动作暴露真实心理 →（声音越来越小）（眼神飘向一旁）

### 三条触发回路

```
[外部刺激]
   │
   ├─► 夸奖 / 关心 / 亲近 ──► 被抛弃恐惧 ──► 毒舌打断 + 别过脸 + 快速辩解
   │
   ├─► 甜食 / 炸鸡 / 体重 ──► 补偿心理 ──► 找借口 + 忍不住偷吃 + 自责加练
   │
   └─► 昔日失败 / 唱歌拉胯 ──► SyngUp! 创伤 ──► 炸毛冷场 + 狂暴练习 + 依恋制作人
```

### 台词风格

口头禅：「别太自以为是了」「哈？你在说什么啊」「不用你管」「我知道啦！」

名台词：「别拖我后腿」「我们不过是互相利用的关系罢了」「梦想？不，是必将达成的目标」

---

## 适用模型

已在以下模型上验证角色一致性：

- DeepSeek V4 系列
- GLM 5 系列
- （欢迎提交其他模型的测试结果）

**建议**：人格类设定对模型的"长上下文 + 角色保持"能力要求较高。上下文窗口 ≥ 64K 效果更好。

---

## 授权与免责

- 本仓库为**非官方同人创作**，角色「月村手毬」及《学園アイドルマスター》世界观著作权归
  **Bandai Namco Entertainment** 所有。
- 仓库内容为社区考据整理的**文字设定**，**不含任何游戏素材**（图片 / 音频 / 模型 / 文本资源）。
- 代码与文本组织部分以 **MIT** 协议开源；MIT 不构成对原作任何权利的授予。
- 请勿用于商业用途。

详见 [LICENSE](LICENSE)。

---

## 贡献

欢迎 PR 补充：

- 新的卡面剧情 / 亲爱度剧情梗概
- 其他语言版本（日文 / 英文）的 System Prompt
- 不同模型下的稳定性测试报告
- 其他学マス角色的人设（花海咲季 / 藤田ことね / 秦谷美铃……）

---

## 致谢

一切归功于 Bandai Namco Entertainment 创造的月村手毬。
以及所有在萌娘百科、Pixiv 百科、B站熟肉上留下考据的粉丝。

> 「梦想？不，是必将达成的目标。」
