---
share: true
---
# Git提交规范

## 规范提交信息

### 提交模板

Commit message 应该包含使用空行隔开的三个部分: Header(必须)，Body(可选) 和 Footer(可选)。

```text
<type>(<scope>): <subject>
// 空一行
<body>
// 空一行
<footer>
```

一般每行不应该超过72个字符

#### type

`type`(必须), 用于说明 commit 的类别，只允许使用下面7个标识。

* feat: 一个新的 feature
* fix: 一个 Bug fix
* docs: 文档层面的更改
* style: 代码格式的调整，比如缺失的符号之类的，不存在代码逻辑上的变更
* refactor: 重构
* perf :性能优化
* test: 添加测试、重构测试，无应用代码修改
* ci: 添加或更新CI配置和脚本
* build: 构建过程更改或更新依赖
* chore: 构建过程或辅助工具的变动
* revert: 撤销上一次的 commit

#### scope

`scope`(可选), 用于说明 commit 影响的范围，比如数据层、控制层、视图层等等，视项目不同而不同。

#### subject

`subject`(必须), 是 commit 目的的简短描述，不超过50个字符。

* 以动词开头，使用第一人称现在时，比如change，而不是changed或changes
* 第一个字母大写
* 结尾不加句号

#### body

body(可选), 是对本次 commit 的详细描述，可以分成多行。由于 Commit 的复杂程度不同，因此不要求每个 Commit 都写内容。主体内需要说明 **What (是什么）** 和 **Why (为什么)**，以确保阅读你的 Commit 的人能够明了前因后果。

编写正文时，需要注意标题和正文之间的空行，并限制每一行的长度不超过 72 个字符。下面是一个范例。

```text
More detailed explanatory text, if necessary.  Wrap it to 
about 72 characters or so.

Further paragraphs come after blank lines.

- Bullet points are okay, too
- Use a hanging indent
```

有两个注意点。

1. 使用第一人称现在时，比如使用change而不是changed或changes
2. 应该说明代码变动的动机，以及与以前行为的对比

#### footer

footer 部分只用于两种情况。

1. 不兼容变动
   如果当前代码与上一个版本不兼容，则 Footer 部分以BREAKING CHANGE开头，后面是对变动的描述、以及变动理由和迁移方法。

    ```text
    BREAKING CHANGE: isolate scope bindings definition has changed.

    To migrate the code follow the example below:

    Before:

    scope: {
      myAttr: 'attribute',
    }

    After:

    scope: {
      myAttr: '@',
    }

    The removed `inject` wasn't generaly useful for directives so there should be no code using it.
    ```

2. 关闭 Issue
   如果当前 commit 针对某个issue，那么可以在 Footer 部分关闭这个 issue, 多个用逗号分隔

    ```text
    Closes #123, #245, #992
    ```

