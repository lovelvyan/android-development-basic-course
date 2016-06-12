#布局的常用属性

## 1 单个控件常用属性
```
android:id —— 为控件指定相应的ID
android:text —— 指定控件当中显示的文字，需要注意的是，这里尽量使用strings.xml文件当中的字符串
android:grivity —— 指定控件的基本位置，比如说居中，居右等位置
android:textSize —— 指定控件当中字体的大小
android:background —— 指定该控件所使用的背景色,RGB命名法
android:width —— 指定控件的宽度
android:height —— 指定控件的高度
android:padding —— 指定控件的内边距，也就是说控件当中的内容
android:sigleLine —— 如果设置为真的话，则将控件的内容在同一行当中进行显示
```
## 2 相对布局常用属性
```
android:layout_above 将该控件的底部至于给定ID的控件之上
android:layout_below 将该控件的顶部至于给定ID的控件之下
android:layout_toLeftOf 将该控件的右边缘和给定ID的控件的左边缘对齐
android:layout_toRightOf 将该控件的左边缘和给定ID的控件的右边缘对齐

android:layout_alignBaseline 该控件的baseline和给定ID的控件的baseline对齐
android:layout_alignBottom 将该控件的底部边缘与给定ID控件的底部边缘对齐
android:layout_alignLeft 将该控件的左边缘与给定ID控件的左边缘对齐
android:layout_alignRight 将该控件的右边缘与给定ID控件的右边缘对齐
android:layout_alignTop 将给定控件的顶部边缘与给定ID控件的顶部对齐

android:alignParentBottom 如果该值为true，则将该控件的底部和父控件的底部对齐
android:layout_alignParentLeft 如果该值为true，则将该控件的左边与父控件的左边对齐
android:layout_alignParentRight 如果该值为true，则将该控件的右边与父控件的右边对齐
android:layout_alignParentTop 如果该值为true，则将空间的顶部与父控件的顶部对齐

android:layout_centerHorizontal 如果值为真，该控件将被至于水平方向的中央
android:layout_centerInParent 如果值为真，该控件将被至于父控件水平方向和垂直方向的中央
android:layout_centerVertical 如果值为真，该控件将被至于垂直方向的中央
```
## 3 其他常用属性

+ EditText的android:hint
>设置EditText为空时输入框内的提示信息。

+ android:gravity
> android:gravity属性是对该view 内容的限定．比如一个button 上面的text.  你可以设置该text 在view的靠左，靠右等位置．以button为例，android:gravity="right"则button上面的文字靠右

+ android:layout_gravity
> android:layout_gravity是用来设置该view相对与起父view 的位置．比如一个button 在linearlayout里，你想把该button放在靠左、靠右等位置就可以通过该属性设置．以button为例，android:layout_gravity="right" 则button靠右。

+ android:scrollHorizontally
> 设置文本超出TextView的宽度的情况下，是否出现横拉条。

+ android:layout_alignParentRight
> 使当前控件的右端和父控件的右端对齐。这里属性值只能为true或false，默认false。

+ android:scaleType
> android:scaleType是控制图片如何resized/moved来匹对ImageView的size。ImageView.ScaleType / android:scaleType值的意义区别：
```
CENTER /center  按图片的原来size居中显示，当图片长/宽超过View的长/宽，则截取图片的居中部分显示。

CENTER_CROP / centerCrop  按比例扩大图片的size居中显示，使得图片长(宽)等于或大于View的长(宽)。

CENTER_INSIDE / centerInside  将图片的内容完整居中显示，通过按比例缩小或原来的size使得图片长/宽等于或小于View的长/宽。

FIT_CENTER / fitCenter  把图片按比例扩大/缩小到View的宽度，居中显示。

FIT_END / fitEnd   把图片按比例扩大/缩小到View的宽度，显示在View的下部分位置。

FIT_START / fitStart  把图片按比例扩大/缩小到View的宽度，显示在View的上部分位置。

FIT_XY / fitXY  把图片不按比例扩大/缩小到View的大小显示。

MATRIX / matrix 用矩阵来绘制，动态缩小放大图片来显示。

要注意一点，Drawable文件夹里面的图片命名是不能大写的。
```

+ Android:width
> 其实是定义控件上面的文本(TextView) 的宽度，当然这个宽度也是和 android:layout_width 配合起来作用的，如果 android:layout_width="fill_parent" 的话，那么设置 android:width 是没有意义的。

+ android:layout_width
> 其实是可以实现 android:width 的效果的，我觉得这应该是为什么在 android 实例中看不到有人用 android:width 的原因吧。

```
两者的区别：
android:width 的值，一般是 "100dp" 这样的数值。
android:layout_width 的值，一般是"fill_parent","wrap_content","match_parent"。当然，它也可以像前者一样，设置数值的。
```