-   Mermaid能绘制哪些图？

-   饼状图：使用`pie`关键字，具体用法后文将详细介绍
-   流程图：使用`graph`关键字，具体用法后文将详细介绍
-   序列图：使用`sequenceDiagram`关键字
-   甘特图：使用`gantt`关键字
-   类图：使用`classDiagram`关键字
-   状态图：使用`stateDiagram`关键字
-   用户旅程图：使用`journey`关键字

  

-   实例：朱元璋家谱简图，圆圈代表皇帝。

```
graph LR
emperor((朱八八))-.子.->朱五四-.子.->朱四九-.子.->朱百六


朱雄英--长子-->朱标--长子-->emperor
emperor2((朱允炆))--次子-->朱标
朱樉--次子-->emperor
朱棡--三子-->emperor
emperor3((朱棣))--四子-->emperor
emperor4((朱高炽))--长子-->emperor3
```

![](https://pic1.zhimg.com/80/v2-d60c1e597b317815a15b1deeb12cb0cc_720w.jpg)

以上是概述，下面详细介绍饼状图和流程图的语法。其他图的语法可访问上文给出的项目地址，自行学习。（记得挂梯子）



## **饼状图**

  

-   在线渲染器：[Online FlowChart & Diagrams Editor](https://link.zhihu.com/?target=https%3A//mermaidjs.github.io/mermaid-live-editor/%23/edit/eyJjb2RlIjoicGllXG5cIkRvZ3NcIiA6IDQyLjk2XG5cIkNhdHNcIiA6IDUwLjA1XG5cIlJhdHNcIiA6IDEwLjAxIiwibWVybWFpZCI6eyJ0aGVtZSI6ImRlZmF1bHQifX0)（需要梯子）

  

-   语法——仅供参考，建议直接看实例

-   从`pie`关键字开始图表
-   然后使用`title`关键字及其在字符串中的值，为饼图赋予标题。（这是**可选的**）
-   数据部分

-   在`" "`内写上分区名。
-   分区名后使用`:`作为分隔符
-   分隔符后写上数值，最多支持2位小数——数据会以百分比的形式展示

  

-   实例

```text
pie
    title 为什么总是宅在家里？
    "喜欢宅" : 15
    "天气太热或太冷" : 20
    "穷" : 500
```

![](https://pic1.zhimg.com/80/v2-b1e0d29fc161651eb7c7420e5839e9b4_720w.jpg)

## **流程图**

-   在线渲染器：[Online FlowChart & Diagrams Editor](https://link.zhihu.com/?target=https%3A//mermaidjs.github.io/mermaid-live-editor/%23/edit/eyJjb2RlIjoiZ3JhcGggVERcbiAgICBBW0hhcmRdIC0tPnxUZXh0fCBCKFJvdW5kKVxuICAgIEIgLS0-IEN7RGVjaXNpb259XG4gICAgQyAtLT58T25lfCBEW1Jlc3VsdCAxXVxuICAgIEMgLS0-fFR3b3wgRVtSZXN1bHQgMl0iLCJtZXJtYWlkIjp7InRoZW1lIjoiZGVmYXVsdCJ9fQ)（需要挂梯子）

**实例**

```text
graph LR
    A[Start] --> B{Is it?};
    B -- Yes --> C[OK];
    C --> D[Rethink];
    D --> B;
    B -- No ----> E[End];
```

![](https://pic2.zhimg.com/80/v2-3be12faf90194a7fba93f379ba6f3ab1_720w.jpg)

**方向**：用于开头，声明流程图的方向。

-   `graph`或`graph TB`或`graph TD`：从上往下
-   `graph BT`：从下往上
-   `graph LR`：从左往右
-   `graph RL`：从右往左

**结点**

-   无名字的结点：直接写内容，此时结点边框为方形；节点内容不支持空格
-   有名字的结点：节点名后书写内容，内容左右有特定符号，结点边框由符号决定；节点内容可以有空格

> 下面的实例中，没有为graph指定方向，因此默认是从上往下的。但是由于各个结点之前没有箭头，所以他们都处于同一排。id1-id6是节点名，可随意定义。

```text
graph
    默认方形
    id1[方形]
    id2(圆边矩形)
    id3([体育场形])
    id4[[子程序形]]
    id5[(圆柱形)]
    id6((圆形))
```

![](https://pic2.zhimg.com/80/v2-73a3e2e292b4c1048b289a8a2fbf0541_720w.png)

```text
graph
	id1{菱形}
	id2{{六角形}}
	id3[/平行四边形/]
	id4[\反向平行四边形\]
	id5[/梯形\]
	id6[\反向梯形/]
```

![](https://pic2.zhimg.com/80/v2-bc009b5c5dd16bf28785206ee48c8a75_720w.png)

**连线样式**

-   实线箭头：分为无文本箭头和有文本箭头，有文本箭头有2种书写格式

```text
graph LR
a-->b--文本1-->c-->|文本2|d
```

![](https://pic1.zhimg.com/80/v2-27825da5a69b2902e2d4a0f1b2a7bae0_720w.jpg)

-   粗实线箭头：分为无文本箭头和有文本箭头

```text
graph LR
a==>b==文本==>c
```

![](https://pic3.zhimg.com/80/v2-b8fdb0fb0be7da93eb1244cd527f418e_720w.jpg)

-   虚线箭头：分为无文本箭头和有文本箭头

```text
graph LR
a-.->b-.文本.->c
```

![](https://pic4.zhimg.com/80/v2-81f70454562829e0e45aecb2365a7a63_720w.jpg)

-   无箭头线：即以上三种连线去掉箭头后的形式

```text
graph LR
a---b
b--文本1!---c
c---|文本2|d
d===e
e==文本3===f
f-.-g
g-.文本.-h
```

![](https://pic1.zhimg.com/80/v2-7cd50c7b552ed814b5fdadee5990c89c_720w.png)

-   其他连线：需要将`graph`关键字改为`flowchart`，除了新增加的连线形式外，上面三种线的渲染效果也会不同

```text
flowchart LR
    A o--o B
    B <--> C
    C x--x D
    
    旧连线 --文本--> 也会不同
```

![](https://pic3.zhimg.com/80/v2-3100c7052739f2cc179bb29d135d94ce_720w.jpg)

-   延长连线：增加相应字符即可，如下图中的B到E，连线中增加了一个`-`。字符可多次添加。

```text
graph LR
    A[Start] --> B{Is it?};
    B -->|Yes| C[OK];
    C --> D[Rethink];
    D --> B;
    B --->|No| E[End];
```

![](https://pic3.zhimg.com/80/v2-77c9feb3ad17b1c66cbf42621554a87e_720w.jpg)

**连线形式**

-   直链

```text
graph LR
   A -- text --> B -- text2 --> C
```

![](https://pic4.zhimg.com/80/v2-f18273d87cf1b3133cf8dd8a1c191f5f_720w.jpg)

-   多重链：可以使用`&`字符，或单个描述

```text
graph 
   a --> b & c--> d
   
   A & B--> C & D
   
    X --> M
    X --> N
    Y --> M
    Y --> N
```

![](https://pic1.zhimg.com/80/v2-cffe0ed82d60d3227047a809bf3ce03c_720w.jpg)

**其他**

-   子图：需要将`graph`关键字改为`flowchart`，在代码段的开始加入`subgraph`，尾部加入`end`

```text
flowchart TB
    c1-->a2
    subgraph one
    a1-->a2
    end
    subgraph two
    b1-->b2
    end
    subgraph three
    c1-->c2
    end
    one --> two
    three --> two
    two --> c2
```

![](https://pic2.zhimg.com/80/v2-d0e9793ba304a10f3cbc8055261157f1_720w.jpg)

-   注释：在行首加入`%%`即可。

```text
graph LR
%%这是一条注释，在渲染图中不可见
    A[Hard edge] -->|Link text| B(Round edge)
    B --> C{Decision}
    C -->|One| D[Result one]
    C -->|Two| E[Result two]
```

![](https://pic1.zhimg.com/80/v2-a7af018b57b210d0c772f3beac98ad10_720w.jpg)