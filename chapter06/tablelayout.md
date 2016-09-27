TableLayout(表格布局)
====================
>是一个ViewGroup以表格显示它的子视图（view）元素，即行和列标识一个视图的位置。一个TableLayout 由许多的TableRow 组成，每个TableRow 都会定义一行（ row ，你可以定义其它的子对象，这在下面会解释到）。TableLayout 容器不会显示row 、cloumns 或cell 的边框线。每个 row 拥有0个或多个的cell ，每个cell 拥有一个View 对象。

## 用表格布局需要知道以下几点：
+ android:shrinkColumns：setShrinkAllColumns(boolean)，作用是设置表格的列是否收缩（列编号从0开始，下同），多列用逗号隔开（下同），如android:shrinkColumns="0,1,2"，即表格的第1、2、3列的内容是收缩的以适合屏幕，不会挤出屏幕。
+ android:collapseColumns：setColumnCollapsed(int,boolean)，作用是设置表格的列是否隐藏。
+ android:stretchColumns：setStretchAllColumns(boolean)，作用是设置表格的列是否拉伸。

