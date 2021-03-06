# Markdown（2）

上回介绍到了段落标记和行内标记。这回我们分别介绍各类Markdown所支持的各种格式。这些格式有的是段落标记，有的是行内标记，有的则有段落标记和行内标记两种形式，有的则需要段落标记和行内标记配合才能生效。

## 标题和目录

###  标题标记

标题是一种段落标记。

就像之前提到的，在一个段落行首加`#`然后空格（一定要有空格），就把这一段标记为了标题。如果加2个`#`就表示二级标题，如果加3个`#`就表示三级标题。依此类推，直到六级标题。一般没有七级标题。

```markdown
# 这是一级标题

## 这是二级标题

### 这是三级标题

#### 这是四级标题

## 这是另一个二级标题

## 这里还有一个二级标题
```

### 标题的规范

所有标题应当形成一个树状的结构。跟在同级标题后边的标题表示并列关系，跟在高级（数字越小越高级）标题后边的标题从属于所跟的高级标题。这样一级标题就是树根，二级三级等一级一级的标题就书的枝杈。

为了维持树形结构，尽量只在一个文本中使用一次一级标题。而且这个一级标题最好是第一个段落。也不要跨级别使用标题。二级标题下变一定用三级，三级下用四级。不要出现二级标题下直接用四级、五级、六级标题的情况。还有不要给文章加太多的层级。

虽然Markdown支持到六级标题，但是一般五六级标题根本用不到。如果文章比较短，用到二级标题就可以了。文章很长的情况下才需要用三四级标题进一步细分。

这些不是强制性的语法规则，而是一种代码风格。帮助你写出容易看懂， 井然有序的代码。

> **Typora快捷键**
>
> Typora默认当光标在某一段时使用<kbd>Ctrl</kbd>加数字键的组合键可以把这一段设置成数字对应等级的标题。使用<kbd>Ctrl</kbd>+<kbd>=</kbd>可以让光标所在段落标题等级升高一级。用<kbd>Ctrl</kbd>+<kbd>-</kbd>降低一级。六级标题降低一级是普通段落。普通段落升高一级是六级标题。<kbd>Ctrl</kbd>+<kbd>0</kbd>把光标所在段落设为普通段落。

### 目录

Typora支持TOC标记。TOC就是Table Of Content的缩写。这个标记也是一个段落标记。但是它不需要标记任何的内容段落，单独作为一段就行了。源码中TOC标记写作`[toc]`。

```markdown
[toc]

# 这是一级标题

## 这是二级标题

### 这是三级标题

## 这是另一个二级标题
```

上边这段代码在渲染后，标记`toc`的地方会被自动生成的目录所代替。点击目录中的项目可以直接跳转到对应的段落。这个目录则是根据各个等级的标题标记所生成的。如果你按规范写标题标记，自动生成的目录会非常清晰。反之，只会生成一个很难看的目录。

TOC标记的插入位置，没有明确的要求。可以在一级标题之前，或者一级标题之后其他标题之前。也可以放到文本中任何地方。但是我建议TOC放在文章中靠前的地方比较好。

> **不一定要用TOC**
>
> Typora编辑Markdown的时候可以用侧栏查看文章大纲结构（也是根据标题生成的）。Typora在导出PDF的时候，不论有没有TOC标记，都会自动生成PDF的书签。这种情况下，我认为不一定要用TOC标记再在页面中插入一个目录。

## 引用段落

### 引用段落标记

引用段落是一种段落标记。被标记的段落会显示为引用段落样式，通常是引述内容，注释等。在样式上可以和正文相区别。

在段首加`>`然后空格，就把整个段落标记为引用段落。

### 引用段落的链接

如果两个相邻的段落都被标记为引用段落。那么这两个引用段落会表现为两个互不相连的引用块。如果把分隔两个段落的空行上打上也打上`>`。那么两个引用段落就会合并到一个引用块中显示（但是仍为两个段落）。

```markdown
> 这两个引用段

> 彼此不连接

> 下边这两个引用段
>
> 会显示在同一个引用块里。但是是一个引用块里的两段。
```

### 引用段落的嵌套

引用块里还能嵌套别的格式。比如一个引用段在表示引用的标记`>`（注意加个空格）之后再加上`#`（也要加空格）。那么这个段落就会表示为引用中的标题。

```markdown
夏五月，郑伯克段于鄢。

> ## 《左传》的看法
> 
> 共叔段超越了一个做弟弟的本分，所以称段而不是弟。
>
> ## 《公羊传》的看法
>
> 之所以说“克”，那完全是为了强调郑庄公的恶。
>
> ## 《谷梁传》的看法
>
> 所不说杀，而说克，那是为了表示，共叔段当时不是只身一人，而是有很多人追随他。
```

引用块中还能嵌套引用块。我们之前介绍的单个`>`是一级引用。而`>>`是二级引用，表示引用中的引用。例如：

```markdown
一天世界君又在睡觉了。

> 我是听酒石酸说的。
>
>> 酒石酸说他是听一天世界君自己说的。
```

