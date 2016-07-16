#Button基本使用方法

##简单使用过程
+ 首先，添加Button控件到XML布局文件中，也可通过程序添加。
+ 在布局文件中设置按钮的一些属性，如位置，宽高，按钮上的字，颜色等。
+ 设置按钮的id号，这是按钮唯一的名字，用于程序获取当前按钮。
+ 在Activity中定义变量、实例化定义的按钮。
+ 给定义的按钮设置按钮监听事件。

### 1 布局中定义
```
<Button
    android:id="@+id/tech_btn"
    android:layout_width="200dp"
    android:layout_height="50dp"
    android:background="@color/colorAccent"
    android:text="这是一个按钮"
    android:textColor="#ffffff"
    android:textSize="10pt">
</Button>
```
### 2 Activity中获取Button

```
public class MainActivity extends AppCompatActivity {
    /*声明按钮变量*/
    private Button main_tech_btn;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        /*按钮实例化*/
        main_tech_btn = (Button) findViewById(R.id.tech_btn);
    }
}
```
### 3 Butoon设置监听事件
+ 方法一：可以写一个内部类，实现OnClickListener接口，在这个类中实现onClick方法，方法里面写在按钮点击时想做的具体工作。将这个内部类的对象传入按钮的setOnClickListener方法中，即完成监听器对象和按钮的绑定（在事件源Button上注册了事件监听器），这时候只要按钮被点击，那么监听器对象的onClick方法就会被调用。
```
/*按钮实例化*/
main_tech_btn = (Button) findViewById(R.id.tech_btn);
main_tech_btn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                            /*点击按钮执行的方法体代码*/
                            System.out.println("方法一：点击了按钮！");
                        }
        });
```
+ 方法二：通过onClick属性，通过这个属性设置处理点击事件的方法名，在Activity中实现这个方法。
```
1.布局中定义监听方法
<Button
        android:layout_width="200dp"
        android:onClick="tech_btnClick"
        android:layout_height="50dp"
        android:background="@color/colorAccent"
        android:text="这是一个按钮"
        android:textColor="#ffffff"
        android:textSize="10pt">
</Button>
2.实现监听事件
public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
    }
    /*  需要注意的是这个方法必须符合三个条件：
        1.public
        2.返回void
        3.只有一个参数View，这个View就是被点击的这个控件。
    */
    public void tech_btnClick(View view) {
        /*点击按钮执行的方法体代码*/
        System.out.println("方法二：点击了按钮！");
    }
}
```
+ 方法三：方法一的简写形式，在按钮只设置监听事件时使用方便。如果当前Activity中多次使用，需按照第一种方式定义声明。
```
定义布局中的按钮控件和方法一一样定义ID属性。

public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        findViewById(R.id.tech_btn).setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                /*点击按钮执行的方法体代码*/
                System.out.println("方法三：点击了按钮！");
            }
        });
    }
}
```

