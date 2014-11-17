html标签语义化：
========================                        
1、什么是HTML语义化？
-------------------------
基本上都是围绕着几个主要的标签，像标题（H1~H6）、列表（li）、强调（strong em）等等。
根据内容的结构化（内容语义化），选择合适的标签（代码语义化）便于开发者阅读和写出更优雅的代码的同时让浏览器的爬虫和机器很好地解析。
2、为什么要语义化？
------------------------
为了在没有CSS的情况下，页面也能呈现出很好地内容结构、代码结构、为了裸奔时好看；
用户体验：例如title、alt用于解释名词或解释图片信息、label标签的活用；
有利于SEO：和搜索引擎建立良好沟通；
有助于爬虫抓取更多的有效信息：爬虫依赖于标签来确定上下文和各个关键字的权重；
方便其他设备解析（如屏幕阅读器、盲人阅读器、移动设备）以意义的方式来渲染网页；
便于团队开发和维护，语义化更具可读性，是下一步把网页的重要动向，遵循W3C标准的团队都遵循这个标准，可以减少差
异化。
3、写HTML代码时应注意什么？
------------------------
尽可能少的使用无语义的标签div和span；
在语义不明显时，既可以使用div或者p时，尽量用p, 因为p在默认情况下有上下间距，对兼容特殊终端有利；
不要使用纯样式标签，如：b、font、u等，改用css设置。
需要强调的文本，可以包含在strong或者em标签中（浏览器预设样式，能用CSS指定就不用他们），strong默认样式是加粗
（不要用b），em是斜体（不用i）；
使用表格时，标题要用caption，表头用thead，主体部分用tbody包围，尾部用tfoot包围。表头和一般单元格要区分开，
表头用th，单元格用td；
表单域要用fieldset标签包起来，并用legend标签说明表单的用途；
每个input标签对应的说明文本都需要使用label标签，并且通过为input设置id属性，在lable标签中设置for=someld来让
说明文本和相对应的input关联起来。

\<Hx\>
------------------------
        <h1>、<h2>、<h3>、<h4>、<h5>、<h6>,作为标题使用，并且依据重要性递减。<h1>是最高的等级。
例如:

CODE:
        \<h1\>文档标题<\/h1\>
        \<h2\>次级标题\</h2\>
而不要使用
        \<div class="title"\>文档标题\</div\>，或者\<span class="title"\>文档标题\</span\>.
        很明显搜索引擎对于后者是不会认为他是标题的。
\<p\>
------------------------
段落标记，知道了<p>作为段落，你就不会再使用<br/>来换行了，而且不需要<br/><br/>来区分段落与段落。<p></p>
中的文字会自动换行，而且换行的效果优于<br>
。段落与段落之间的空隙也可以利用CSS来控制，很容易而且清晰的区分出段落与段落。在利用行高(line-height)
很容易的定义出行间距，再定义首字下沉等效果，那就挺完美了。

\<ul\>、\<ol\>、\<li\>
------------------------
<ul>无序列表，很常见的到了大家广泛的使用，<ol>有序列表也挺常用。在web标准化过程中，<ul>还被更多的用于导航条，本
来导航条就是个列表，这样做是完全正确的，而且当你的浏览器不支持CSS的时候，导航链接仍然很好使，就是美观方面差了一
点。

\<dl\>、\<dt\>、\<dd\>
------------------------
dl就是“定义列表”。比如说词典里面的词的解释、定义就可以用这种列表。
例如：
CODE:
        \<dl\>        
        \<dt\>Dog\</dt\>        
        \<dd\>A carnivorous mammal of the family Canidae.\</dd\>        
        \</dl\>
CODE:
        \<dl\>
        \<dt\>上海滩\</dt\>            
        \<dd\>
        这部拍摄于1980年的《上海滩》堪称是香港电视史上最成功、最经典的剧集。            
        当年在香港播出以后，产生了巨大的轰动效应。
        \</dd\>            
        \<dt\>周润发\</dt\>            
        \<dd\>
        和所有伟大的影星一样，周润发印证了一个时代，一个香港电影的黄金时代。            
        风衣墨镜、冷血双枪、阳光微笑，都封存胶片之中，当我们回首寻望的时候，发哥已被刻为一个时代的坐标。
        \</dd\>
        \</dl\>