> 虽然Markdown允许三级引用，四级引用这样复杂的引用，也允许在引用中嵌套大部分其他段落标记。但是我不建议故意写这么复杂的嵌套。一般的文章根本不需要这么复杂的排版格式来说明思路。弄得太复杂一方面给自己添麻烦，一方面让读者看着都头大。

> **Typora** 技巧
>
> 当输入一个引用段落后。按<kbd>Enetr</kbd>的话，Typora会自动把新行也算到这个引用块里。你可以接着输入新的引用段落。
>
> 如果不想输入新的引用段落了，就在光标停留在这个引用块内的空行时，再次按<kbd>Enter</kbd>。这样就会退出引用块内的输入，回到普通段落模式。注意这种用法必须让光标停留在引用块内的“空行”（对应源码中只有引用标记`>`，而没有写其他任何内容的行）。

## 列表

### 无序列表

如果要表示若干并列的条目，可以使用列表标记。列表算是一种段落标记。同一张列表当中，不同项目之间不需要有空行。但是一张表格的首行之前和尾行之后最好要有空行（就是说把一整张列表当作一个段落）。另外，同一张列表中每一个项目行首都必须加列表标记。

先来看无序列表。其标记是`-`（标记后也要空一格再写内容）。

```markdown
购物清单：

- 方便面两箱
- 可乐三桶
- 牙刷一个
- 5号电池2节 
```

> 无序列表的标记用`+`或者`*`也可以。但是不管用哪个，一定要统一。最好不要混用。

### 任务清单

在无序列表的标记和标记后的空格之后加上`[ ]`就表示任务清单项目（注意`[`和`]`之间有一个空格，`]`和后续内容之间也需要插入空格）。这个项目在渲染后`[ ]`会被渲染为一个可以勾选的框。如果打勾就表示已完成。默认`[ ]`表示没有被勾选，`[x]`表示被勾选。

```markdown
记得吃药

- [ ] 维生素C
- [x] 消食片
```

### 有序列表

如果列表中的项目有一定的顺序，那么就可以使用有序列表。有序列表在渲染的时候，从上到下会自动编上序号。有序列表的写法和无序列表类似，但是把`*`换成了`1.`（注意在后边要有空格）。

```markdown
1. 打开编辑器
1. 写一些内容
1. 导出为PDF格式
```

> 有序列表标记中不一定要都写成1。你也可以用1，2，3，4等按顺序写下来。但是这样做很麻烦，列表长一点容易数错 。而且如果写了十几条突然想起来中间要加一条很麻烦。后边的都要改。所以不如直接都写成`1.`，让编译器编译的时候自动排号。

### 列表的嵌套

同一层级的列表中最好不要混用不同列表。但是可以把不同种类的列表嵌套起来。

嵌套方式就是在列表某一个条目下一行直接写子列表。为了表示层级关系，里层子列表要比外层列表在行首多几个空格。一般来说为了美观整齐，如果外层列表是无序列表（或者任务清单），里层列表条目的列表标记前加2个空格。如果外层是有序列表，则里层列表的列表标记前加3个空格。

```markdown
1. 把大象装进冰箱
   1. 打开冰箱门
   1. 把大象装进去
   1. 把门关上
1. 把动物园埋了
   * 把猛兽埋了
     * 把老虎埋了
     * 把狮子埋了
   * 把食草动物埋了
```

虽然Markdown支持多层列表嵌套。但是仍然不建议把列表嵌套弄得太复杂。列表中的内容应当是比较简短的。如果你的一条用大段文字都说不清，而且里边还包含了若干层小结构。我建议你还是用一层标题加一段正文来表示比较好。

> **Typora快捷键**
>
> 为了叙述方便，我把外层的列表称为高级的，里层列表称为低级的。
>
> 在Typora的所见即所得编辑模式下，光标停留在一个列表项目上时，按<kbd>Tab</kbd>会让本条目的嵌套等级降低一级（视觉上就是往右移动了），<kbd>Shift</kbd>+<kbd>Tab</kbd>会让列表条目升高一级（视觉上就是往左移动了）。
>
> <kbd>Enter</kbd>在列表中的应用类似于引用段落中的。当完成一个列表项目的输入按回车，就会自动插入一个同级，同种类的列表条目。如果不想输入新条目了，就在出现这个空的新条目时再次按<kbd>Enter</kbd>。就会取消列表条目。不过是嵌套的条目。取消了内层列表条目，但是缩进还在。再次按<kbd>Enter</kbd>又会创建一个空的外层列表条目。再按<kbd>Enter</kbd>才能取消空的外部列表条目。所以如果嵌套比较深，需要多按几次<kbd>Enter</kbd>才能彻底退出列表输入。（也可以直接用鼠标点其他地方退出。）
>
> 另外<kbd>Backspace</kbd>可以删除列表标记。

​		

## 强调和标记

本部分介绍的几种格式都是用于行内的。

