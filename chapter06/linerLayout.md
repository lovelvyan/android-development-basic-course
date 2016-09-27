# LinearLayout线性布局


LinearLayout是线性布局控件，它包含的子控件将以横向或竖向的方式排列，按照相对位置来排列所有的widgets或者其他的containers,超过边界时，某些控件将缺失或消失。因此一个垂直列表的每一行只会有一个widget或者是container，而不管他们有多宽，而一个水平列表将会只有一个行高（高度为最高子控件的高度加上边框高度）。LinearLayout保持其所包含的widget或者是container之间的间隔以及互相对齐（相对一个控件的右对齐、中间对齐或者左对齐）。

##xml属性

+ android:orientation：设置它内容的对其方向（横向/竖向）。

+ android:gravity：指定如何在该对象中放置此对象的内容（x/y坐标值）。
<blockquote>
<p>gravity 这个英文单词是重心的意思，在这里就表示停靠位置的意思。

 **android:layout_gravity 和 android:gravity 的区别**

 从名字上可以看到，android:gravity是对元素本身说的，元素本身的文本显示在什么地方靠着换个属性设置，不过不设置默认是在左侧的。android:layout_gravity是相对与它的父元素说的，说明元素显示在父元素的什么位置。

 比如说button：android:layout_gravity 表示按钮在界面上的位置。 android:gravity表示button上的字在button上的位置。

 这两个属性可选的值有：top、bottom、left、right、center_vertical、fill_vertical、center_horizontal、fill_horizontal、center、fill、clip_vertical。
 而且这些属性是可以多选的，用“|”分开。默认这个的值是：Gravity.LEFT
</p>
</blockquote>

+ android:baselineAligned：是否允许用户调整它内容的基线。

+ android:baselineAlignedChildIndex：当一个线性布局与另一个布局是按基线对齐的一部分，它可以指定其内容的基线对齐方式。

##layout_weight特殊说明
与其它线性布局属性不同，其它线性的属性应用在布局视图本身，而这个属性是应用在它的子控件上的。当屏幕上有足够空间来正确的展示所有控件的时候，这个权值技巧很有效。那就是说，当空间很紧的时候，权值属性可能会被其它因素覆盖，比如视图裁剪或者在TextView下试图不环绕文本。


##对齐方式gravity取值
+ top：不改变大小，位置置于容器的顶部
+ bottom：不改变大小，位置置于容器的底部
+ left：不改变大小，位置置于容器的左边
+ right：不改变大小，位置置于容器的右边
+ center_vertical：不改变大小，位置置于容器的纵向中央部分
+ center_horizontal：不改变大小，位置置于容器的横向中央部分
+ center：不改变大小，位置置于容器的横向和纵向的中央部分
+ fill_vertical：可能的话，纵向延伸可以填满容器
+ fiil_horizontal：可能的话，横向延伸可以填满容器
+ fiil：可能的话，纵向和横向延伸填满容器

