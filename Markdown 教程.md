# Markdown 教程
## 富文本编辑器

随着人类历史的发展，记录成了文化思想传承的重要手段，从结绳记事，到龟甲石刻、帛锦文书、纸笔发明，计算机的出现彻底的变革了文字的录入和输出方式。
如何让普通人能够借助电脑实现文字创作，一直是推动各种编辑工具发展的内在动力。富文本工具的出现打破了只有程序员才使用电脑的局面，每个普通人也能通过敲击键盘和点击鼠标，完成文档创作工作。

文档创造包括两个方面：内容和“外貌”，内容主要包括文字，除去文字之外，还包括图片、表格等内容，而外貌即所说的格式或者样式。

如 Office Word、IWork 的 Papers、WPS 的文字等富文本编辑器通过把**内容输入**和**样式调整**相分离，使用者先输入纯文字，在通过鼠标选择，将不同的为赋予不同的样式，最终形成带格式的文档，这份文档的最终效果能够出现在屏幕上，进而打印出来。编辑过程中屏幕上生成的文档和打印出来的文档效果一致，这也就是所说的“所见即所得”的编辑器。然而，这个过程往往有一些不尽如人意的地方：

> 内容输入（输入）与格式调整（排版）状态分离

这就造成，使用者无法一气呵成的完成文档创作，需要在“内容输入”和“格式调整”两个状态不断切换，于是原本心如止水的创作过程被打破，必须通过不断地调整才能达到最终效果。

一些文本编辑工具出现了，他们把输入和排版两个过程分开，通过`标签`定义不同样式，通过`渲染`把最终的文档效果呈现，两者用`模板`相连，即通过模板指定不同标签具有不同的样式（外观）。HTML 和 Tex 就是这类的程序。





## 初步认识 Markdown

### Markdown 和常见的富文本编辑器有什么区别

如果只输入不带任何格式的文字，无需任何复杂的工具。正是为了赋予文字不同的「外貌」（即格式或者样式），我们才需要文字编辑器。例如输入的文字属于纯文本（即不带格式），而给文字标记上的颜色则属于文字的样式。对于用户来说，Markdown 编辑器和富文本编辑器（例如 Word2 )的作用是一致的：**使用者输入纯文字，通过编辑器的处理，使其拥有一份样式，最终得到带格式的文档。**

然而这两者的差距，就在处理文字的过程中。富文本编辑器以 Word 为例，输入文字后，选择不同的功能（通常是通过点击某个图标），例如加粗或者调整字体大小，处理后的效果直接显示在屏幕上，与打印出来的效果相同。所以富文本编辑器又叫「所见即所得」编辑器。

而 Markdown 编辑器则不同，输入文字后通常是在文字的前后同时输入一些标记字符，输入后在编辑窗口也不会即时的显示出效果3 。需要手动切换进预览模式查看处理效果。因为这些标记字符的存在，所以 Markdown 本身是一种标记语言。

## Markdown 的理念
## Markdown 的本质

如果仔细观察这两种编辑器和我们日常使用它们的习惯，就能更深一步理解这两种工具的差异。**在编辑文稿时，我们其实不是像小时候在格子纸中写文章那样一气呵成，而是不断的在「输入文字」和「编辑文字」两个状态中切换**。富文本编辑器「编辑文字」是通过点击图形化的功能按钮来实现，Markdown 编辑器则是通过标记字符去编辑。所以 Markdown 的核心就在于通过输入字符同时进行排版和内容输入。

当理解了「为什么 Markdown 里有那么多和内容无关的字符」这个问题之后，随之而来的可能就是两个概念的混淆——Markdown 语法和 Markdown 编辑器。我们口中常说的 Markdown 到底指什么呢。其实 Markdown 的创始人 John Gruber 这样定义：

> "Markdown" is ② things:
>
> (1) a plain text formatting syntax;
>
> (2) a software tool, that converts the plain text formatting to others.

通俗的说，首先Markdown 意味着一套标记语法，这些标记字符就是用来赋予文字不同格式；其次，能将标记字符转换，最终呈现出我们想要的排版效果的软件，就是所谓的 Markdown 编辑器。目前除了那些为了 Markdown 专门开发的编辑器之外，你会看到一些网站（例如简书）或者应用（例如 Airmail 的 Mac 版）注明「支持 Markdown」，这意味着他们的编辑器也可以完成将标记字符转换的过程。

## 理念

Markdown 的目标是实现「易读易写」。

