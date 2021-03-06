---
title: Vim 初级入门
date: 2016-07-23 19:04:11
tags: [vim]
---

## 前言

没有接触过Vim的同学, 一定会觉得平时使用的IDE很好用, 但是当你开始使用Vim, 并且渐渐熟悉, 我觉得你会爱上这一款编辑器.
千万不要因为一开始Vim有太多命令需要记忆而放弃它. 
  
这篇博客是翻译自《[Learn Vim Progressively](http://yannesposito.com/Scratch/en/blog/Learn-Vim-Progressively/)》, 并在我觉得有必要添加说明的地方添加了自己的说明. 我认为是最适合入门Vim的教程, 没有之一.

---

## 正文开始

你想以最快的方式自学Vim吗? 在人类最优秀的编辑器面前, 你必须至少先学会如何幸存下来, 然后再去一点点整合使用它的技巧.

[Vim](http://www.vim.org/) the Six Billion Dollar editor

> Better, Stronger, Faster

当你学会使用Vim, 它将成为你最后一个编辑器. 虽然学习它的过程很不容易, 但是最后它会难以置信的好用.

<!--more-->

下面4个步骤是你自学的感受:

1. 存活
2. 使用顺手
3. 更好, 更强, 更快
4. 使用Vim的超能力

当你读完这篇文章, 你将会爱上vim.

但是我们开始之前, 要先说明一点: 

* 学习vim的过程将是十分痛苦的
* 将花费一些时间, 千万不要觉得浪费时间儿放弃
* 学习他的过程就像是学习乐器, 一旦入门, 就会变得很轻松
* 不要奢望像其他编辑器一样三天之内就能熟练掌握, 学习vim至少需要两个星期而不是三天


### Level 1 - 存活

0. 安装vim
1. 运行vim
2. **不要做任何事情!** 请先阅读

在普通编辑器中, 当你敲击键盘就能在屏幕上看到想要的字符. 但是对于Vim来讲, 不是这样的. 当你启动vim的时候, vim当前正在 *`Normal`* 模式下, 你需要先将模式切换为 *`Insert`* 模式, 才能够输入字符. 从 *`Normal`* 模式到 *`Insert`* 模式, 需要敲击键盘字符 `i`.

当你进入*`Insert`*模式, 你可能会感觉舒服一点, 因为你可以像普通编辑器一样输入字符了. 如果你想从*`Insert`*模式切换回*`Normal`*模式, 只需要敲击键盘最左上角的键`ESC`键.

现在你知道如何在*`Insert`*模式和*`Normal`*模式之间切换了. 现在, 你必须要掌握下面几个命令以保证你能在*`Normal`*模式下存活下去:

> - `i`   : 切换到*`Insert`*模式. 按`ESC`返回*`Normal`*模式
> - `x`   : 删除当前光标所在的一个字符
> - `:wq` : 保存并退出 (`:w` 保存编辑的文件, `:q` 退出vim)
> - `dd`  : 删除光标所在的一行
> - `p`   : 粘贴

> #####推荐

> - `hjkl` (强烈推荐但不强制使用): 你可以使用键盘的 ↑ ↓ ← → 进行光标的移动. **提示:** 在*`Normal`*模式下, `j`代表方向 ↓
> - `:help <command>` : 显示 `<command>` 的帮助文档. 你可以直接输入 `:help` 而不输入 `<command>` 获取一般性帮助.

最开始, 你只需要上面5个命令. 当你很自然地使用以上命令, 抛弃之前普通编辑器的习惯, 那么你就可以到**Level 2**了.

但是, 在*`Normal`*模式下需要注意的是: 在普通编辑器下, `Ctrl-C`是复制命令, 这是个组合按键来完成一项复制的功能, 但是在vim下, 不可以轻易地使用`Ctrl`. 事实上, 在Vim的 *`Normal`* 模式下, vim已经赋予每一个按键功能, 也就是说, 在*`Normal`*模式下, 每一个键都是功能键, 而不需要你按下`Ctrl`去组合其他按键实现某项功能.

**提示**

- 为了便于书写和阅读, 下面的文章中, `<C-λ>` 将代表键入 `Ctrl-λ`
- 命令都是以`:`开头, 并且最后要键入`<enter>`. 如: 当我写`:q`, 将代表`:q<enter>`

### Level 2 - 感觉顺手

你现在已经可以在vim中存活了. 现在是时候学点其他的命令了. 下面是我的建议(以下命令都是在*`Normal`*模式下键入):

1. 各种插入模式

> - `a`  : 在当前光标后开始插入, 并且进入*`Insert`*模式
> - `o`  : 从当前行下面插入新行, 并且进入*`Insert`*模式
> - `O`  : 从当前行上面插入新行, 并且进入*`Insert`*模式
> - `cw` : 删除光标开始的单词, 并且进入*`Insert`*模式

2. 基本的移动

> - `0`  : 到光标所在行的最开始
> - `^`  : 到光标所在行第一个非空字符
> - `$`  : 到光标所在行的末尾
> - `g_` : 到光标所在行最后一个非空字符
> - `/pattern` : 向下搜索字符串`pattern`
> - `?pattern` : 向上搜索字符串`pattern`
> 
> **注**: 搜索时, 键入`n`键可以查看下一项, 键入`N`键可以查看上一项

3. 复制/粘贴

> - `p` : 在当前光标后粘贴
> - `P` : 在当前光标前粘贴
> - `yy`: 复制光标所在整行

4. 撤销/恢复 (Undo/Redo)

> - `u` : 撤销
> - `<C-r>` : 恢复

5. 载入/保存/退出/修改文件(Buffer)

> `:e <path/to/file>` : 打开文件
> `:w` : 保存文件修改
> `:saveas <path/to/file>` : 另存为`<path/to/file>`
> `:x`, `ZZ` or `:wq` : 保存并退出. `:wq`相当于先`:w`再`:q`; `:x`只在需要时保存; `ZZ`不需要输入`:`和回车`<enter>`
> `:q!` : 强制退出而不保存修改. `:qa!`, 强制退出所有正在编辑的文件, 即使其他文件有做过修改而没有保存
> `:bn`和`:bp` : 切换到下/上一个文件

花一点时间去熟悉上面的命令. 当你熟练掌握之后, 你可以完成你在普通编辑器几乎所有功能. 你可能会觉得用vim还是有点别扭. 但是跟着我进入下一Level, 或许你可以明白为什么要花费这么多力气去学习它.

### Level 3 - 更好. 更强. 更快.

恭喜你已经到达了Level 3! 我们现在开始学习一些有趣的东西. 在Level 3, 我们只讨论和vi编辑器兼容的那些命令.

#### 3.1 更好

让我们看看vim是怎么样帮助你做重复的命令的:

1. `.`(点) : 重复上一次的命令
2. `N<command>`: 将会运行`<command>`N次, 这里的N是一个整数

下面是一个例子. 打开一个文件然后输入下面的命令:

> - `2dd` : 将会删除2行
> - `3p`  : 将会执行粘贴命令3次
> - `100idesu [ESC]` : 将会输入 "desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu desu"
> - `.`   : 跟在上一个命令后面代表再次输入100次"desu"
> - `3.`  : 将会输入3次"desu"(而不是300次, 你看vim多么聪明)

#### 3.2 更强

知道如何高效的在vim中移动光标十分重要. 不要跳过这一部分.

1. N`G` : 移动光标到第N行
2. `gg` : 相当于 `1G`, 到文件的最开始一行
3. `G`  : 到文件的最后一行
4. 按照单词移动:
> 1. `w` : 到下一个单词的开始
> 2. `e` : 到下一个单词的结尾
> 默认情况下, 我们认为单词是由一系列字符和下划线组成. 如果你认为由空格分隔开的字符串即为单词, 那么你只需要使用`W`和`E`.

> ![单词移动](http://p3.qhimg.com/t01ba88a3a55faa8746.jpg)


现在介绍更高效的移动方式:

> - `%` : 匹配括号移动光标, 如`()`,`[]`,`{}`
> - `*`和`#` : 匹配光标当前所在单词, 并且向下/上查找匹配的单词, 并把光标移到查找到的单词

相信我, 最后的三个命令是十分高效的.

#### 3.3 更快

记住如何移动光标了吗, 因为很多命令都是可以组合使用的. 并且大多是以以下格式:

`<start position><command><end position>`

例如: `0y$` 意思是

- `0` : 将光标移动到行首
- `y` : 开始复制
- `$` : 复制到行尾

我们也可以使用`ye`, 从光标所在位置复制到单词结束.
也可以使用`y2/foo`, 从光标所在位置复制到匹配的第二个`foo`

对`y`(复制)来说是这样的, 那么对`d`(删除), `v`(可视化选择), `gU`(转大写), `gu`(转小写)等等命令来说也是同样适用的

### Level 4 - 适用Vim的超能力

<<未完待续>>

