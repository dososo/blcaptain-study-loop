# 能设计一个可验收的 Rust CLI 契约

## 已掌握

学习者能把“学 Rust”落到团队内部 CLI 的用户、命令、输入、输出、失败场景和验收标准上。

## 证据等级

E2 应用。

## 证据

已完成一个可检查的命令契约草案:

```text
bltool process <input-path> --out <output-path> --format json
bltool check <input-path> --strict
bltool explain <error-code>
```

最小验收:

- `process` 能处理一个正常输入并输出 JSON。
- `check` 能在不写文件的情况下报告问题。
- `explain` 能把错误码翻译成团队成员看得懂的修复建议。
- `--help` 中每个参数都有一句人话说明和一个例子。

## 为什么这算 E2

这不是“看过 clap 教程”，而是已经把团队场景转成可实现、可讨论、可验收的命令接口。下一轮可以直接写代码验证。

## 下一步影响

- 课程难度从概念理解进入项目薄片。
- 后续学习优先级变成 `clap`、文件 I/O、`Result`、错误输出和 CLI smoke test。
