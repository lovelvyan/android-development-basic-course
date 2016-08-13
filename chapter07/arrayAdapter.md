# ArrayAdapter的基本使用方法

ArrayAdapter是BaseAdapter的派生类，在BaseAdapter的基础上，添加了一项重大的功能:可以直接使用泛型构造。默认的ArrayAdapter期望接受的样式文件里只含有一个textview，然后它把接受到的数据toString后（即调用数据对象的toString方法）展示在textview里。

###构造方法

+ ArrayAdapter(Context context, int resource)
+ ArrayAdapter(Context context, int resource, int textViewResourceId)
+ ArrayAdapter(Context context, int resource, T[] objects)
+ ArrayAdapter(Context context, int resource, int textViewResourceId, T[] objects)
+ ArrayAdapter(Context context, int resource, List<T> objects)
+ ArrayAdapter(Context context, int resource, int textViewResourceId, List<T> objects)

###使用方式一（基本使用）：
>使用构造方法 ArrayAdapter(Context context, int resource, T[] objects)
```
   public class ArrayAdapterActivity extends ListActivity {
        @Override
        public void onCreate(Bundle savedInstanceState) {
            super.onCreate(savedInstanceState);
            //列表项的数据
            String[] strArray = {"one","two","three","four","five"};
            ArrayAdapter<String> adapter = new ArrayAdapter<String>(this,android.R.layout.simple_expandable_list_item_1,strArray);
            setListAdapter(adapter);
        }
    }
```
###使用方式二（简单数据简单布局）：

>使用构造方法 ArrayAdapter(Context context, int resource, T[] objects)

```
     public class ArrayAdapterActivity extends Activity {

           private ListView listView;

           @Override
           public void onCreate(Bundle savedInstanceState){
               super.onCreate(savedInstanceState);

               listView = new ListView(this);//当然此步骤也可以自定义ListView布局

               listView.setAdapter(new ArrayAdapter<String>(this, android.R.layout.simple_expandable_list_item_1,getData()));
               setContentView(listView);
           }

           private List<String> getData(){

               List<String> data = new ArrayList<String>();

               data.add("one");
               data.add("two");
               data.add("three");
               data.add("four");
               data.add("five");

               return data;
           }
       }
```
###使用方式三（简单数据复杂布局）：

>使用构造方法 ArrayAdapter(Context context, int resource, int textViewResourceId, List<T> objects)

```
     public class ArrayAdapterActivity extends Activity {

           private ListView listView;

           @Override
           public void onCreate(Bundle savedInstanceState){
               super.onCreate(savedInstanceState);

               listView = new ListView(this);//当然此步骤也可以自定义ListView布局

               ArrayAdapter<String> adapter = new ArrayAdapter<String>(this, R.layout.user_list_item, R.id.user_list_item_textview,getData());

               setContentView(listView);
           }

           private List<String> getData(){

               List<String> data = new ArrayList<String>();

               data.add("one");
               data.add("two");
               data.add("three");
               data.add("four");
               data.add("five");

               return data;
           }
       }
```
> user_list_item.xml布局文件
```
    <?xml version="1.0" encoding="utf-8"?>
    <LinearLayout  xmlns:android="http://schemas.android.com/apk/res/android"
        android:layout_width="fill_parent"
        android:layout_height="wrap_content">
        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:id="@+id/user_list_item_textview"
            android:text="TextView">
        </TextView>
        <Button
            android:text="button"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content">
        </Button>
    </LinearLayout>
  ```
###使用方式四（数据复杂样式复杂使用）：
```
    public class ArrayAdapterActivity extends Activity {

        @Override
            protected void onCreate(Bundle savedInstanceState) {
                super.onCreate(savedInstanceState);
                setContentView(R.layout.activity_main);

                ListView listView = (ListView) this.findViewById(R.id.list);

                UserAdapter adapter = new UserAdapter(this, R.layout.list_item);

                adapter.add(new User(10, "周周", "男"));

                adapter.add(new User(10, "莉莉", "女"));

                listView.setAdapter(adapter);

            }
    }

    class UserAdapter extends ArrayAdapter<User> {
        private int mResourceId;

        public UserAdapter(Context context, int textViewResourceId) {
            super(context, textViewResourceId);
            this.mResourceId = textViewResourceId;
        }

        @Override
        public View getView(int position, View convertView, ViewGroup parent) {
            User user = getItem(position);
            LayoutInflater inflater = getLayoutInflater();
            View view = inflater.inflate(mResourceId, null);
            TextView nameText = (TextView) view.findViewById(R.id.name);
            TextView ageText = (TextView) view.findViewById(R.id.age);
            TextView sexText = (TextView) view.findViewById(R.id.sex);

            nameText.setText(user.getName());
            ageText.setText(user.getAge());
            sexText.setText(user.getSex());

            return view;
        }
    }

    class User {
        private int mAge;
        private String mName;
        private String mSex;

        public User(int age, String name, String sex) {
            this.mAge = age;
            this.mName = name;
            this.mSex = sex;
        }

        public String getName() {
            return this.mName;
        }

        public String getAge() {
            return this.mAge + "";
        }

        public String getSex() {
            return this.mSex;
        }
    }

```