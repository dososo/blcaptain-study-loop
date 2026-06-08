# 学习复盘

## 阶段 1: 从“学 Rust”改成“交付 CLI”

### 现在已经能做什么

- 能把模糊目标“学 Rust”改写成两周内可验收的 CLI 交付目标。
- 能定义 CLI 的用户、输入、输出、错误场景和验收方式。
- 能识别第一轮学习不应该从所有权理论开始，而应该从命令契约和 thin slice 开始。

### 证据

- `LEARNING-BRIEF.md` 已写清真实期限、交付物、边界和证据门槛。
- `lessons/0001-rust-cli-contract.html` 产出 CLI 契约练习。
- `cards/0001-rust-cli-contract-card.html` 将命令接口设计压缩为可复用检查卡。
- `progress/0001-rust-cli-contract-e2.md` 记录了可观察练习结果。

### 卡住的地方

- 还没有真实团队输入样例，当前只能用模拟任务设计命令。
- 还没有确认团队使用 macOS、Linux 还是混合环境。
- 还没进入 Rust 所有权难点，后续文件处理时会遇到。

### 下一步最小动作

1. 找到 3 个真实输入样例和 2 个失败样例。
2. 用 `clap` 写出 `--help`，让一个团队成员只看帮助文案判断是否会用。
3. 做一个最小 `process` 命令，先返回结构化假数据。

## 阶段 2: 错误处理和内部发布

### 现在已经能做什么

- 能把 Rust `Result` 学习绑定到 CLI 用户体验，而不是停留在语法解释。
- 能把 panic、错误码、stderr 和可读修复建议分开处理。
- 能用发布检查卡判断一个内部 CLI 是否真的适合给同事试用。

### 证据

- `lessons/0002-error-handling-release.html` 提供 4 类失败场景练习。
- `cards/0002-team-cli-release-checklist.html` 覆盖安装、帮助文案、错误提示、样例和验收。
- `progress/0002-error-handling-release-e2.md` 记录了错误处理和发布验收的 E2 证据。

### 下一步最小动作

- 将模拟命令替换为真实目录扫描或文件转换逻辑。
- 增加 `tests/cli_smoke.rs`，覆盖帮助文案、成功路径和 2 个失败路径。
- 请团队里最不熟悉 Rust 的同事试跑 README。

### 资料和节奏调整

- 暂不学习宏、生命周期高级内容和异步。
- 第二周只补交付需要的 Rust 知识: 结构体、错误枚举、测试、路径处理和分发。
