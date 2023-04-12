[25](https://www.bilibili.com/video/BV1fe411N7cJ?p=15&vd_source=74872e41274c3d29495fcb0f1ba131bd)

[01:33](https://www.bilibili.com/video/BV1fe411N7cJ?p=15&vd_source=74872e41274c3d29495fcb0f1ba131bd#t=93.267085)
通过SUMIFS函数，得到这样的一个汇总结果。

[02:34](https://www.bilibili.com/video/BV1fe411N7cJ?p=15&vd_source=74872e41274c3d29495fcb0f1ba131bd#t=154.296959)
分列修复格式不对的身份证号。

[03:13](https://www.bilibili.com/video/BV1fe411N7cJ?p=15&vd_source=74872e41274c3d29495fcb0f1ba131bd#t=193.467971)
插入函数→文本类函数UPPER，变大写字母。lower，变小写。proper，首字母大写。[04:22](https://www.bilibili.com/video/BV1fe411N7cJ?p=15&vd_source=74872e41274c3d29495fcb0f1ba131bd#t=262.693974)智能工具箱：文本处理→格式转换→大小写→各种大小写选项。

[04:55](https://www.bilibili.com/video/BV1fe411N7cJ?p=15&vd_source=74872e41274c3d29495fcb0f1ba131bd#t=295.750739)
left函数，从某单元格从左边开始取指定个字符。right、mid同理。[05:35](https://www.bilibili.com/video/BV1fe411N7cJ?p=15&vd_source=74872e41274c3d29495fcb0f1ba131bd#t=335.474619)智能工具箱：截取文本。

[05:53](https://www.bilibili.com/video/BV1fe411N7cJ?p=15&vd_source=74872e41274c3d29495fcb0f1ba131bd#t=353.971621)
round函数，保留指定位数小数点后四舍五入。

[06:55](https://www.bilibili.com/video/BV1fe411N7cJ?p=15&vd_source=74872e41274c3d29495fcb0f1ba131bd#t=415.746637)
IF函数。[07:36](https://www.bilibili.com/video/BV1fe411N7cJ?p=15&vd_source=74872e41274c3d29495fcb0f1ba131bd#t=456.067402)常量是中文、英文之类的，需要用双引号给引出来。（双引号打全）[08:29](https://www.bilibili.com/video/BV1fe411N7cJ?p=15&vd_source=74872e41274c3d29495fcb0f1ba131bd#t=509.944182)文本型数字和数值型数字不一样。（[[WPS操作技巧/一只阳台上的猫（B站）/分列-单元格内容拆分与整理#^hn7idz|反链]]）[08:53](https://www.bilibili.com/video/BV1fe411N7cJ?p=15&vd_source=74872e41274c3d29495fcb0f1ba131bd#t=533.841627)如何转换文本型数字，开始→格式→转换成数值。

[09:38](https://www.bilibili.com/video/BV1fe411N7cJ?p=15&vd_source=74872e41274c3d29495fcb0f1ba131bd#t=578.267815)
分类汇总。

[10:34](https://www.bilibili.com/video/BV1fe411N7cJ?p=15&vd_source=74872e41274c3d29495fcb0f1ba131bd#t=634.760512)
ALT→D→L，数据有效性→序列→来源=月份。月份是提前设置好的名称。公式→名称管理器→月份→引用位置=参数表XX。

[11:02](https://www.bilibili.com/video/BV1fe411N7cJ?p=15&vd_source=74872e41274c3d29495fcb0f1ba131bd#t=662.776112)
定义的名称是在单独做的参数表。（[[二级有效性与动态选项设置]]）

[11:36](https://www.bilibili.com/video/BV1fe411N7cJ?p=15&vd_source=74872e41274c3d29495fcb0f1ba131bd#t=696.295246)
原始数据的下拉列表资料也是从参数表来的。

[12:02](https://www.bilibili.com/video/BV1fe411N7cJ?p=15&vd_source=74872e41274c3d29495fcb0f1ba131bd#t=722.374725)
颜色的变化通过条件格式来管。开始→条件格式→管理规则→[12:27](https://www.bilibili.com/video/BV1fe411N7cJ?p=15&vd_source=74872e41274c3d29495fcb0f1ba131bd#t=747.285824)

[13:08](https://www.bilibili.com/video/BV1fe411N7cJ?p=15&vd_source=74872e41274c3d29495fcb0f1ba131bd#t=788.505193)
SUMIFS函数（多条件求和函数），和[[WPS操作技巧/一只阳台上的猫（B站）/修复和清洗不标准数据源#^zq9msn|数据透视表]]有异曲同工之妙。

[13:44](https://www.bilibili.com/video/BV1fe411N7cJ?p=15&vd_source=74872e41274c3d29495fcb0f1ba131bd#t=824.501584)
SUMIFS函数怎么写。[14:38](https://www.bilibili.com/video/BV1fe411N7cJ?p=15&vd_source=74872e41274c3d29495fcb0f1ba131bd#t=878.418066)MONTH公式提取“月”。[15:23](https://www.bilibili.com/video/BV1fe411N7cJ?p=15&vd_source=74872e41274c3d29495fcb0f1ba131bd#t=923.314804)示例。[19:12](https://www.bilibili.com/video/BV1fe411N7cJ?p=15&vd_source=74872e41274c3d29495fcb0f1ba131bd#t=1152.695996)锁行锁列（F4锁定）。[21:46](https://www.bilibili.com/video/BV1fe411N7cJ?p=15&vd_source=74872e41274c3d29495fcb0f1ba131bd#t=1306.394343)Ctrl+R、Ctrl+D复制。