可读性，无论如何，都是最重要的。一份使用 Markdown 格式撰写的文件应该可以直接以纯文本发布，并且看起来不会像是由许多标签或是格式指令所构成。Markdown 语法受到一些既有 text-to-HTML 格式的影响，包括 [Setext](http://docutils.sourceforge.net/mirror/setext.html)、[atx](http://www.aaronsw.com/2002/atx/)、[Textile](http://textism.com/tools/textile/)、[reStructuredText](http://docutils.sourceforge.net/rst.html)、[Grutatext](http://www.triptico.com/software/grutatxt.html) 和 [EtText](http://ettext.taint.org/doc/)，而最大灵感来源其实是纯文本电子邮件的格式。

### 兼容 HTML

Markdown 语法的目标是：成为一种适用于网络的书写语言。

Markdown 不是想要取代 HTML，甚至也没有要和它相近，它的语法种类很少，只对应 HTML 标记的一小部分。Markdown 的构想不是要使得 HTML 文档更容易书写。在我看来， HTML 已经很容易写了。Markdown 的理念是，能让文档更容易读、写和随意改。HTML 是一种发布的格式，Markdown 是一种书写的格式。就这样，Markdown 的格式语法只涵盖纯文本可以涵盖的范围。

不在 Markdown 涵盖范围之内的标签，都可以直接在文档里面用 HTML 撰写。不需要额外标注这是 HTML 或是 Markdown；只要直接加标签就可以了。

要制约的只有一些 HTML 区块元素――比如<div>、<table>、<pre>、<p>等标签，必须在前后加上空行与其它内容区隔开，还要求它们的开始标签与结尾标签不能用制表符或空格来缩进。Markdown 的生成器有足够智能，不会在 HTML 区块标签外加上不必要的 <p> 标签。

例子如下，在 Markdown 文件里加上一段 HTML 表格：

```html
这是一个普通段落。

<table>
    <tr>
        <td>Foo</td>
    </tr>
</table>

这是另一个普通段落。
```

请注意，在 HTML 区块标签间的 Markdown 格式语法将不会被处理。比如，你在 HTML 区块内使用 Markdown 样式的*强调*会没有效果。

HTML 的区段（行内）标签如 <span>、<cite>、<del> 可以在 Markdown 的段落、列表或是标题里随意使用。依照个人习惯，甚至可以不用 Markdown 格式，而直接采用 HTML 标签来格式化。举例说明：如果比较喜欢 HTML 的 <a> 或 <img> 标签，可以直接使用这些标签，而不用 Markdown 提供的链接或是图像标签语法。

和处在 HTML 区块标签间不同，Markdown 语法在 HTML 区段标签间是有效的。

### 特殊字符自动转换

在 HTML 文件中，有两个字符需要特殊处理： < 和 & 。 < 符号用于起始标签，& 符号则用于标记 HTML 实体，如果你只是想要显示这些字符的原型，你必须要使用实体的形式，像是 &lt; 和 &amp;。

& 字符尤其让网络文档编写者受折磨，如果你要打「AT&T」 ，你必须要写成「AT&amp;T」。而网址中的 & 字符也要转换。比如你要链接到：

http://images.google.com/images?num=30&q=larry+bird

你必须要把网址转换写为：

http://images.google.com/images?num=30&q=larry+bird

才能放到链接标签的 href 属性里。不用说也知道这很容易忽略，这也可能是 HTML 标准检验所检查到的错误中，数量最多的。

Markdown 让你可以自然地书写字符，需要转换的由它来处理好了。如果你使用的 & 字符是 HTML 字符实体的一部分，它会保留原状，否则它会被转换成 &amp;。

所以你如果要在文档中插入一个版权符号©，你可以这样写：

```html
&copy;
```

Markdown 会保留它不动。而若你写：

```html
AT&T
```

Markdown 就会将它转为：

```html
AT&amp;T
```

类似的状况也会发生在 < 符号上，因为 Markdown 允许 兼容 HTML ，如果你是把 < 符号作为 HTML 标签的定界符使用，那 Markdown 也不会对它做任何转换，但是如果你写：

```html
4 < 5
```

Markdown 将会把它转换为：

```html
4 &lt; 5
```

不过需要注意的是，code 范围内，不论是行内还是区块， < 和 & 两个符号都一定会被转换成 HTML 实体，这项特性让你可以很容易地用 Markdown 写 HTML code （和 HTML 相对而言， HTML 语法中，你要把所有的 < 和 & 都转换为 HTML 实体，才能在 HTML 文件里面写出 HTML code。）


## Markdown 的优点

经过前面的铺垫，我相信你已经能体会 Markdown 的特殊之处。而正是这些乍看之下有些怪异的设计，让它形成了自己的独特优势。为了能更直观的体会 Markdown 的不同之处，建议在阅读的同时打开 [Cmd 在线编辑器](https://www.zybuluo.com/mdeditor) 尝试下面的简单例子（如果只是想试用而不想注册，可以全选，然后删除当前页面的文字）。别担心不理解那些标记字符的含义，在后文中会有相应的解释。

### 书写过程流畅

如前文中所讲，用富文本编辑器编辑文字时是两个不连续的动作，输入文字时双手放在键盘上，编辑文字则需要视线和手离开输入框和键盘，去寻找和点击功能按钮。很少人使用 Word 时是一次性输入全部文字后，再去一次性的编辑文字格式（然而这却是使用 Word 相对较高效的方式）。

而 Markdown 的「书写流畅」就体现在将**这两个动作合成一个输入字符的动作**。视线一直固定在光标处，手也不需要移动，只是输入时使用不同的字符——文本字符和标记字符——就能同时完成编辑和输入。这种体验类似纸笔时代的书写，使用者全部的注意力都可以集中在将大脑中的语句输出，而不用不停地切换。

**例 1：**试着在编辑框中输入下面这段字符：

```
尼采说：
> Was mich nicht umbringt, macht mich **stärker**.
```

你会发现引用的句子已经被展示成了特殊的样式，而 stärker 这个单词也被加粗了。可以试试或回想下如果在 Word 上要如何实现这个效果。

### 格式不随编辑器而改变，导出与分享方便

如果你有足够多使用 Word 的经历，一定会体验过「同一份 Word 文档，在不同地方打开就变得不同」这样的魔幻现实主义色彩的经历。不同版本、不同平台之间的 Word 的文档由于软件工程方面的原因，一直不能保证「在任何地方打开都显示同样的效果」，更别说 WPS 这类第三方的软件。这让通过 Word 格式来分享文档显得不够保险。

而 Markdown 则完全规避了硬件、编辑器和平台差异带来的问题。由于所有编辑器是基于一套 Markdown 语法来编写转换流程，就能**保证在任何地方，打开来都是同样的格式**。更安心的是，由于 Markdown 格式保持的文件本质上仍是一份纯文本，就能保证目前任何平台都有工具可以打开它，而不用担心对方是 Mac, 会不会打不开 Word 的场景。所以以 Markdown 格式来分享文档，远比富文本格式省心。

前文我们说过，Markdown 编辑器其实是负责将 Markdown 语法标记符转换成其他格式，这暗示了 Markdown 格式的导出也十分方便，因为这个转换的目标是可以随时变换的。以 [MarkEditor](https://sspai.com/34656) 为例，除了常见的 PDF 、HTML 和富文本格式（可以直接保持格式粘贴到 Word 中），还可以复制为微信公众号格式。

### 书写错误易发现

任何程度的使用者，在这两类工具的使用过程中都会出现使用错误4 ，这是不可避免的。然而 Word 的问题就在于，虽然所见即所得的界面让它可以即时的发现问题，但是由于它将编辑的过程交给了图形化的功能按键，出现问题时就无法回溯问题所在之处。例如选中一个单词设为粗体后，接下来输入的文字没有变回默认的字重这类错误。其次由于它的功能复杂程度很高，使用者可能没有正确的理解功能的使用场景，而只是做到了看上去排好了。例如常见的用空格而非分页符来分页，或者用空格来对齐，随后产生的排版问题，也很难直接在编辑界面中发现。

而 Markdown 由于是使用标记字符来控制排版，所以你**在预览时发现的错误都可以直接在文稿中去查看**，到底是标记字符输入错了，还是漏掉了字符。很多时候我们不会意识到这也是一个优势，但是在长期的使用中，就会体会到能快速发现问题和解决问题所给人带来的愉悦。

**例 2：**试着在编辑框中输入下面这段字符：

```
尼采说：
> Was mich **nicht umbringt, macht mich **stärker**.
```

还是第一个例子中的那句话，但是这次我想把「nicht」和「stärker」这两个词都加粗，加粗的标记字符是文字前后加上`**`，但是这时发现加粗的文字是错误的，通过看查看文稿你会很容易发现「nicht」这个词的后面忘了加上标记字符。

当然 Markdown 还有其他一些优势，例如可选的工具多样之类的，但是我认为这都不是它所具有的决定性的优势。上述三点都和 Markdown 的本质——标记语言——有关，这也是 Markdown 和富文本编辑的本质差异，也是富文本编辑器无论如何改进都不可能跨越的鸿沟。




## 了解基本 Markdown 语法

在对 Markdown 有了初步的认识后，我们可以真正地去了解这套略显「神秘」的标记语法。说它神秘只是因为对完全不了解编程语言的人来说，通过字符来实现功能仍显得不直观和缺乏逻辑。换句话说，作为初学者，真的只能去死记硬背这套语法吗？看似杂乱琐碎的标记字符之间有没有什么逻辑呢？

其实想到 Markdown 和其他富文本编辑器一样，都是用来编辑文字的功能，就不会有太多的恐惧，Markdown 语法只是将我们在富文本编辑器中常用的功能，换一种方式呈现出来了而已。下面我们就以来源于 [John Gruber 最早定义的一套基本语法](https://daringfireball.net/projects/markdown/) 为例，来了解 Markdown 主要的三大类标记字符。

这里提醒一下，下面不会罗列出所有的标记字符，因为看一遍并不会帮你记住这些标记字符。你可以在 [这里](http://wowubuntu.com/markdown/) 查看完整的文档。下面主要是对看似毫无逻辑的语法进行梳理，希望帮你有序的理解。

## 区块元素

### 段落和换行

一个 Markdown 段落是由一个或多个连续的文本行组成，它的前后要有一个以上的空行（空行的定义是显示上看起来像是空的，便会被视为空行。比方说，若某一行只包含空格和制表符，则该行也会被视为空行）。普通段落不该用空格或制表符来缩进。

「由一个或多个连续的文本行组成」这句话其实暗示了 Markdown 允许段落内的强迫换行（插入换行符），这个特性和其他大部分的 text-to-HTML 格式不一样（包括 Movable Type 的「Convert Line Breaks」选项），其它的格式会把每个换行符都转成 <br /> 标签。

如果你确实想要依赖 Markdown 来插入 <br /> 标签的话，在插入处先按入两个以上的空格然后回车。

的确，需要多费点事（多加空格）来产生 <br /> ，但是简单地「每个换行都转换为 <br />」的方法在 Markdown 中并不适合， Markdown 中 email 式的 区块引用 和多段落的 列表 在使用换行来排版的时候，不但更好用，还更方便阅读。

### 标题

Markdown 支持两种标题的语法，类 Setext 和类 atx 形式。

类 Setext 形式是用底线的形式，利用 = （最高阶标题）和 - （第二阶标题），例如：

```html
This is an H1
=============

This is an H2
-------------
```

任何数量的 = 和 - 都可以有效果。

类 Atx 形式则是在行首插入 1 到 6 个 # ，对应到标题 1 到 6 阶，例如：

```html
# 这是 H1

## 这是 H2

###### 这是 H6
```

你可以选择性地「闭合」类 atx 样式的标题，这纯粹只是美观用的，若是觉得这样看起来比较舒适，你就可以在行尾加上 #，而行尾的 # 数量也不用和开头一样（行首的井字符数量决定标题的阶数）：

```html
# 这是 H1 #

## 这是 H2 ##

### 这是 H3 ######
```

### 区块引用Blockquotes

Markdown 标记区块引用是使用类似 email 中用 > 的引用方式。如果你还熟悉在 email 信件中的引言部分，你就知道怎么在 Markdown 文件中建立一个区块引用，那会看起来像是你自己先断好行，然后在每行的最前面加上 > ：

```md
> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
> consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
> Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.
> 
> Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
> id sem consectetuer libero luctus adipiscing.
```

Markdown 也允许你偷懒只在整个段落的第一行最前面加上 > ：

```md
> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.

> Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
id sem consectetuer libero luctus adipiscing.
```

区块引用可以嵌套（例如：引用内的引用），只要根据层次加上不同数量的 > ：

```md
 This is the first level of quoting.
>
> > This is nested blockquote.
>
> Back to the first level.
```

引用的区块内也可以使用其他的 Markdown 语法，包括标题、列表、代码区块等：

```md
> ## 这是一个标题。
> 
> 1.   这是第一行列表项。
> 2.   这是第二行列表项。
> 
> 给出一些例子代码：
> 
>     return shell_exec("echo $input | $markdown_script");
```

任何像样的文本编辑器都能轻松地建立 email 型的引用。例如在 BBEdit 中，你可以选取文字后然后从选单中选择增加引用阶层。

### 列表

Markdown 支持有序列表和无序列表。

无序列表使用星号、加号或是减号作为列表标记：

```md
*   Red
*   Green
*   Blue
```

等同于：

```md
+   Red
+   Green
+   Blue
```

也等同于：

```md
-   Red
-   Green
-   Blue
```

有序列表则使用数字接着一个英文句点：

```md
1.  Bird
2.  McHale
3.  Parish
```

很重要的一点是，你在列表标记上使用的数字并不会影响输出的 HTML 结果，上面的列表所产生的 HTML 标记为：

```md
<ol>
<li>Bird</li>
<li>McHale</li>
<li>Parish</li>
</ol>
```

如果你的列表标记写成：

```md
1.  Bird
1.  McHale
1.  Parish
```

或甚至是：

```md
3. Bird
1. McHale
8. Parish
```

你都会得到完全相同的 HTML 输出。重点在于，你可以让 Markdown 文件的列表数字和输出的结果相同，或是你懒一点，你可以完全不用在意数字的正确性。

如果你使用懒惰的写法，建议第一个项目最好还是从 1. 开始，因为 Markdown 未来可能会支持有序列表的 start 属性。

列表项目标记通常是放在最左边，但是其实也可以缩进，最多 3 个空格，项目标记后面则一定要接着至少一个空格或制表符。

要让列表看起来更漂亮，你可以把内容用固定的缩进整理好：

```md
*   Lorem ipsum dolor sit amet, consectetuer adipiscing elit.
    Aliquam hendrerit mi posuere lectus. Vestibulum enim wisi,
    viverra nec, fringilla in, laoreet vitae, risus.
*   Donec sit amet nisl. Aliquam semper ipsum sit amet velit.
    Suspendisse id sem consectetuer libero luctus adipiscing.
```

但是如果你懒，那也行：

```md
*   Lorem ipsum dolor sit amet, consectetuer adipiscing elit.
Aliquam hendrerit mi posuere lectus. Vestibulum enim wisi,
viverra nec, fringilla in, laoreet vitae, risus.
*   Donec sit amet nisl. Aliquam semper ipsum sit amet velit.
Suspendisse id sem consectetuer libero luctus adipiscing.
```

如果列表项目间用空行分开，在输出 HTML 时 Markdown 就会将项目内容用 <p> 标签包起来，举例来说：

```md
*   Bird
*   Magic
```

会被转换为：

```md
<ul>
<li>Bird</li>
<li>Magic</li>
</ul>
```

但是这个：

```md
*   Bird

*   Magic
```

会被转换为：

```md
<ul>
<li><p>Bird</p></li>
<li><p>Magic</p></li>
</ul>
```

列表项目可以包含多个段落，每个项目下的段落都必须缩进 4 个空格或是 1 个制表符：

```md
1.  This is a list item with two paragraphs. Lorem ipsum dolor
    sit amet, consectetuer adipiscing elit. Aliquam hendrerit
    mi posuere lectus.

    Vestibulum enim wisi, viverra nec, fringilla in, laoreet
    vitae, risus. Donec sit amet nisl. Aliquam semper ipsum
    sit amet velit.

2.  Suspendisse id sem consectetuer libero luctus adipiscing.
```

如果你每行都有缩进，看起来会看好很多，当然，再次地，如果你很懒惰，Markdown 也允许：

```md
*   This is a list item with two paragraphs.

    This is the second paragraph in the list item. You're
only required to indent the first line. Lorem ipsum dolor
sit amet, consectetuer adipiscing elit.

*   Another item in the same list.
```

如果要在列表项目内放进引用，那 > 就需要缩进：

```md
*   A list item with a blockquote:

    > This is a blockquote
    > inside a list item.
```

如果要放代码区块的话，该区块就需要缩进两次，也就是 8 个空格或是 2 个制表符：

```md
*   一列表项包含一个列表区块：

        <代码写在这>
```

当然，项目列表很可能会不小心产生，像是下面这样的写法

```md
1986. What a great season.
```

换句话说，也就是在行首出现数字-句点-空白，要避免这样的状况，你可以在句点前面加上反斜杠。

```md
1986\. What a great season.
```

### 代码区块

和程序相关的写作或是标签语言原始码通常会有已经排版好的代码区块，通常这些区块我们并不希望它以一般段落文件的方式去排版，而是照原来的样子显示，Markdown 会用 <pre> 和 <code> 标签来把代码区块包起来。

要在 Markdown 中建立代码区块很简单，只要简单地缩进 4 个空格或是 1 个制表符就可以，例如，下面的输入：

```md
这是一个普通段落：

    这是一个代码区块。
```

Markdown 会转换成：

```md
<p>这是一个普通段落：</p>

<pre><code>这是一个代码区块。
</code></pre>
```

这个每行一阶的缩进（4 个空格或是 1 个制表符），都会被移除，例如：

```md
Here is an example of AppleScript:

    tell application "Foo"
        beep
    end tell
```

会被转换为：

```md
<p>Here is an example of AppleScript:</p>

<pre><code>tell application "Foo"
    beep
end tell
</code></pre>
```

一个代码区块会一直持续到没有缩进的那一行（或是文件结尾）。

在代码区块里面， & 、 < 和 > 会自动转成 HTML 实体，这样的方式让你非常容易使用 Markdown 插入范例用的 HTML 原始码，只需要复制贴上，再加上缩进就可以了，剩下的 Markdown 都会帮你处理，例如：

```md
<div class="footer">
  &copy; 2004 Foo Corporation
</div>
```

会被转换为：

```md
<pre><code>&lt;div class="footer"&gt;
    &amp;copy; 2004 Foo Corporation
&lt;/div&gt;
</code></pre>
```

代码区块中，一般的 Markdown 语法不会被转换，像是星号便只是星号，这表示你可以很容易地以 Markdown 语法撰写 Markdown 语法相关的文件。

### 分隔线

你可以在一行中用三个以上的星号、减号、底线来建立一个分隔线，行内不能有其他东西。你也可以在星号或是减号中间插入空格。下面每种写法都可以建立分隔线：

```md
* * *

***

*****

- - -

---------------------------------------
```

## 区段元素

### 链接

Markdown 支持两种形式的链接语法： 行内式和参考式两种形式。

不管是哪一种，链接文字都是用 [方括号] 来标记。

要建立一个行内式的链接，只要在方块括号后面紧接着圆括号并插入网址链接即可，如果你还想要加上链接的 title 文字，只要在网址后面，用双引号把 title 文字包起来即可，例如：

```md
This is [an example](http://example.com/ "Title") inline link.

[This link](http://example.net/) has no title attribute.
```

会产生：

```md
<p>This is <a href="http://example.com/" title="Title">
an example</a> inline link.</p>

<p><a href="http://example.net/">This link</a> has no
title attribute.</p>
```

如果你是要链接到同样主机的资源，你可以使用相对路径：

```md
See my [About](/about/) page for details.
```

参考式的链接是在链接文字的括号后面再接上另一个方括号，而在第二个方括号里面要填入用以辨识链接的标记：

```md
This is [an example][id] reference-style link.
```

你也可以选择性地在两个方括号中间加上一个空格：

```md
This is [an example] [id] reference-style link.
```

接着，在文件的任意处，你可以把这个标记的链接内容定义出来：

```md
[id]: http://example.com/  "Optional Title Here"
```

链接内容定义的形式为：

- 方括号（前面可以选择性地加上至多三个空格来缩进），里面输入链接文字
- 接着一个冒号
- 接着一个以上的空格或制表符
- 接着链接的网址
- 选择性地接着 title 内容，可以用单引号、双引号或是括弧包着

下面这三种链接的定义都是相同：

```md
[foo]: http://example.com/  "Optional Title Here"
[foo]: http://example.com/  'Optional Title Here'
[foo]: http://example.com/  (Optional Title Here)
```

**请注意：**有一个已知的问题是 Markdown.pl 1.0.1 会忽略单引号包起来的链接 title。

链接网址也可以用方括号包起来：

```md
[id]: "Optional Title Here"
```

你也可以把 title 属性放到下一行，也可以加一些缩进，若网址太长的话，这样会比较好看：

```md
[id]: http://example.com/longish/path/to/resource/here
    "Optional Title Here"
```

网址定义只有在产生链接的时候用到，并不会直接出现在文件之中。

链接辨别标签可以有字母、数字、空白和标点符号，但是并不区分大小写，因此下面两个链接是一样的：

```md
[link text][a]
[link text][A]
```

隐式链接标记功能让你可以省略指定链接标记，这种情形下，链接标记会视为等同于链接文字，要用隐式链接标记只要在链接文字后面加上一个空的方括号，如果你要让 "Google" 链接到 google.com，你可以简化成：

```md
[Google][]
```

然后定义链接内容：

```md
[Google]: http://google.com/
```

由于链接文字可能包含空白，所以这种简化型的标记内也许包含多个单词：

```md
Visit [Daring Fireball][] for more information.
```

然后接着定义链接

```md
[Daring Fireball]: http://daringfireball.net/
```

链接的定义可以放在文件中的任何一个地方，我比较偏好直接放在链接出现段落的后面，你也可以把它放在文件最后面，就像是注解一样。

下面是一个参考式链接的范例：

```md
I get 10 times more traffic from [Google] [1] than from
[Yahoo] [2] or [MSN] [3].

  [1]: http://google.com/        "Google"
  [2]: http://search.yahoo.com/  "Yahoo Search"
  [3]: http://search.msn.com/    "MSN Search"
```

如果改成用链接名称的方式写：

```md
I get 10 times more traffic from [Google][] than from
[Yahoo][] or [MSN][].

  [google]: http://google.com/        "Google"
  [yahoo]:  http://search.yahoo.com/  "Yahoo Search"
  [msn]:    http://search.msn.com/    "MSN Search"
```

上面两种写法都会产生下面的 HTML。

```md
<p>I get 10 times more traffic from <a href="http://google.com/"
title="Google">Google</a> than from
<a href="http://search.yahoo.com/" title="Yahoo Search">Yahoo</a>
or <a href="http://search.msn.com/" title="MSN Search">MSN</a>.</p>
```

下面是用行内式写的同样一段内容的 Markdown 文件，提供作为比较之用：

```md
I get 10 times more traffic from [Google](http://google.com/ "Google")
than from [Yahoo](http://search.yahoo.com/ "Yahoo Search") or
[MSN](http://search.msn.com/ "MSN Search").
```

参考式的链接其实重点不在于它比较好写，而是它比较好读，比较一下上面的范例，使用参考式的文章本身只有 81 个字符，但是用行内形式的却会增加到 176 个字元，如果是用纯 HTML 格式来写，会有 234 个字元，在 HTML 格式中，标签比文本还要多。

使用 Markdown 的参考式链接，可以让文件更像是浏览器最后产生的结果，让你可以把一些标记相关的元数据移到段落文字之外，你就可以增加链接而不让文章的阅读感觉被打断。

### 强调

Markdown 使用星号（*）和底线（_）作为标记强调字词的符号，被 * 或 _ 包围的字词会被转成用 <em> 标签包围，用两个 * 或 _ 包起来的话，则会被转成 <strong>，例如：

```md
*single asterisks*

_single underscores_

**double asterisks**

__double underscores__
```

会转成：

```md
<em>single asterisks</em>

<em>single underscores</em>

<strong>double asterisks</strong>

<strong>double underscores</strong>
```

你可以随便用你喜欢的样式，唯一的限制是，你用什么符号开启标签，就要用什么符号结束。

强调也可以直接插在文字中间：

```md
un*frigging*believable
```

但是**如果你的 \* 和 _ 两边都有空白的话，它们就只会被当成普通的符号。**

如果要在文字前后直接插入普通的星号或底线，你可以用反斜线：

```md
\*this text is surrounded by literal asterisks\*
```

### 代码

如果要标记一小段行内代码，你可以用反引号把它包起来（`），例如：

```md
Use the `printf()` function.
```

会产生：

```md
<p>Use the <code>printf()</code> function.</p>
```

如果要在代码区段内插入反引号，你可以用多个反引号来开启和结束代码区段：

```md
``There is a literal backtick (`) here.``
```

这段语法会产生：

```md
<p><code>There is a literal backtick (`) here.</code></p>
```

代码区段的起始和结束端都可以放入一个空白，起始端后面一个，结束端前面一个，这样你就可以在区段的一开始就插入反引号：

```md
A single backtick in a code span: `` ` ``

A backtick-delimited string in a code span: `` `foo` ``
```

会产生：

```md
<p>A single backtick in a code span: <code>`</code></p>

<p>A backtick-delimited string in a code span: <code>`foo`</code></p>
```

在代码区段内，& 和方括号都会被自动地转成 HTML 实体，这使得插入 HTML 原始码变得很容易，Markdown 会把下面这段：

```md
Please don't use any `<blink>` tags.
```

转为：

```md
<p>Please don't use any <code><blink></code> tags.</p>
```

你也可以这样写：

```md
`&#8212;` is the decimal-encoded equivalent of `&mdash;`.
```

以产生：

```md
<p><code>&amp;#8212;</code> is the decimal-encoded
equivalent of <code>&amp;mdash;</code>.</p>
```

### 图片

很明显地，要在纯文字应用中设计一个「自然」的语法来插入图片是有一定难度的。

Markdown 使用一种和链接很相似的语法来标记图片，同样也允许两种样式： 行内式和参考式。

行内式的图片语法看起来像是：

```md
![Alt text](/path/to/img.jpg)

![Alt text](/path/to/img.jpg "Optional title")
```

详细叙述如下：

- 一个惊叹号 !
- 接着一个方括号，里面放上图片的替代文字
- 接着一个普通括号，里面放上图片的网址，最后还可以用引号包住并加上 选择性的 'title' 文字。

参考式的图片语法则长得像这样：

```md
![Alt text][id]
```

「id」是图片参考的名称，图片参考的定义方式则和连结参考一样：

```md
[id]: url/to/image  "Optional title attribute"
```

到目前为止， Markdown 还没有办法指定图片的宽高，如果你需要的话，你可以使用普通的 <img> 标签。

## 其它

### 反斜杠

Markdown 可以利用反斜杠来插入一些在语法中有其它意义的符号，例如：如果你想要用星号加在文字旁边的方式来做出强调效果（但不用 <em> 标签），你可以在星号的前面加上反斜杠：

```md
\*literal asterisks\*
```

Markdown 支持以下这些符号前面加上反斜杠来帮助插入普通的符号：

```md
\   反斜线
`   反引号
*   星号
_   底线
{}  花括号
[]  方括号
()  括弧
#   井字号
+   加号
-   减号
.   英文句点
!   惊叹号
```

### 自动链接

Markdown 支持以比较简短的自动链接形式来处理网址和电子邮件信箱，只要是用方括号包起来， Markdown 就会自动把它转成链接。一般网址的链接文字就和链接地址一样，例如：

```md
<http://example.com/>
```

Markdown 会转为：

```md
<a href="http://example.com/">http://example.com/</a>
```

邮址的自动链接也很类似，只是 Markdown 会先做一个编码转换的过程，把文字字符转成 16 进位码的 HTML 实体，这样的格式可以糊弄一些不好的邮址收集机器人，例如：

```md
<address@example.com>
```

Markdown 会转成：

```md
<a href="mailto:addre
ss@example.co
m">address@exa
mple.com</a>
```

在浏览器里面，这段字串（其实是 <a href="mailto:address@example.com">address@example.com</a>）会变成一个可以点击的「address@example.com」链接。

（这种作法虽然可以糊弄不少的机器人，但并不能全部挡下来，不过总比什么都不做好些。不管怎样，公开你的信箱终究会引来广告信件的。）

## Markdown 语法的演进

如果你是第一次接触 Markdown，可能会觉得之前提及的 Markdown 拥有的编辑功能稍显羸弱；而如果你之前接触过 Markdown，就会发现一个奇怪的现象：在一些 Markdown 文档中出现的标记字符，居然不在这份 John Gruber 写的官方文档里。这就自然联系到下一个话题——Markdown 语法的增强和不同语法之间的异同。

正如任何一门自然语言都会存在方言的现象一样，随着 Markdown 的发展和普及，越来越多人不满足于 John Gruber 定义的那些**功能有限**的标记字符，开始以他的语法为基础，拓展出各种各样的「Markdown 方言」。这些改进主要体现在两个方面：

1. 增加新的标记字符，带来了新的编辑功能，例如表格、脚注和目录等。
2. 修改了现有的标记字符，这主要出现在一些编辑器中，例如 Ulysses。

### 对基本语法的拓展

提到在编辑功能上对原生 Markdown 的拓展，最好的例子当属 Github Flavored Markdown。这是一套由 [Github](http://github.com/) 网站为了帮助他们的主体用户群——程序员——更好的书写项目文档而推出的 Markdown 版本。由于其网站本身的影响力，以及他们的用户和 Markdown 用户高度重合，所以这套语法在互联网中得到了广泛推广。

原有的 Markdown 语法的功能稍显不足，Github Flavored Markdown 在前面所说的语法的三个方面都做出了相应的增强。同样的，你可以通过 [官方文档](https://help.github.com/articles/basic-writing-and-formatting-syntax/) 来查看全部的语法。相较原生语法，Github Flavored Markdown 主要做了以下改进：

- 在对文字处理方面，它可以直接将网址高亮出来（原生语法需要加相应的标记字符）。
- 在对段落的处理方面，对原有代码块进行了增强，如果你在代码块后表明代码语言：

```
    ```python
    def 点赞机():
        if 文章不错：
            return 点赞
        else:
            return 差评
```


就能直接看到相应编程语言的语法高亮。

- 要插入文章元素方面，它支持在 Markdown 里写表格，如果你这么写：

```
| First Header | Second Header |
| ------------ | ------------- |
| Content Cell | Content Cell  |
| Content Cell | Content Cell  |
```

就会显示成：

| First Header | Second Header |
| ------------ | ------------- |
| Content Cell | Content Cell  |
| Content Cell | Content Cell  |

Github Flavored Markdown 是个很好的案例，说明了为什么会有人对原有的基本 Markdown 语法进行改进——**就是为了满足各种原生 Markdown 没有提供的需求**。

除了 Github Flavored Markdown 之外，MultiMarkdown 也不能不提。事实上目前众多编辑器都或多或少从 Multimarkdown 获取了一些灵感，相比 Github Flavored Markdown，Multimarkdown 是一套功能更为强大，同时语法更复杂的体系。如果有兴趣，你可以去 [官网](http://fletcherpenney.net/) 查看完整的语法文档。而你会在很多编辑器中都能发现，它们或多或少的支持了 MultiMarkdown 的语法。

不过如果你是初学者，我能给的建议是：先**不要**一上来就接触太多不同的增强型语法，这样会使得你愈发困惑。如果在日后使用中遇到了某些特殊的需求，例如脚注，再去搜索了解有哪些语法和编辑器支持你想要的那些功能[1](https://sspai.com/post/36682#fn1)。

### 对通用语法的修改

除了上面所说的对基本语法的修改，还有的编辑器会对某些在通用语法中出现过的标记字符进行定制。例如，删除线的语法通常情况下是`~~要删除的文字~~`，但是在 [Bear](https://sspai.com/35830) 中，开发者将它定义成`-要删除的文章-`。

这种情况的出现，主要还是**不同的开发者对 Markdown 的标记字符的「好用」理解不同**。遇到这种情况大可不必担心，一般的编辑器都会给出自己的标记字符文档，有的还会让用户做出选择，是使用通用的语法标记，还是这个编辑器专属的语法。

既然有了多种选择就有比较，而作为使用者，我认为我们只需认识到有这种「方言现象」的存在就好，如果过于纠结哪套语法更好，其实并不能提高多少使用上的效率。由于 Markdown 编辑器的效率高度依赖使用者的肌肉记忆，也就使得使用者的习惯才是最主要的影响因子。对于你来说，**你习惯的语法才是效率最高的**。

## Markdown 的使用

前面是完整的对 Markdown 的介绍，看完之后，理论上你应该能上手 Markdown。这时「什么时候该用」和「用什么工具」的选择就会浮现出来。事实上，我并不希望作为初学者你一开始就陷入「对工具得选择」而忘记了 Markdown 的初衷，所以接下来对这两个问题的回答，我都只会提出一两个例子，作为引导，而非像之前力求全面系统的阐述。

### Markdown 的局限性

「什么时候该用 Markdown」，其实是个回答非常个性化的问题。为了厘清 Markdown 和其他编辑器的边界，与其枚举一个个应用场景，不如把问题改为**「什么时候不该用 Markdown」**。

前文有提到，Markdown 只是一个「轻量级标记语言」，相比同为标记语言的 Latex 、Word 或 Pages 这类文字处理软件，更不用说 Indesign 这种专业级的排版软件，Markdown 在排版的功能上显得羸弱。与最熟悉的 Word 相比，稍微对比一下就能发现其中的缺陷：

1. **Markdown 无法对「段落」进行灵活处理**。在 Word 中你可以随意插入文本框，调整它的位置。尽管这并不是一个常见的用法，但是这意味着，Word 能以段落为单位进行排版（Latex 也可以做到相似的效果），相比 Markdown 只能线性的对文字排版，专门的排版软件无疑是更能满足专业需求的。
2. **Markdown 对非纯文本元素的排版能力很差**，最常见的例子就是图片。诚然，现在很多编辑器都支持了图文混排，但是受制于纯文本格式，Markdown 编辑器几乎不可能做到 Word 一样对图片灵活的调整位置，更不用说文字围绕图片进行自适应排版之类的效果。

可以看出，这些弱势都来源于 Markdown 本身的纯文本格式，因为 Markdown 从一开始就定位为「文字输入工具」，排版功能也是基于 HTML 的延伸，**并不适合对排版格式自定义程度较高的文档进行排版。**

### 适用 Markdown 的几个场景

尽管 Markdown 尚不是大众化的工具，但是感谢开发者们源源不断的创意，为我们提供了极为丰富的工具选择。工具的多样，让 Markdown 能渗透进各种各样的场景。小到写备忘录，大到完成一部书稿，都有相应优秀 Markdown 工具。想在一篇文章里罗列全部的场景基本不可能，所以我们在这篇还是从 Markdown 本身的特质出发，看看它在某些场景下的表现。

#### 网络环境下的写作

Markdown 基于 HTML 语言而被开发出来，开发它的目的就是创造一门「更易读、更易写」的语言用于网络世界的写作。可以说，没有什么工具比 Markdown 更适合用于网络环境下的写作了。

早前的「网络环境下的写作」可能专指博客或者个人站点，但是随着移动互联网的兴起，微信公众号等媒介的出现，读者的阅读习惯也渐渐改变，Markdown 也顺应了这一时代的变化。对于原本的「自留地」——博客或个人站点—— Markdown 保持了一贯的方便，例如 MWeb 可以帮你把使用 Markdown 所写的文字一键生成静态网站。在长微博和微信公众号写作方面，Markdown 也有优势，例如 [MarkEditor](https://sspai.com/34656) 可以直接把文章从编辑器中发送到微信（朋友圈或好友），也可以复制成微信公众号格式，省去了在微信后台编辑的功夫。

总结起来，在网络环境下的写作， **Markdown 可以让使用者专心于文章书写，而非排版**。

#### 文档协作

之前是利用了 Markdown 「写作即排版」的特点，而现在是利用它「纯文本格式」的优势。一份 Markdown 文本用任何软件在任何系统下打开，都能保证基本的格式不错乱（起码能打开没有乱码的纯文本文档），这使得：

1. 团队成员间可以自由选用自己喜欢的操作系统和编辑器工具来进行写作，而不局限于 Word 或者 Google Docs等只支持富文本编辑的软件。
2. 文档的展示方式不仅仅是在编辑器中，你可以随时把文档转换成网页，任何时候任何人都可以方便地查看。

用 Markdown 来协作，你既可以选择熟悉的共享文件的方式（借助网盘），也可以用 Simplenote 或者 Quip 这类内置了协作功能的编辑器。无论如何，**用 Markdown 来文档协作会比其他工具更自由。**

#### 其他领域

正如上文所讲，由于开发者们的创意，让 Markdown 几乎渗透进每一个需要文字书写的领域。

统计学者可以利用 R Markdown 直接将自己的脚本和图表排版成一篇报告，这项功能甚至是直接集成到 RStudio（一款 R 语言的 IDE）中的；由于有 Pandoc 这个格式转换利器，理论上可以将 Markdown 转换为常见的 Docx 或者 Tex 格式文档，这让学术写作者和办公人士可以将 Markdown 作为初稿的工具；借助马克飞象等工具，使得 Markdown 可以和 Evernote 这类笔记软件结合起来。

这些 Markdown 进阶的用法，在本文就不做展开。由此来看，相比熟悉的 Word 等工具，**Markdown 的应用场景不是更窄，反而是更广**。

## Markdown 工具的推荐

本文是定位于完全不了解或者还没有习惯 Markdown 的读者来入门的文章，而不是给已有自己使用习惯或者工具选择的读者，同时也不是 Markdown 工具的横向对比评测，所以，在工具的选择上，我也只会给出我认为最适合入门的那一款。这意味着，这不是要选出最好的 Markdown 编辑器，而是最适合作为入门使用的 Markdown 编辑器。至于什么算是适合入门者的？我认为最好要达到以下三点要求：

1. **能使用通用语法书写**。尽管各式各样的拓展型语法增强了 Markdown 的功能，但是对于刚开始接触这门工具的人来说，首先掌握最常见的用法更利于以后的自由选择。
2. **有明确的使用场景**。Markdown 实在是太容易学了，但是对很多人而言，没有使用起来的原因之一是：缺乏一个明确的「这里我要用 Markdown」 的场景。所以编辑器的设计上最好有明确的使用场景。
3. **在功能或设计上优化 Markdown**。原则上来说，任何能输入文本的地方都能写 Markdown 格式的文本（甚至在 Word 里）。那么对于入门者的工具而言，一定要在某些地方优化了书写 Markdown 的体验。比如解决了图文混排，提供了语法高亮等一些附属功能。

下文针对各平台的推荐我都是根据上述三个角度来挑选的。所以再一次强调，以下的推荐只是我认为**最适合入门者**的编辑器，并不代表其他软件不如这三款或者不适合刚入门的人上手。事实上你可以完全根据上述三点，去自己感受和选择其他的编辑器。

## 感谢

感谢http://daringfireball.net/projects/markdown/

## Markdown 免费编辑器

Windows 平台

- [MarkdownPad](http://markdownpad.com/)
- [MarkPad](http://code52.org/DownmarkerWPF/)

Linux 平台

- [ReText](http://sourceforge.net/p/retext/home/ReText/)

Mac 平台

- [Mou](http://mouapp.com/)

在线编辑器

- [Markable.in](http://markable.in/)
- [Dillinger.io](http://dillinger.io/)

浏览器插件

- [MaDe](https://chrome.google.com/webstore/detail/oknndfeeopgpibecfjljjfanledpbkog) (Chrome)

高级应用(Sublime Text 2 + MarkdownEditing 教程)

- [Sublime Text 2](http://www.sublimetext.com/2)
- [MarkdownEditing](http://ttscoff.github.com/MarkdownEditing/)
- [教程](http://lucifr.com/2012/07/12/markdownediting-for-sublime-text-2/)

------------

## 参考

[http://www.markdown.cn/](http://www.markdown.cn/)