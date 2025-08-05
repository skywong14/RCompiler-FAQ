## RCompiler FAQ
### How to Ask Questions

You can contribute or ask questions in the following ways:

1. **Issues:** If you have any question, feel free to open a new issue.
2. **Pull Requests (PRs):** If you find an error in the documentation or want to add new content, we welcome you to submit a pull request.


### Frequently Asked Questions (FAQ)

We will update this README with answers to common questions.

#### Undefined Behavior (UB) and Simplifications

**The following actions are classified as Undefined Behavior (UB) or are design simplifications for this course:**

- 超过 $1M$ 的源代码。
- 包含任何扩展ASCII字符或多字节Unicode字符 (码点大于 $127$ 的所有字符)的源代码。
- 会引发 `Panic` 的所有代码（如数组的越界访问、整型变量除以 $0$）。
- 使用未初始化的变量。
- 违反所有权的操作。
- 所有语法宏（Syntactic Macros）。
- 大部分语法糖（`?` 运算符、`Closures`、`Turbofish` 、`for loop (Iterator loops，包括 Loop labels)`等）。
- 所有 `unsafe` 的操作（如 `Raw Borrow operators`）。
- 会引发生命周期错误的所有代码（如悬垂引用），和与生命周期的特性相关的语法（如生命周期注解），我们不要求任何生命周期检查。
- 我们对 `Identifiers` 做如下简化：标识符的第一个字符必须为英语字母，第二个字符开始可以是英语字母、数字或者下划线。标识符区分大小写并且长度超过 $64$ 个字符的标识符是未定义的。
- 我们对 `float literals` 做如下简化：不要求 `FLOAT_EXPONENT` 的实现。
- 我们对 `Comments` 做如下简化：只需要考虑 C++ 风格的两种非文档注释（Non-doc comments）。

*以上部分内容与 Spec 仓库的要求冲突，冲突部分请以此文档为准，我们会逐步删减和更新 Spec 仓库。*

**The following behaviors are not UB, but instead have well-defined specifications:**

- 表达式的各个操作数的求值顺序（对于需要多个操作数的表达式，其求值顺序依照源代码从左至右依次进行；对于复合赋值表达式，文档中也有明确的说明）