\<cite\>、cite 、\<q\>、 \<blockquote\>
------------------------
论坛和blog经常会用到引用别人的话，用<q>来标记简短的单行引用。Web浏览器会自动识别在<q> 
之间的内容。不幸的是，IE不能识别，并且有些时候， <q>会引起一些可访问性(Accessibility)
的问题。正因为如此，一些人建议尽量不要使用 <q>,手动的插入引用标记。在一个包含适当的类的 <span>
中加入单行的引用内容，那么就可以用CSS来给引用设计样式了，但是这个没有语义上的意义。 您可以读读Mark 
Pilgrim写的The Q tag  (http://diveintomark.org/archives/2002/05/04/the_q_tag )关于处理<q>相关问题的看法。
对于那些一段或者好几段的长篇引用，就应当使用 <blockquote>
了。CSS可以用来定义引用的样式。注意，一段文章是不可以直接放在<blockquote>
中的，引用的内容还必须包含在一个元素中，通常是<p>。属性cite既可以与<q> 一起用，也可以与<blockquote>
一起用，用来提供引用内容的来源地址。需要注意的是，如果你使用 <span>来代替 <q>标记引用内容,那么你就不能使用 
cite属性了。例如:

CODE:
        \<cite\>Designing with Web Standards\</cite\> is an excellent book by Jeffrey Zeldman.

CODE:
        \<p\> \<cite\>孔子\</cite\>曰：\<q\>学而不思则罔，思而不学则殆\</q\>.\</p\>

CODE:
        \<p\>The W3C says that \<q cite="http://www.w3.org/TR/REC-html40/ \<br>      
        struct/text.html#h-9.2.1"\>The presentation of phrase elements  \<br>         
        depends on the user agent.\</q\>.\</p\>        

CODE:
        <blockquote cite="http://www.w3cn.org/">        
        <p>&#8220;我们大部分人都有深刻体验，每当主流浏览器版本的升级，我们刚建立的网站就可能变得过时，   
        我们就需要升级或者重新建造一遍网站。例如1996-1999年典型的"浏览器大战"，        
        为了兼容 Netscape 和 IE，网站不得不为这两种浏览器写不同的代码。同样的，
        每当新的网络技术和交互设备的出现，我们也需要制作一个新版本来支持这种新技术或新设备，
        例如支持手机上网的 WAP 技术。类似的问题举不胜举：网站代码臃肿、繁杂浪费了我们大量的带宽；
        针对某种浏览器的 DHTML 特效，屏蔽了部分潜在的客户；不易用的代码，残障人士无法浏览网站等等。
        这是一种恶性循环，是一种巨大的浪费。&#8221;</p>
        </blockquote>
\<em\>、 \<strong\>
------------------------
\<em\> 是用作强调的，\<strong\>是用作重点强调的。 大部分浏览器用斜体显示强调的内容，用粗体来显示重点强调的内容，然
而，这是没有必要的，如果是为了确定强调内容的显示方式，最好的方法就是使用CSS来定义他们的表现。当你想要的只是视觉
上的效果时，就不要使用强调了。而且如果你想要强调但是还觉得粗体或者斜体不视觉效果没那么好，特别是斜体对于中文来
说，那么你完全可以定义一些其他的比较醒目的样式达到强调的效果。
例如:
CODE:
        \<p\>\<em\>强调\</em\> 的文本通常用斜体显示，
        然而， \<strong\>特别强调\</strong\> 的文本通常以粗体显示。\</p\>
        \<ins\>, \<del\>    知道del，就不要再用\<s\>做删除线了，用del显然更具有语义化。而且del还带有cite和datetime来表明删除
        的原因以及删除的时间。ins是表示插入，也有这样的属性。
\<table\>、\<td\>、\<th\>、\<caption\>、 summary
------------------------

XHTML中的表格不应用来布局。然而如果是为了标记列表的数据，就应该使用表格了。\<th\>为表格标题，属性summar为摘要，\<caption\>标签为首部说明，\<thead\>标签为表格头部，\<tbody\>标签为表格主体内容，\<tfoot\>标签为表格尾部。
其中还可以使用scope 可用于取代headers属性，标记含有表头信息的单元格，其中各数值的内容如下：
　row 指示当前单元格，为包含当前单元格的行提供相关的表头信息。
　col 指示当前单元格，为根据当前单元格指定的列提供相应的表头信息。
　rowgroup 指示当前单元格，为包含当前单元格的其余行组提供相关的表头信息。
　colgroup 指示当前单元格，为根据当前单元格指定的其余列组提供相应的表头信息。
abbr 用于定义表头单元格中的缩写名，如果没有定义该属性，则将默认单元格内容为节略形式。

4、HTML5新增了哪些语义标签：
------------------------
HTML5的革新之一：语义化标签一节元素标签。

在HTML5出来之前，我们用div来表示页面章节，但是这些div都没有实际意义。（即使我们用css样式的id和class形容这块内容
的意义）。这些标签只是我们提供给浏览器的指令，只是定义一个网页的某些部分。但现在，那些之前没“意义”的标签因为因
为html5的出现消失了，这就是我们平时说的“语义”。

但是也不要因为html5新标签的出现，而随意用之，错误的使用肯定会事与愿违。所以有些地方还是要用div的，就是因为div没
有任何意义的元素，他只是一个标签，仅仅是用来构建外观和结构。因此是最适合做容器的标签。

W3C定义了这些语义标签，不可能完全符合我们有时的设计目标，就像制定出来的法律不可能流传100年都不改变，更何况它才
制定没多久，不可能这些语义标签对所有设计目标的适应。只是一定程度上的“通用”，我们的目标是让爬虫读懂重要的东西就
够了。
结论：不能因为有了HTML5标签就弃用了div，每个事物都有它的独有作用的。
节点元素标签因使用的地方不同，我将他们分为：节元素标签、文本元素标签、分组元素标签分开来讲解HTML5中新增加的语义
化标签和使用总结。
### header元素
header 元素代表“网页”或“section”的页眉。
通常包含h1-h6元素或hgroup，作为整个页面或者一个内容块的标题。也可以包裹一节的目录部分，一个搜索框，一个nav，或
者任何相关logo。
整个页面没有限制header元素的个数，可以拥有多个，可以为每个内容块增加一个header元素
        \<header\>
        \<hgroup\>
        \<h1\>网站标题\</h1\>
        \<h1\>网站副标题\</h1\>
        \</hgroup\>
        \</header\>
### header使用注意：
可以是“网页”或任意“section”的头部部分；
没有个数限制。
如果hgroup或h1-h6自己就能工作的很好，那就不要用header。
### footer元素
footer元素代表“网页”或“section”的页脚，通常含有该节的一些基本信息，譬如：作者，相关文档链接，版权资料。如果foot
er元素包含了整个节，那么它们就代表附录，索引，提拔，许可协议，标签，类别等一些其他类似信息。
footer的示例代码
        \<footer\>
        COPYRIGHT@小北
        \</footer\>
### footer使用注意：
可以是“网页”或任意“section”的底部部分；
没有个数限制，除了包裹的内容不一样，其他跟header类似。
### hgroup元素
hgroup元素代表“网页”或“section”的标题，当元素有多个层级时，该元素可以将h1到h6元素放在其内，譬如文章的主标题和副
标题的组合
hgroup示例代码
        \<hgroup\>
        \<h1\>这是一篇介绍HTML 5语义化标签和更简洁的结构\</h1\>
        \<h2\>HTML5\</h2\>
        \</hgroup\>
### hgroup使用注意：
如果只需要一个h1-h6标签就不用hgroup
如果有连续多个h1-h6标签就用hgroup
如果有连续多个标题和其他文章数据，h1-h6标签就用hgroup包住，和其他文章元数据一起放入header标签
### nav元素
nav元素代表页面的导航链接区域。用于定义页面的主要导航部分。
nav实例：
        \<nav\>
        \<ul\>
        \<li\>HTML5\</li\>
        \<li\>CSS3\</li\>
        \<li\>JavaScript\</li\>
        \</ul\>
        \</nav\>
但是我在有些时候却情不自禁的想用它，譬如：侧边栏上目录，面包屑导航，搜索样式，或者下一篇上一篇文章，但是事实上
规范上说nav只能用在页面主要导航部分上。页脚区域中的链接列表，虽然指向不同网站的不同区域，譬如服务条款，版权页等
，这些footer元素就能够用了。
### nav使用注意：
用在整个页面主要导航部分上，不合适就不要用nav元素；
### aside元素
aside元素被包含在article元素中作为主要内容的附属信息部分，其中的内容可以是与当前文章有关的相关资料、标签、名次
解释等。（特殊的section）
在article元素之外使用作为页面或站点全局的附属信息部分。最典型的是侧边栏，其中的内容可以是日志串连，其他组的导航
，甚至广告，这些内容相关的页面。
aside实例：
        \<article\>
        \<p\>内容\</p\>
        \<aside\>
        \<h1\>作者简介\</h1\>
        \<p\>小北，前端一枚\</p\>
        \</aside\>
        \</article\>
### aside使用总结：
aside在article内表示主要内容的附属信息，
在article之外则可做侧边栏，没有article与之对应，最好不用。
如果是广告，其他日志链接或者其他分类导航也可以用
### section元素
section元素代表文档中的“节”或“段”，“段”可以是指一篇文章里按照主题的分段；
“节”可以是指一个页面里的分组。
section通常还带标题，虽然html5中section会自动给标题h1-h6降级，但是最好手动给他们降级。如下：
section示例代码：
        \<section\>
        \<h1\>section是啥？\</h1\>
        \<article\>
        \<h2\>关于section\</h1\>
        \<p\>section的介绍\</p\>
        \<section\>
        \<h3\>关于其他\</h3\>
        \<p\>关于其他section的介绍\</p\>
        \</section\>
        \</article\>
        \</section\>
### section使用注意：
一张页面可以用section划分为简介、文章条目和联系信息。不过在文章内页，最好用article。section不是一般意义上的容器
元素，如果想作为样式展示和脚本的便利，可以用div。
表示文档中的节或者段；
article、nav、aside可以理解为特殊的section，所以如果可以用article、nav、aside就不要用section，没实际意义的就用d
iv
### article元素
article元素最容易跟section和div容易混淆，其实article代表一个在文档，页面或者网站中自成一体的内容，其目的是为了
让开发者独立开发或重用。譬如论坛的帖子，博客上的文章，一篇用户的评论，一个互动的widget小工具。（特殊的section）
除了它的内容，article会有一个标题（通常会在header里），会有一个footer页脚。我们举几个例子介绍一下article，好更
好区分article、section、div。
一篇简单文章的article示例代码:
        \<article\>
        \<h1\>一篇文章\</h1\>
        \<p\>文章内容..\</p\>
        \<footer\>
        \<p\>\<small\>版权：html5jscss网所属，作者：小北\</small\>\</p\>
        \</footer\>
        \</article\>
上例是最好简单的article标签使用情况，如果在article内部再嵌套article，那就代表内嵌的article是与它外部的内容有关
联的，如博客文章下面的评论，如下：
        \<article\>
        \<header\>
        \<h1\>一篇文章\</h1\>
        \<p\>\<time pubdate datetime="2012-10-03"\>2012/10/03\</time\>\</p\>
        \</header\>
        \<p\>文章内容..\</p\>
        \<article\>
        \<h2\>评论\</h2\>
        \<article\>
        \<header\>
        \<h3\>评论者: XXX\</h3\>
        \<p\>\<time pubdate datetime="2012-10-03T19:10-08:00"\>~1 hour ago\</time\>\</p\>
        \</header\>
        \<p\>哈哈哈\</p\>
        \</article\>
        \<article\>
        \<header\>
        \<h3\>评论者: XXX\</h3\>
        \<p\>\<time pubdate datetime="2012-10-03T19:10-08:00"\>~1 hour ago\</time\>\</p\>
        \</header\>
        \<p\>哈？哈？哈？\</p\>
        \</article\>
        \</article\>
        \</article\>
文章里的评论，一个article嵌套article来表示的实例
article内部嵌套article，有可能是评论或其他跟文章有关联的内容。那article内部嵌套section一般是什么情况呢。如下：
        \<article\>
        \<h1\>前端技术\</h1\>
        \<p\>前端技术有那些\</p\>
        \<section\>
        \<h2\>CSS\</h2\>
        \<p\>样式..\</p\>
        \</section\>
        \<section\>
        \<h2\>JS\</h2\>
        \<p\>脚本\</p\>
        \</section\>
        \</article\>
文章里的章节，一个article里的section实例
因为文章内section部分虽然也是独立的部分，但是它门只能算是组成整体的一部分，从属关系，article是大主体，section是
构成这个大主体的一部分。本网站的全部文章都是article嵌套一个个section章节，这样能让浏览器更容易区分各个章节所包
括的内容。

那section内部嵌套article又有哪些情况呢，如下
        \<section\>
        \<h1\>介绍: 网站制作成员配备\</h1\>
        \<article\>
        \<h2\>设计师\</h2\>
        \<p\>设计网页的...\</p\>
        \</article\>
        \<article\>
        \<h2\>程序员\</h2\>
        \<p\>后台写程序的..\</p\>
        \</article\>
        \<article\>
        \<h2\>前端工程师\</h2\>
        \<p\>给楼上两位打杂的..\</p\>
        \</article\>
        \</section\>
一个section里的article实例
设计师、程序员、前端工程师都是一个独立的整体，他们组成了网站制作基本配备，当然还有其他成员~~。设计师、程序员、
前端工程师就像article，是一个个独立的整体，而section将这些自成一体的article包裹，就组成了一个团体。

article和section和例子就例举这么多了，具体情况具体分析，不易深究。漏了divd，其实div就是只是想用来把元素组合或者
给它们加样式时使用。

### article使用注意：

自身独立的情况下：用article
是相关内容：用section
没有语义的：用div

### HTML5其他结构元素标签

HTML5节元素标签包括body article nav aside section header footer hgroup ，还有h1-h6 address。

address代表区块容器，必须是作为联系信息出现，邮编地址、邮件地址等等,一般出现在footer。
h1-h6因为hgroup，section和article的出现，h1-h6定义也发生了变化，允许一张页面出现多个h1。
HTML5语义化标签还有第二篇HTML 5的革新——语义化标签(二)。我们在构造语义化和结构化的标签时的选择也变得有些不慎重。
也就是说，我们不应该滥用超语义化的元素。