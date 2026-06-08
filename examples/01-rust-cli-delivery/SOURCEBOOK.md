# Rust CLI 学习资料清单

## S1 一手来源

- The Rust Programming Language  
  链接: https://doc.rust-lang.org/book/  
  用途: 理解 Rust 基础、错误处理、模块、测试和一个小型 I/O 项目如何组织。  
  可信原因: Rust 官方书。  
  新鲜度: 发布前检查链接。  
  访问性: 可直接访问。

- Rust By Example  
  链接: https://doc.rust-lang.org/rust-by-example/  
  用途: 快速查 `Result`、`Option`、文件 I/O、迭代器和错误传播的最小例子。  
  可信原因: Rust 官方示例集。  
  新鲜度: 发布前检查链接。  
  访问性: 可直接访问。

- Cargo Book  
  链接: https://doc.rust-lang.org/cargo/  
  用途: 确认项目结构、依赖管理、测试和发布二进制的基本流程。  
  可信原因: Cargo 官方文档。  
  新鲜度: 发布前检查链接。  
  访问性: 可直接访问。

- clap documentation  
  链接: https://docs.rs/clap/latest/clap/  
  用途: 设计 CLI 参数、子命令、帮助文案和 derive API。  
  可信原因: crate 文档和 API 参考。  
  新鲜度: 发布前检查链接。  
  访问性: 可直接访问。

## S2 专家资料

- Command Line Applications in Rust  
  链接: https://rust-cli.github.io/book/  
  用途: 学习 CLI 的项目组织、错误输出、测试和用户体验细节。  
  可信原因: Rust CLI 领域常用实践手册。  
  新鲜度: 发布前检查链接。  
  访问性: 可直接访问。

## S3 团队上下文

- 团队现有手工流程  
  用途: 定义 CLI 的真实输入、输出、命令命名和验收标准。  
  可信原因: 直接来自目标用户的工作流。  
  风险: 示例中使用模拟流程，真实项目需替换为团队自己的任务。

- 团队机器环境  
  用途: 判断二进制分发、shell、路径、权限和网络限制。  
  可信原因: 直接影响工具是否能被使用。  
  风险: 不同系统可能需要不同安装方式。

## 资料使用策略

- 第一周只读完成 thin slice 所需内容，不系统学习整本书。
- 一切 Rust 语法学习都服务于 CLI 交付: 参数解析、文件 I/O、错误处理、测试。
- 如果官方资料和社区例子冲突，优先官方资料；社区例子只用于理解实践。
- 涉及 crate 版本时，以项目 `Cargo.toml` 锁定版本为准，不在学习记录里写死“最新版”。

## 仍需补充

- 真实团队任务的输入样例。
- 真实输出格式的消费者是谁。
- 团队能接受的安装方式: cargo install、本地二进制、还是内部脚本封装。