* 用一对`*`括起来的字用斜体显示。
* 用一对`**`括起来的字用粗体显示。
* 用一对`~~`括起来的字，会被加上删除线。

这几种强调之间可以嵌套。

```markdown
这是*斜体*，这是**粗体**，这是~~删除线~~。

这是***粗斜体***。这是~~*删除线加斜体*~~。这是~~**删除线加粗体**~~。这~~***是删除线加粗斜体***~~。

有的编辑器可能对强调嵌套不太支持。比如VSCode中粗斜体必须在被标记的文字（连同标记）前后加空格才能识别。写成这样 ***粗斜体*** 。
```

> 也可以用一对下划线`_`表示斜体，用一对双下划线`__`表示粗体。但是不管用哪种，请尽量保持一致。

以下三种格式需要在Typora的设置中启用才能使用。

* 用一对`~`表示把括住的字显示为下标。
* 用一对`^`表示把括住的字显示为上标。
* 用一对`==`表示把括住的字显示为高亮。

```markdown
水分子化学式是H~2~O。钙离子写作Ca^2+^。

这是==高亮==。
```

> 个人认为，为了保持统一。在启用了内联公式后不需要再启用这种风格的上标和下标。而高亮的使用看个人喜好。
>
> 需要注意，有的编辑器并不支持删除线，高亮之类的语法。

> Typora中有一些快捷键可以直接修改选中内容的行内格式。<kbd>Ctrl</kbd>+<kbd>B</kbd>是加粗，<kbd>Ctrl</kbd>+<kbd>I</kbd>是倾斜。<kbd>Ctrl</kbd>+<kbd>\\</kbd>表示清除选中内容的格式。

## 代码排版

### 显示有语法意义的字符

如果你要在文章中显示的字符正好在Markdown中有语法意义（例如`*`，`#`），可以在这些符号前加反斜杠`\`表示取消其语法意义（反斜杠本身是个标记，不会显示出来）。如果要显示反斜杠本身，就用反斜杠标记反斜杠。`\\`实际会显示1个反斜杠。

### 行内代码

如果一串字符中带语法意义的字符比较多时，一个一个用反斜杠标记就很麻烦。可以用一对反引号<code>`</code>把这段内容括起来。表示代码片段。代码片段中的符号都会原样显示（包括反斜杠，但除了反引号）。

```markdown
在Emacs中写入代码`# include<stdio.h>`。
```

### 代码段

连续3个反引号<code>```</code>占1行就是代码段标记。一篇文章从头到尾，所有的代码段标记两两配对（不会发生嵌套）。一对配对的代码段之间的内容会被认为都是代码而原样输出（除了代码段标记本身）。

一个代码段的开头标记之前和结尾标记之后最好有空行。

>在Typora中输入代码段时，如果按回车，新行仍然在代码段内。需要<kbd>Ctrl</kbd>+<kbd>Enter</kbd>来结束代码段的输入（或者把光标移动到其他地方）。

### 代码字体和语法高亮

行内代码和代码段中的代码都会使用专门的代码显示字体显示。一般是等宽字体。这点可以在CSS中修改。

对于代码段而言可以在开头标记的3个反引号之后紧跟着写上代码语言名称。这样在渲染的时候关键字，变量，函数等就会自动被语法高亮功能渲染上特殊的颜色，格式等。例如：

```markdown
接下来的Python教学中会讲解以下代码。

​```python
def gen():
  clock=0
  def timer():
    nonlocal clock
    clock+=1
    return clock
  return timer
  
f1=gen()
f2=gen()
print(f1())
print(f1())
print(f1())
print(f2())
​```
```

因为行内代码和代码段内的文字会以专门字体（和专门样式）显示。即使你写的代码里不包含Markdown标记，只要写的内容是代码，就建议标记为代码或者代码段。

### 输入反引号的问题

如果一定要在代码片段中使用再写上反引号，可以使用HTML的code标签（不过不是很推荐，这样做必须检查同一段上下文有没有其他反引号）。如果多个反引号和code标签存在于同一个段落。谁先谁后，运算级如何很难说。

建议这种情况就把代码放到代码段里。代码段里除了一行只有3个反引号的代码段标记本身，不会误判其他代码。

那么如何在Markdown的代码段里写代码段本身呢？严格来说是不行的。因为代码段里转义字符反斜杠本身都失去了语法意义。所以就不能转义代码段标记。但是用Typora所见即所得模式会发现可以在代码段里写代码段标记。切换到源码模式就不难发现奥秘。原来Typora在代码段内的代码段标记前自动加了一个字符，这样整行就不再是代码段标记，所以就不会出现误判。这个字符在普通字体中不会显示所以看不出来。在Typora的源码模式下能看到是因为Typora源码模式用了特殊字体。

而插入的这个神秘字符叫做零宽度空格（ZERO WIDTH SPACE，缩写为ZWSP）Unicode编号200B，UTF-8编码E2 80 8B。在其他编辑器里也可以使用这个技巧。只不过输入这个字符不太方便。而Typora是自动输入的。


