---
title: 代码高亮与演示 (Expressive Code)
published: 2024-04-10
description: 了解如何在 Markdown 中使用非常漂亮的代码块。
tags: [Markdown, 博客, 演示]
category: 示例
draft: false
---

在这里，我们将展示如何使用强大的 [Expressive Code](https://expressive-code.com/) 来渲染非常漂亮的代码块。以下是一些示例，告诉你怎样把代码展示得更清晰、更酷炫。

## Expressive Code 功能一览

### 1. 基础语法高亮

[语法高亮说明](https://expressive-code.com/key-features/syntax-highlighting/)

#### 普通的语法高亮

```js
console.log('这段代码有漂亮的语法高亮！')
```

#### 甚至可以渲染终端的彩色输出 (ANSI)

```ansi
ANSI 颜色支持:
- 常规: [31m红色[0m [32m绿色[0m [33m黄色[0m [34m蓝色[0m [35m洋红色[0m [36m青色[0m
- 加粗:    [1;31m红色[0m [1;32m绿色[0m [1;33m黄色[0m [1;34m蓝色[0m [1;35m洋红色[0m [1;36m青色[0m
- 暗色:  [2;31m红色[0m [2;32m绿色[0m [2;33m黄色[0m [2;34m蓝色[0m [2;35m洋红色[0m [2;36m青色[0m

256 色 (展示 160-177):
[38;5;160m160 [38;5;161m161 [38;5;162m162 [38;5;163m163 [38;5;164m164 [38;5;165m165[0m
[38;5;166m166 [38;5;167m167 [38;5;168m168 [38;5;169m169 [38;5;170m170 [38;5;171m171[0m
[38;5;172m172 [38;5;173m173 [38;5;174m174 [38;5;175m175 [38;5;176m176 [38;5;177m177[0m

完整的 RGB 颜色:
[38;2;34;139;34m森林绿 - RGB(34, 139, 34)[0m

文本格式: [1m加粗[0m [2m暗色[0m [3m斜体[0m [4m下划线[0m
```

### 2. 编辑器与终端边框风格

你可以让代码看起来像是在真正的代码编辑器或者终端里运行的一样。

#### 编辑器风格边框

```js title="我的测试文件.js"
console.log('这是一个带有文件标题的例子')
```

---

只要在代码第一行加上特定格式的注释，也可以自动识别文件名：

```html
<!-- src/content/index.html -->
<div>这里是通过注释识别文件名的例子</div>
```

#### 终端风格边框

如果你把代码标记为 `bash` 或者 `sh`，它会自动带上终端的边框：

```bash
echo "这是一个没有标题的终端框"
```

---

```powershell title="PowerShell 终端示例"
Write-Output "这个终端框有标题！"
```

### 3. 高亮特定的代码行

如果你想强调某一行或某段代码，可以像下面这样：

#### 标记整行或多行

```js {1, 4, 7-8}
// 第 1 行 - 被行号标记选中了
// 第 2 行
// 第 3 行
// 第 4 行 - 被行号标记选中了
// 第 5 行
// 第 6 行
// 第 7 行 - 通过 "7-8" 的范围被选中
// 第 8 行 - 通过 "7-8" 的范围被选中
```

#### 添加 "新增" 或 "删除" 标记 (绿色的 ins 和 红色的 del)

```js title="line-markers.js" del={2} ins={3-4} {6}
function demo() {
  console.log('这一行被标记为已删除 (红色)')
  // 这一行和下一行被标记为已新增 (绿色)
  console.log('这是第二行新增的代码')

  return '这一行使用的是默认的普通高亮标记 (中性颜色)'
}
```

#### 在代码行旁边添加标签

```jsx {"1":5} del={"2":7-8} ins={"3":10-12}
// 这是一个带有数字标签的高亮示例
<button
  role="button"
  {...props}
  value={value}
  className={buttonClassName}
  disabled={disabled}
  active={active}
>
  {children &&
    !active &&
    (typeof children === 'string' ? <span>{children}</span> : children)}
</button>
```

#### 标记代码中的特定单词或短语

```js "指定的文字"
function demo() {
  // 你可以高亮代码行里的任何单词
  return '所有匹配的“指定的文字”都会被高亮显示';
}
```

#### 结合 Diff 语法

```diff lang="js"
  function thisIsJavaScript() {
    // 整个代码块都按 JavaScript 语法高亮
    // 同时你还能像写 Git Diff 一样加加减减！
-   console.log('这里是将被删除的旧代码')
+   console.log('这里是闪闪发亮的新代码！')
  }
```

### 4. 代码折叠与展开

你可以把一些不那么重要的、很长的前置代码给折叠起来，让读者一目了然。

```js collapse={1-5, 12-14, 21-24}
// 所有的这些初始化代码都会默认被折叠起来！
import { someBoilerplateEngine } from '@example/some-boilerplate'
import { evenMoreBoilerplate } from '@example/even-more-boilerplate'

const engine = someBoilerplateEngine(evenMoreBoilerplate())

// 这部分核心代码默认是可见的
engine.doSomething(1, 2, 3, calcFn)

function calcFn() {
  // 你可以在一个代码块里折叠多个不同的区域
  const a = 1
  const b = 2
  const c = a + b

  // 这里会保持可见
  console.log(`计算结果: ${a} + ${b} = ${c}`)
  return c
}

// 直到结尾的这些清理代码也会再次被折叠
engine.closeConnection()
engine.freeMemory()
engine.shutdown({ reason: '示例结束' })
```

### 5. 显示行号

你可以通过 `showLineNumbers` 来强制显示代码行号：

```js showLineNumbers
// 这个代码块会显示行号
console.log('来自第 2 行的问候！')
console.log('我在第 3 行')
```