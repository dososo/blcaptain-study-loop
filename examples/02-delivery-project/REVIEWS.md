# 学习复盘

## 阶段 1: 从 skill 想法到输出契约

### 现在已经能做什么

- 能把“图片转视频分镜提示词”拆成清晰的 prompt pack 输出结构。
- 能区分图片事实、创作推断、镜头设计、负面约束和模型适配。
- 能定义 skill 的第一轮可用标准，而不是直接追求完整视频生成链路。

### 证据

- `LEARNING-BRIEF.md` 明确了一天内 MVP 的产物和边界。
- `lessons/0001-skill-minimum-delivery.html` 说明最小可交付 skill 的四个判断点。
- `cards/0001-skill-delivery-card.html` 形成 skill 交付检查卡。
- `progress/0001-skill-delivery-e2.md` 记录 E2 证据。

### 卡住的地方

- 还没有真实图片输入，只能使用模拟图片描述。
- 不同视频模型对运动、时长和负面提示词支持不同。
- 创作者对“好用提示词”的标准还需要真实反馈。

## 阶段 2: Forward test 和质量门禁

### 现在已经能做什么

- 能用一张模拟图片描述生成结构化 prompt pack。
- 能用质量门禁检查事实幻觉、镜头连续性、提示词可执行性和模型适配风险。
- 能判断下一轮应补真实图片测试，而不是继续扩展理论。

### 证据

- `lessons/0002-forward-test-quality-gate.html` 展示 forward test 的检查方式。
- `cards/0002-storyboard-prompt-quality-gate.html` 将质量门禁压缩为长期可复用卡片。
- `progress/0002-forward-test-e2.md` 记录通过质量门禁的 E2 证据。

### 下一步最小动作

1. 用一张真实产品图或人物图做 forward test。
2. 补一个模型适配小节: 通用 prompt、Runway、Kling、Pika 或其他目标模型。
3. 请一个创作者判断 prompt pack 是否能直接复制使用。

### 资料和节奏调整

- 不先做大而全视频模型百科。
- 先把输出质量门禁稳定下来，再扩展模型参数。
