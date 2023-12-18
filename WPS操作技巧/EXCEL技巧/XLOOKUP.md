XLOOKUP函数的基本结构是：

**=XLOOKUP(lookup_value,lookup_array,return_array,[if_not_found],[match_mode],[search_mode])**

翻译成大白话就是：

**=XLOOKUP(查找值,查找范围,结果范围,[找不到时显示的值],[匹配方式],[查询模式])**

在这六个参数中，前三个是必须的，后面三个根据自己的需要选择使用。

以下通过七个方面的应用示例帮大家了解这个函数，内容比较多，分两次发布，今天先看前三个方面的例子。

## **示例1：常规匹配（对标LOOKUP）**  

按照姓名匹配入职日期，公式为=XLOOKUP(G2,B:B,C:C)。

![](https://pic1.zhimg.com/80/v2-73c39e1614ffad336cce05d39c99185c_1440w.webp)

这种用法和LOOKUP的使用结构非常像，但是有本质的区别。LOOKUP函数要求查找范围必须升序排列，而XLOOKUP则无此限制。就这个问题使用LOOKUP的结果如图所示：

![](https://pic2.zhimg.com/80/v2-3f183e03053721006e755093ac051319_1440w.webp)

再比如按姓名匹配员工ID，这在VLOOKUP的用法中叫反向查找，XLOOKUP还是一样的用法，公式为=XLOOKUP(G2,B:B,A:A)。

![](https://pic2.zhimg.com/80/v2-ceca786192512d285d426ce2a631f6c1_1440w.webp)

这是给大家介绍的第一种用法，**XLOOKUP（查找值，查找范围，结果范围）**，没有顺序要求，没有方向要求，这体验一下子就超过了VLOOKUP和LOOKUP。

## **示例2：一次查找多个值（数组用法）**

如果XLOOKUP的第一参数选择一个单元格区域，可以对应得到多个结果。在Excel365中更容易看到这种数组自动扩展的效果。

![动图封面](https://pic2.zhimg.com/v2-6c5d0f23db9b8cffddb0ae1058e58ef1_b.jpg)

在此提醒那些用VLOOKUP时，第一参数习惯选一列的朋友，如果你这样用XLOOKUP的话，电脑能卡死！

XLOOKUP的这种特性非常重要，比如要统计某几个人的岗位津贴总和，就可以直接用公式=SUM(XLOOKUP(F2:F5,A:A,D:D))得到结果，这个公式非365用户需要按**Ctrl+Shift+Enter**三键。

![](https://pic1.zhimg.com/80/v2-4ac8ab1e82b8f0bb5788a3dcebb6dc84_1440w.webp)

## **示例3：第四参数的妙用**

来看这个例子，按照姓名找对应的成绩，当出现数据源中不存在的姓名是，结果为#N/A。

![](https://pic2.zhimg.com/80/v2-24e76a3619b49049a727f7507ca6407d_1440w.webp)

通常遇到这种情况我们的第一反应是外面嵌套一个IFERROR函数，实际上XLOOKUP的第四参数就可以取代IFERROR函数了。

公式修改为=XLOOKUP(D2,A:A,B:B,"姓名有误")。

![](https://pic2.zhimg.com/80/v2-6ca32af7fa751ab8abb59556881aea65_1440w.webp)

对于这个参数，我想大家都很容易掌握，毕竟使用一个参数就能少嵌套一个函数，这是非常好的体验。

##   
**示例4：多样的匹配方式**

XLOOKUP提供了四种匹配方式。

![](https://pic3.zhimg.com/80/v2-83a028c3f0399f945bc876736dc044ba_1440w.webp)

从函数自带的提示不难看出四种匹配方式的意思。0或者省略是精确匹配，之前的例子都是这种方式。-1是精确匹配或下一个较小的项，例如按照成绩匹配等级，可以使用公式=XLOOKUP(B2,F:F,G:G,"",-1)。

![](https://pic4.zhimg.com/80/v2-2a5281a5af7a2a03250de0997a3305a3_1440w.webp)

这个公式的意思是在F列中找52，找不到的时候就找小于52的一个值，也就是0，最后得到的结果就是0所对应的等级。如果就这样看的话，似乎用LOOKUP更简单。

![](https://pic4.zhimg.com/80/v2-9ccc674add6856801cb4f8fb5ec90903_1440w.webp)

但是LOOKUP要求查找范围升序，假如数据变成这样，结果就全错了。

![](https://pic1.zhimg.com/80/v2-ff5304e6dc86298d1138ac07a8a242c8_1440w.webp)

可以看出XLOOKUP函数完全不受顺序的影响，LOOKUP则多了一些限制。

如果匹配方式用1的话则正好相反，找不到要找的值时，则会找较大的一个值。例如公式=XLOOKUP(B2,F:F,G:G,"",1)就会得到这样的结果。

![](https://pic2.zhimg.com/80/v2-587af0bc2a9106a2ed20e9de9390488d_1440w.webp)

从这个例子可以看出，在做区间匹配时，-1对应下限值，1对应上限值。

## **示例5：使用通配符**

有时候在匹配数据时会用到通配符，例如根据单位检查匹配对应的业务人员，公式为=XLOOKUP("*"&D2&"*",A:A,B:B,"无对应人员",2)。

![](https://pic3.zhimg.com/80/v2-0c61ddcbac701430cc6b881e772be60a_1440w.webp)

XLOOKUP函数默认不支持通配符的，如果要用通配符，第五参数必须填2，这也是XLOOKUP函数的一个特殊之处。

## **示例6：多种查询方式**

查询方式和匹配方式是不一样的概念，XLOOKUP提供了四种查询方式：

![](https://pic1.zhimg.com/80/v2-0bca01538f5bb802045f011553aef4dc_1440w.webp)

查询方式1是从上向下，默认的也是这种方式。查询方式-1是从下向上，如果要查找的值是唯一的，那么这两种方式得到的结果是一样的，但是当要查找的值有多个的时，两种方式的区别就出现了。

例如公式=XLOOKUP(E2,B:B,C:C,"",0,1)得到的就是每个人的首日销量。

![](https://pic2.zhimg.com/80/v2-38b696c65cc0d967caaf3bc9b91763c1_1440w.webp)

而公式=XLOOKUP(E2,B:B,C:C,"",0,-1)得到的则是每个人的末日销量。

![](https://pic3.zhimg.com/80/v2-85e374cf0b99ea8889beea5f7660a19e_1440w.webp)

这两种查询方式都是遍历法原理，只是查询方向的区别，而查询方式2和-2，则用的是二分法原理，区别就是二分法的时候默认升序还是降序。关于遍历法和二分法原理，理论性较强，可以参考之前的这篇教程，本文就不赘述了。

[【Excel函数教程】Excel公式中的二分法原理揭秘​mp.weixin.qq.com/s?__biz=MzI1MTM2NzY1NQ==&mid=2247497782&idx=1&sn=83ca2ad00ea0fcc8a06de40164d96c75&chksm=e9f6a1bede8128a86d545bb4d6813ab8f63d66d838bc9e12b98d9d3218ccfe083b0e6408814b&scene=21#wechat_redirect![](https://pic4.zhimg.com/v2-c45d257c8cca03e5b56c169cf31a242f_180x120.jpg)](https://link.zhihu.com/?target=http%3A//mp.weixin.qq.com/s%3F__biz%3DMzI1MTM2NzY1NQ%3D%3D%26mid%3D2247497782%26idx%3D1%26sn%3D83ca2ad00ea0fcc8a06de40164d96c75%26chksm%3De9f6a1bede8128a86d545bb4d6813ab8f63d66d838bc9e12b98d9d3218ccfe083b0e6408814b%26scene%3D21%23wechat_redirect)

## **示例7：横向匹配和多列匹配**

横向查找之前多是用HLOOKUP函数来解决，现在也可以用XLOOKUP，只要查找范围和结果范围是横向的就行。例如公式=XLOOKUP(B6,1:1,2:2)就是横向查找的结果。  

![](https://pic3.zhimg.com/80/v2-304244d0ea90bf3c62924298518575a2_1440w.webp)

在没有XLOOKUP的时候，我们使用VLOOKUP做多列匹配往往要用到COLUMN函数，现在就方便了，只要将结果区域选择多列即可，注意这种用法只能对连续的多列匹配适用。

![动图](https://pic3.zhimg.com/v2-9a4a12a6420f51791a9397bd549ab29e_b.webp)

以上就是XLOOKUP函数的基本用法，功能确实很多也很强大，希望有条件的伙伴能够赶紧练起来。