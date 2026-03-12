# prompt-coach-cn

一个中文优先的 Codex 提示词设计 skill。

它不是“提示词模板合集”，而是一个会先理解任务、再优化需求、最后生成更合适 prompt 或成品的前置建模层。

---

## 它解决什么问题

很多提示词不好，不是因为句子写得不够花，而是因为：

- 任务类型一开始就判断错了
- 用户给的输入角色没分清
- 真正要优化的目标没定准
- 还没想清中间结构，就急着下笔
- 该写成故事、分析、引导式追问还是世界观样章，没有先选对

`prompt-coach-cn` 的核心，就是先把这些底层问题处理好，再决定怎么写。

---

## 它和普通提示词 skill 的区别

它默认不是“看到需求就立刻给一个第一版 prompt”，而是会先在内部做一轮隐藏建模：

1. 判任务类型
2. 判输入角色
3. 选目标函数
4. 抽中间表示层
5. 选成品单位和最终结构

然后再通过这些机制提质量：

- complexity gate
- taste memory
- decision cache
- hidden local candidate synthesis
- early stop

也就是说，它更像一个**提示词建模器**，而不是一个只会拼装模板的提示词写手。

---

## 当前能力

### 提示词相关

- 写提示词
- 优化提示词
- 压缩提示词
- 重构提示词
- 修稳结构化输出
- few-shot / 结构化中文改写

### 任务判断相关

- `summary` vs `insight`
- `topic prompt` vs `engine prompt`
- `source-constrained translation` vs `theme expansion`
- `guided inquiry` vs `direct explanation`
- `symbolic-world entry` vs `symbolic-world analysis`

### 成品单位判断

- analytical explainer
- character-driven short story
- scene-based slice essay
- case-driven article
- guided inquiry flow
- interactive symbolic transcript
- embodied mental-world simulation
- reusable generator / engine

### 进阶机制

- 主题原生化成形，避免所有 prompt 长得都一样
- 隐藏多候选比较，但默认只输出最终一版
- 记住稳定偏好，但允许当前要求覆盖旧偏好
- 用 decision cache 复用已经验证有效的决策
- 用 complexity gate 避免每次都跑重流程

---

## 它适合什么场景

你不知道怎么问 AI 时：

- “帮我写一个提示词”
- “把这个需求变成 prompt”
- “这个 prompt 为什么老不稳定”
- “不要直接给答案，带我一步步找到本质”
- “这个主题写出来总像模板，帮我做得更贴主题”

你直接要成品，但又希望它先帮你把需求理顺时：

- “以如果情绪有实体颜色为主题，写一篇故事”
- “如果你能通过 AI 看清事物的本质，写一篇文章”
- “帮我做一个能进入精神世界的角色扮演 prompt”

---

## 它背后的设计原则

这个 skill 不是从一两条 prompt 逆向拼出来的，而是从一批中文案例里抽出来的方法论。

它真正学的不是“某个 prompt 长什么样”，而是：

- 为什么这个任务要分阶段
- 为什么这个输入是证据，不只是灵感
- 为什么这个案例更像引擎，而不是成品
- 为什么有的任务要解释，有的任务要引导，有的任务要进入世界
- 为什么第一版经常只是能用，不是最强版

一句话说：

> 好 prompt 不是“写得复杂”，而是“建模正确”。

---

## 当前版本

- skill version: `0.3.5`
- eval count: `50`

这一版重点补了：

- complexity gate
- decision cache
- hidden local candidate synthesis
- 低维偏好画像
- 更强的 theme-native shaping

---

## 仓库结构

- [SKILL.md](./SKILL.md)
- [evals/evals.json](./evals/evals.json)
- [references/checklists.md](./references/checklists.md)
- [references/decision-cache.md](./references/decision-cache.md)
- [references/patterns.md](./references/patterns.md)
- [references/source-notes.md](./references/source-notes.md)
- [references/user-taste-profile.md](./references/user-taste-profile.md)

---

## 使用方式

如果你在 Codex 里安装它，常见用法有两种：

### 1. 显式要 prompt

- “帮我写一个提示词”
- “优化这个 prompt”
- “把这个需求变成稳定 prompt”

### 2. 直接要结果

你不需要先学会怎么提问。

你可以直接说：

- “写一篇故事”
- “写一篇文章”
- “设计一个角色扮演”
- “帮我做一个世界观设定”

它会先在内部优化需求，再直接给你结果。

---

## 设计目标

最终目标不是让它“会几个案例”，而是让它：

- 遇到新主题也能判断对
- 越用越懂当前用户的偏好
- 该认真时认真，该停时会停
- 少一点模板味，多一点主题自己的样子

如果你想要的是一个越来越像“你的版本”的提示词 skill，这个仓库就是沿着这个方向做的。
