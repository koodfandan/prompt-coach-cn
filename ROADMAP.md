# ROADMAP

`prompt-coach-cn` 的目标不是变成一个提示词模板仓库，而是逐步进化成一个：

- 更会判断任务本质
- 更会做隐藏优化
- 更懂当前用户偏好
- 该快时快、该深时深

的中文提示词建模 skill。

---

## 当前阶段：v0.3.x

这一阶段已经完成的重点：

- 默认前置需求优化
- task family / artifact unit 双层判断
- theme-native shaping
- hidden synthesis
- taste memory
- decision cache
- complexity gate

当前已经解决的问题：

- 提示词太模板化
- 第一版就交，质量不够高
- 不同主题 prompt 长得太像
- 只会做 prompt，不会先理解需求
- 明明用户要成品，却没先做隐藏 prompt 建模

---

## 下一阶段：v0.4.x

目标：让 skill 从“会判断”进一步变成“更会分配计算成本”。

重点方向：

### 1. 更稳的 early-stop

不是只写了规则，而是真正更明确地判断：

- 什么情况下当前版本已经足够好
- 什么情况下继续发散只是在浪费成本

### 2. 更细的局部合成策略

把当前的 hidden synthesis 继续从：

- 整版候选比较

往：

- 局部组件比较
- 局部重组

继续压缩。

目标是进一步减少：

- token 消耗
- 延迟
- 无效重复搜索

### 3. 更低维的偏好更新机制

当前已经有 compact taste profile。
下一步希望它能更自动地区分：

- 稳定偏好
- 一次性偏好
- 当前任务内偏好

避免记忆越来越重，最后反而限制输出范围。

### 4. 更好的失败模式优先修复

不是每次都平均优化所有维度，而是先判断：

- 这次最可能失败在哪

再优先修那一层。

---

## 中期阶段：v0.5.x

目标：让 skill 具备更强的“发现式设计”能力。

重点方向：

### 1. 更强的 guided inquiry / essence extraction

让“本质挖掘型”任务更稳，不只是会追问，还能：

- 控制抽象层级
- 防止过早下结论
- 区分单因与多因
- 在开放探索和收束判断之间保持平衡

### 2. 更成熟的 symbolic-world roleplay

让“进入一个象征世界”这类任务更系统化：

- container
- state switch
- trigger map
- reveal ladder
- anti-dead-end mechanic

进一步从案例学习，沉淀成更稳定的机制。

### 3. 更精确的 artifact-unit library

现在已经有成品单位判断。
下一步希望把同一任务家族内部的差异继续拉开，例如：

- worldbuilding sample
- character-driven short story
- case-driven article
- reflective monologue
- staged interrogation transcript

让结果不只是“分大类正确”，而是“最后成品单位也更准”。

---

## 长期方向

长期目标不是“提示词写得更花”，而是：

### 1. 变成真正的 prompt modeling layer

也就是未来用户即使不会提问，也能直接说需求，而 skill 在内部完成：

- 分类
- 建模
- 隐藏比较
- 个性化收敛

### 2. 变成真正的 personalized prompt system

不是机械记住用户喜欢什么，而是越来越知道：

- 这个用户讨厌什么
- 这个用户认为什么算“对味”
- 什么样的 prompt/成品会被认为“终于像他自己的版本”

### 3. 变成更经济的决策系统

未来理想状态是：

- 不为简单任务过度推理
- 不为复杂任务偷工减料
- 通过 memory + cache + routing，让每次 hidden work 都更值钱

---

## 不会做的方向

这个 skill 不打算走这些路：

- 变成模板大全
- 变成固定文风生成器
- 为了显得复杂而过度伪代码化
- 用越来越多规则替代真正的任务建模
- 把 personalization 做成风格锁死

---

## 一句话版本

`prompt-coach-cn` 接下来最重要的方向不是“更会写”，而是：

**更会判断、比较、收敛，并且越来越像当前用户真正想要的那个版本。**
