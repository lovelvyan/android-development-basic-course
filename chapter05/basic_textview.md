#TextView的基本使用方法

##简单使用过程
>TextView类似一般UI中的Label等控件，只是为了单纯的显示一行或者多行文本。

+ 了解在Android中如何使用TextView控件
+ 掌握在Android中TextView控件的重要属性


### 1 布局中定义
```
<TextView
    android:id="@+id/tv"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:textColor="#FF0000"
    android:textSize="15pt"
    android:text="这里是要展示的文本内容"
    android:singleLine="true">
</TextView>
```
+ textColor 属性表示文字的颜色。
+ textSize 属性表示文字的大小，单位一般为pt。
+ text 属性表示文本的具体内容。
+ singleLine 属性表示是否文本只显示一行，默认为false，如果为true则只会显示一行文字。

### 2 Activity中获取TextView

```
public class MainActivity extends AppCompatActivity {
    /*声明按钮变量*/
    private TextView main_tech_textview;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        /*TextView实例化*/
        main_tech_textview = (Button) findViewById(R.id.tv);
    }
}
```
### 3 Activity中动态设置TextView显示内容
```
public class MainActivity extends AppCompatActivity {
    /*声明按钮变量*/
    private TextView main_tech_textview;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        /*TextView实例化*/
        main_tech_textview = (Button) findViewById(R.id.tv);
        main_tech_textview.setText("显示到手机界面上！");
    }
}
```