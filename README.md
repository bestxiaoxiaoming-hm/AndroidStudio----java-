# 项目简介

首先此项目是本人学校安卓开发的一次作业，用Android Studio开发一个简单的计算器，这个计算器正常的功能为带括号的加减乘除多项式计算！

## ”activity_main.xml“展示部分

Android Studio开发当中的布局是".XML"的文件格式，普通的初学者也许会使用默认的Constraint Layout布局方式来进行布局，但这里使用的是grid layout（网格布局）很简单的解释就是给定了"行"和"列"的数量，会组成一个网格，在网格里添加控件就可以了！（想深入了解的百度查找，会有更加详细的介绍）

下面是grid layout的一些使用属性，应该很容易看懂！

```xml
<GridLayout
    android:id="@+id/gridlayout"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="#F0F0F0"
    android:alignmentMode="alignBounds"
    android:rowCount="9"
    android:columnCount="4"
    android:orientation="horizontal"

    tools:context=".MainActivity"
    tools:ignore="GridLayout">
   <!-- orientation="horizontal"水平布局
                    "vertical"   垂直布局
                     *rowCount   最大行数
                     *columnCount 最大列数
                     *alignmentMode 对齐模式-->
</GridLayout>
```

下面是TextView,Button,EditText的属性使用！一共使用了19个按钮（为了将每一行平分配位置，所以加入了权重属性，当权重相同时，每个按钮的权力一样，自然不会有不听话的按钮长那么一点或者宽那么一点！）除了最后一个按钮" = "需要将行权重设置为‘ 2 ’以外（让它占满两格！），其余全可以copy！

```xml
<EditText
     android:id="@+id/edit"
     android:layout_gravity="center"
     android:text=" "
     android:textSize="35dp"
     android:layout_columnSpan="4"
     android:layout_rowWeight="3"
     android:layout_columnWeight="1" />
 <TextView
     android:id="@+id/view"
     android:layout_gravity="center"
     android:text="0"
     android:textSize="45dp"
     android:layout_columnSpan="4"
     android:layout_rowWeight="3"
     android:layout_columnWeight="1"/>
<Button
    android:id="@+id/add"
    android:layout_margin="1dp"
    android:background="#FAFAFA"
    android:textColor="#7C7D82"
    android:text="+"
    android:textSize="24dp"
    android:layout_columnWeight="1"
    android:layout_rowWeight="1"
    />
```

为了防止最后一个按钮有人不知道“行“权重如何改为2，所以附上最后一个等号按钮的属性！

```xml
<Button
    android:id="@+id/equal"
    android:layout_margin="1dp"
    android:background="#FAFAFA"
    android:textColor="#7C7D82"
    android:text="="
    android:textSize="24dp"
    android:layout_columnSpan="2"
    android:layout_columnWeight="1"
    android:layout_rowWeight="1"
    />
```

接下来展示activity_main.xml完整部分！

```xml
<?xml version="1.0" encoding="utf-8"?>
<GridLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/gridlayout"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="#F0F0F0"
    android:alignmentMode="alignBounds"
    android:rowCount="9"
    android:columnCount="4"
    android:orientation="horizontal"

    tools:context=".MainActivity"
    tools:ignore="GridLayout">
   <!-- orientation="horizontal"水平布局
                     vertical   垂直布局
                     rowCount   最大行数
                     columnCount 最大列数
                     alignmentMode 对齐模式-->
    <EditText
    android:id="@+id/edit"
    android:layout_gravity="center"
    android:text=" "
    android:textSize="35dp"
    android:layout_columnSpan="4"
    android:layout_rowWeight="3"
    android:layout_columnWeight="1" />
   <TextView
       android:id="@+id/view"
       android:layout_gravity="center"
       android:text="0"
       android:textSize="45dp"
       android:layout_columnSpan="4"
       android:layout_rowWeight="3"
       android:layout_columnWeight="1"/>
   <Button
       android:id="@+id/add"
       android:layout_margin="1dp"
       android:background="#FAFAFA"
       android:textColor="#7C7D82"
       android:text="+"
       android:textSize="24dp"
       android:layout_columnWeight="1"
       android:layout_rowWeight="1"
       />
   <Button
       android:id="@+id/substact"
       android:layout_margin="1dp"
       android:background="#FAFAFA"
       android:textColor="#7C7D82"
       android:text="-"
       android:textSize="24dp"
       android:layout_columnWeight="1"
       android:layout_rowWeight="1"
       />
   <Button
       android:id="@+id/multiply"
       android:layout_margin="1dp"
       android:background="#FAFAFA"
       android:textColor="#7C7D82"
       android:text="×"
       android:textSize="24dp"
       android:layout_columnWeight="1"
       android:layout_rowWeight="1"
       />
   <Button
       android:id="@+id/divide"
       android:layout_margin="1dp"
       android:background="#FAFAFA"
       android:textColor="#7C7D82"
       android:text="÷"
       android:textSize="24dp"
       android:layout_columnWeight="1"
       android:layout_rowWeight="1"
       />
   <Button
       android:id="@+id/seven"
       android:layout_margin="1dp"
       android:background="#FAFAFA"
       android:textColor="#7C7D82"
       android:text="7"
       android:textSize="24dp"
       android:layout_columnWeight="1"
       android:layout_rowWeight="1"
       />
   <Button
       android:id="@+id/eight"
       android:layout_margin="1dp"
       android:background="#FAFAFA"
       android:textColor="#7C7D82"
       android:text="8"
       android:textSize="24dp"
       android:layout_columnWeight="1"
       android:layout_rowWeight="1"
       />
   <Button
       android:id="@+id/nine"
       android:layout_margin="1dp"
       android:background="#FAFAFA"
       android:textColor="#7C7D82"
       android:text="9"
       android:textSize="24dp"
       android:layout_columnWeight="1"
       android:layout_rowWeight="1"
       />
   <Button
       android:id="@+id/left"
       android:layout_margin="1dp"
       android:background="#FAFAFA"
       android:textColor="#7C7D82"
       android:text="("
       android:textSize="24dp"
       android:layout_columnWeight="1"
       android:layout_rowWeight="1"
       />
   <Button
       android:id="@+id/four"
       android:layout_margin="1dp"
       android:background="#FAFAFA"
       android:textColor="#7C7D82"
       android:text="4"
       android:textSize="24dp"
       android:layout_columnWeight="1"
       android:layout_rowWeight="1"
       />
   <Button
       android:id="@+id/five"
       android:layout_margin="1dp"
       android:background="#FAFAFA"
       android:textColor="#7C7D82"
       android:text="5"
       android:textSize="24dp"
       android:layout_columnWeight="1"
       android:layout_rowWeight="1"
       />
   <Button
       android:id="@+id/six"
       android:layout_margin="1dp"
       android:background="#FAFAFA"
       android:textColor="#7C7D82"
       android:text="6"
       android:textSize="24dp"
       android:layout_columnWeight="1"
       android:layout_rowWeight="1"
       />
   <Button
       android:id="@+id/right"
       android:layout_margin="1dp"
       android:background="#FAFAFA"
       android:textColor="#7C7D82"
       android:text=")"
       android:textSize="24dp"
       android:layout_columnWeight="1"
       android:layout_rowWeight="1"
       />
   <Button
       android:id="@+id/three"
       android:layout_margin="1dp"
       android:background="#FAFAFA"
       android:textColor="#7C7D82"
       android:text="3"
       android:textSize="24dp"
       android:layout_columnWeight="1"
       android:layout_rowWeight="1"
       />
   <Button
       android:id="@+id/two"
       android:layout_margin="1dp"
       android:background="#FAFAFA"
       android:textColor="#7C7D82"
       android:text="2"
       android:textSize="24dp"
       android:layout_columnWeight="1"
       android:layout_rowWeight="1"
       />
   <Button
       android:id="@+id/one"
       android:layout_margin="1dp"
       android:background="#FAFAFA"
       android:textColor="#7C7D82"
       android:text="1"
       android:textSize="24dp"
       android:layout_columnWeight="1"
       android:layout_rowWeight="1"
       />
   <Button
       android:id="@+id/Clean"
       android:layout_margin="1dp"
       android:background="#FB7730"
       android:textColor="#FFFFFF"
       android:textSize="24dp"
       android:text="AC"
       android:layout_columnWeight="1"
       android:layout_rowWeight="1"
       />
   <Button
       android:id="@+id/dot"
       android:layout_margin="1dp"
       android:background="#FAFAFA"
       android:textColor="#7C7D82"
       android:text="."
       android:textSize="24dp"
       android:layout_columnWeight="1"
       android:layout_rowWeight="1"
       />
   <Button
       android:id="@+id/zero"
       android:layout_margin="1dp"
       android:background="#FAFAFA"
       android:textColor="#7C7D82"
       android:text="0"
       android:textSize="24dp"
       android:layout_columnWeight="1"
       android:layout_rowWeight="1"
       />
   <Button
       android:id="@+id/equal"
       android:layout_margin="1dp"
       android:background="#FAFAFA"
       android:textColor="#7C7D82"
       android:text="="
       android:textSize="24dp"
       android:layout_columnSpan="2"
       android:layout_columnWeight="1"
       android:layout_rowWeight="1"
       />
</GridLayout>
```



## Main_Activity.java展示部分

首先要建立联系，但是那么多按钮，建立联系是不是太麻烦了哇！这个时候就应该想是不是有一次性建立联系的方法呢，只要想了然后查一查就会发现还真的有！

**FindViewByMe(XML)**很神奇的插件，自行查找如何获取，不在过多描述！

建立的那么多按钮后，如果每个都要单独设置监听事件是不是太麻烦，所以有一个方法onClick方法，多个按钮一起监听。但是在使用此方法是必须连接View.OnClickListener接口。然后set后即可使用。

以下是此方法的运用

```java
public class MainActivity extends AppCompatActivity implements View.OnClickListener{

    /**定义所有使用的按钮，最好与前端id相同,使用findviewbyme! 别一个一个敲*/
    private GridLayout gridlayout;
    private EditText edit;
    private TextView view;
    private Button add;
    private Button substact;
    private Button multiply;
    private Button divide;
    private Button seven;
    private Button eight;
    private Button nine;
    private Button left;
    private Button four;
    private Button five;
    private Button six;
    private Button right;
    private Button three;
    private Button two;
    private Button one;
    private Button Clean;
    private Button dot;
    private Button zero;
    private Button equal;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);

        setContentView(R.layout.activity_main);
        gridlayout = (GridLayout) findViewById(R.id.gridlayout);
        edit = (EditText) findViewById(R.id.edit);
        view = (TextView) findViewById(R.id.view);
        add = (Button) findViewById(R.id.add);
        substact = (Button) findViewById(R.id.substact);
        multiply = (Button) findViewById(R.id.multiply);
        divide = (Button) findViewById(R.id.divide);
        seven = (Button) findViewById(R.id.seven);
        eight = (Button) findViewById(R.id.eight);
        nine = (Button) findViewById(R.id.nine);
        left = (Button) findViewById(R.id.left);
        four = (Button) findViewById(R.id.four);
        five = (Button) findViewById(R.id.five);
        six = (Button) findViewById(R.id.six);
        right = (Button) findViewById(R.id.right);
        three = (Button) findViewById(R.id.three);
        two = (Button) findViewById(R.id.two);
        one = (Button) findViewById(R.id.one);
        Clean = (Button) findViewById(R.id.Clean);
        dot = (Button) findViewById(R.id.dot);
        zero = (Button) findViewById(R.id.zero);
        equal = (Button) findViewById(R.id.equal);
        //建立联系


        edit.setOnClickListener(this);
        view.setOnClickListener(this);
        add.setOnClickListener(this);
        multiply.setOnClickListener(this);
        divide.setOnClickListener(this);
        dot.setOnClickListener(this);
        one.setOnClickListener(this);
        two.setOnClickListener(this);
        three.setOnClickListener(this);
        four.setOnClickListener(this);
        five.setOnClickListener(this);
        six.setOnClickListener(this);
        seven.setOnClickListener(this);
        eight.setOnClickListener(this);
        nine.setOnClickListener(this);
        zero.setOnClickListener(this);
        right.setOnClickListener(this);
        Clean.setOnClickListener(this);
        left.setOnClickListener(this);
        equal.setOnClickListener(this);
        substact.setOnClickListener(this);
		//设置监听


    }
   public void onClick(View v) {
       //………利用获取id的形式来监听
   }
}
```

以下是在使用onClick方法中，通过switch语句来判断那个按钮被按下，并输出相映的字符。

```java
public void onClick(View v) {
    String text = edit.getText().toString();//获取当前文本编译框内容
    String lasttext;
    boolean clean = false;
    Formulautil a = new Formulautil();//自己建立的类！核心部分
    if (text.equals("0"))
    {
        edit.setText("");
    }
    switch(v.getId())
    {
        case R.id.zero:
            edit.setText(edit.getText() + "0");
            Clean.setText("C");
            now = false;
            break;
        case R.id.one:
            edit.setText(edit.getText() + "1");
            Clean.setText("C");
            now = false;
            break;
        case R.id.two:
            edit.setText(edit.getText() + "2");
            Clean.setText("C");
            now = false;
            break;
        case R.id.three:
            edit.setText(edit.getText() + "3");
            Clean.setText("C");
            now = false;
            break;
        case R.id.four:
            edit.setText(edit.getText() + "4");
            Clean.setText("C");
            now = false;
            break;
        case R.id.five:
            edit.setText(edit.getText() + "5");
            Clean.setText("C");
            now = false;
            break;
        case R.id.six:
            edit.setText(edit.getText() + "6");
            Clean.setText("C");
            now = false;
            break;
        case R.id.seven:
            edit.setText(edit.getText() + "7");
            Clean.setText("C");
            now = false;
            break;
        case R.id.eight:
            edit.setText(edit.getText() + "8");
            Clean.setText("C");
            now = false;
            break;
        case R.id.nine:
            edit.setText(edit.getText() + "9");
            Clean.setText("C");
            now = false;
            break;
        case R.id.dot:
            edit.setText(edit.getText() + ".");
            Clean.setText("C");
            now = false;
            break;

        case R.id.right:
            edit.setText(edit.getText() + ")");
            Clean.setText("C");
            now = false;
            break;
        case R.id.left:
            edit.setText(edit.getText() + "(");
            Clean.setText("C");
            now = false;
            break;
        case R.id.add:
            edit.setText(edit.getText() + "+");
            Clean.setText("C");
            now = false;
            break;
        case R.id.substact:
            edit.setText(edit.getText() + "-");
            Clean.setText("C");
            now = false;
            break;
        case R.id.multiply:
            edit.setText(edit.getText() + "×");
            Clean.setText("C");
            now = false;
            break;
        case R.id.divide:
            edit.setText(edit.getText() + "÷");
            Clean.setText("C");
            now = false;
            break;
        case R.id.equal:
            edit.setText(edit.getText() + "=");
            lasttext = edit.getText().toString();
            String a1 = String.valueOf(a.caculate(lasttext));
            view.setText(a1);
            break;
        //清楚操作，保留上一结果===========================================================
        case R.id.Clean:
            edit.setText("0");
            Clean.setText("AC");
            now = true;
        //归零操作，不保留上一次结果=========================================================

    }
```

Main_Activity.java完整部分！

```Java
package com.example.fo_as;

import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.GridLayout;
import android.widget.TextView;


public class MainActivity extends AppCompatActivity implements View.OnClickListener{

    /**定义所有使用的按钮，最好与前端id相同,使用findviewbyme! 别一个一个敲*/
    private GridLayout gridlayout;
    private EditText edit;
    private TextView view;
    private Button add;
    private Button substact;
    private Button multiply;
    private Button divide;
    private Button seven;
    private Button eight;
    private Button nine;
    private Button left;
    private Button four;
    private Button five;
    private Button six;
    private Button right;
    private Button three;
    private Button two;
    private Button one;
    private Button Clean;
    private Button dot;
    private Button zero;
    private Button equal;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);

        setContentView(R.layout.activity_main);
        gridlayout = (GridLayout) findViewById(R.id.gridlayout);
        edit = (EditText) findViewById(R.id.edit);
        view = (TextView) findViewById(R.id.view);
        add = (Button) findViewById(R.id.add);
        substact = (Button) findViewById(R.id.substact);
        multiply = (Button) findViewById(R.id.multiply);
        divide = (Button) findViewById(R.id.divide);
        seven = (Button) findViewById(R.id.seven);
        eight = (Button) findViewById(R.id.eight);
        nine = (Button) findViewById(R.id.nine);
        left = (Button) findViewById(R.id.left);
        four = (Button) findViewById(R.id.four);
        five = (Button) findViewById(R.id.five);
        six = (Button) findViewById(R.id.six);
        right = (Button) findViewById(R.id.right);
        three = (Button) findViewById(R.id.three);
        two = (Button) findViewById(R.id.two);
        one = (Button) findViewById(R.id.one);
        Clean = (Button) findViewById(R.id.Clean);
        dot = (Button) findViewById(R.id.dot);
        zero = (Button) findViewById(R.id.zero);
        equal = (Button) findViewById(R.id.equal);
        //建立联系


        edit.setOnClickListener(this);
        view.setOnClickListener(this);
        add.setOnClickListener(this);
        multiply.setOnClickListener(this);
        divide.setOnClickListener(this);
        dot.setOnClickListener(this);
        one.setOnClickListener(this);
        two.setOnClickListener(this);
        three.setOnClickListener(this);
        four.setOnClickListener(this);
        five.setOnClickListener(this);
        six.setOnClickListener(this);
        seven.setOnClickListener(this);
        eight.setOnClickListener(this);
        nine.setOnClickListener(this);
        zero.setOnClickListener(this);
        right.setOnClickListener(this);
        Clean.setOnClickListener(this);
        left.setOnClickListener(this);
        equal.setOnClickListener(this);
        substact.setOnClickListener(this);
    }
    
    private String lastresult;//用来记录上一个结果
    private boolean now;//判断当前是否进行计算
    
    @Override
    public void onClick(View v) {
        String text = edit.getText().toString();//获取当前文本编译框内容
        String lasttext;
        boolean clean = false;
        Formulautil a = new Formulautil();
        if (text.equals("0"))
        {
            edit.setText("");
        }
        switch(v.getId())
        {
            case R.id.zero:
                edit.setText(edit.getText() + "0");
                Clean.setText("C");
                now = false;
                break;
            case R.id.one:
                edit.setText(edit.getText() + "1");
                Clean.setText("C");
                now = false;
                break;
            case R.id.two:
                edit.setText(edit.getText() + "2");
                Clean.setText("C");
                now = false;
                break;
            case R.id.three:
                edit.setText(edit.getText() + "3");
                Clean.setText("C");
                now = false;
                break;
            case R.id.four:
                edit.setText(edit.getText() + "4");
                Clean.setText("C");
                now = false;
                break;
            case R.id.five:
                edit.setText(edit.getText() + "5");
                Clean.setText("C");
                now = false;
                break;
            case R.id.six:
                edit.setText(edit.getText() + "6");
                Clean.setText("C");
                now = false;
                break;
            case R.id.seven:
                edit.setText(edit.getText() + "7");
                Clean.setText("C");
                now = false;
                break;
            case R.id.eight:
                edit.setText(edit.getText() + "8");
                Clean.setText("C");
                now = false;
                break;
            case R.id.nine:
                edit.setText(edit.getText() + "9");
                Clean.setText("C");
                now = false;
                break;
            case R.id.dot:
                edit.setText(edit.getText() + ".");
                Clean.setText("C");
                now = false;
                break;

            case R.id.right:
                edit.setText(edit.getText() + ")");
                Clean.setText("C");
                now = false;
                break;
            case R.id.left:
                edit.setText(edit.getText() + "(");
                Clean.setText("C");
                now = false;
                break;
            case R.id.add:
                edit.setText(edit.getText() + "+");
                Clean.setText("C");
                now = false;
                break;
            case R.id.substact:
                edit.setText(edit.getText() + "-");
                Clean.setText("C");
                now = false;
                break;
            case R.id.multiply:
                edit.setText(edit.getText() + "×");
                Clean.setText("C");
                now = false;
                break;
            case R.id.divide:
                edit.setText(edit.getText() + "÷");
                Clean.setText("C");
                now = false;
                break;
            case R.id.equal:
                edit.setText(edit.getText() + "=");
                lasttext = edit.getText().toString();
                String a1 = String.valueOf(a.caculate(lasttext));
                view.setText(a1);
                break;
            //清楚操作，保留上一结果，引入计算部分							
            case R.id.Clean:
                edit.setText("0");
                Clean.setText("AC");
                now = true;
            //归零操作，不保留上一次结果
        }
    }
}
```



## 核心计算部分！

计算部分我们采用的是堆栈式的计算，因为可以进行多项式的计算。

思想：输入一串公式，公式当中每个都是不同的字符，然后判断字符是数字还是符号，是数字进数字栈，是符号进符号栈。符号栈里再判断优先级的运算，优先级高的把数字从数字栈里取出，得到答案再入栈！以此进行至结束。

完整代码，全部有注释！

```java
package com.example.fo_as;
import java.util.Stack;
import java.math.BigDecimal;


public class Formulautil {

    /**大致思路是利用栈的出栈入栈压栈来处理一个运算式的先后级排序，进行相映的运算.*/

    //数字栈：用于存储表达式中的各个数字
    private Stack<BigDecimal> numberStack = null;
    //符号栈：用于存储运算符和括号
    private Stack<Character> symbolStack = null;

    private int scale;//除法时出现循环小数保留精度
    public Formulautil(int scale) {
        super();
        this.scale = scale;
    }
    public Formulautil() {
        this(32);
    }

    /**从外面把字符串传递进来！！！*/
    public BigDecimal caculate(String numStr) {
        //判断算数表示是否结束，也就是判断结尾有木有=号！没有给加上！
        //equals方法：值的比较
        //charAt方法：检索方法
        if (numStr.length() > 1
                && !"=".equals(numStr.charAt(numStr.length() - 1) + "")) {
            numStr += "=";
        }
        //检查表达式是否是正确的！利用Standard方法(自定义)
        if (!isStandard(numStr)) {
            String isstandardtext;
            isstandardtext = "出错";
            return null;
        }
        // 初始化栈
        if (numberStack == null) {
            numberStack = new Stack<BigDecimal>();
        }
        numberStack.clear();
        if (symbolStack == null) {
            symbolStack = new Stack<Character>();
        }
        symbolStack.clear();

        /**！！！！！！！！！！核 心！！！！！！！！！！！！*/
        //创建一个StringBuffer，用来放多位的数字
        StringBuffer temp = new StringBuffer();
        // 从表达式的第一个字符开始处理
        for (int i = 0; i < numStr.length(); i++) {
            // 获取一个字符
            char ch = numStr.charAt(i);
            // 若当前字符是数字
            if (isNumber(ch)) {
                // 加入到数字缓存中
                temp.append(ch);
            } else { // 非数字的情况
                // 将数字缓存转为字符串
                String tempStr = temp.toString();
                if (!tempStr.isEmpty()) {
                    BigDecimal num = new BigDecimal(tempStr);
                    // 将数字压栈
                    numberStack.push(num);
                    // 重置数字缓存
                    temp = new StringBuffer();
                }

                // 判断运算符的优先级，若当前优先级低于栈顶的优先级，则先把计算前面计算出来
                while (!comparePri(ch) && !symbolStack.empty()) {
                    // 出栈，取出数字，后进先出
                    BigDecimal b = numberStack.pop();
                    BigDecimal a = numberStack.pop();
                    // 取出运算符进行相应运算，并把结果压栈进行下一次运算
                    switch ((char) symbolStack.pop()) {
                        case '+':
                            numberStack.push(a.add(b));
                            break;
                        case '-':
                            numberStack.push(a.subtract(b));
                            break;
                        case '×':
                            numberStack.push(a.multiply(b));
                            break;
                        case '÷':
                            try {
                                numberStack.push(a.divide(b));
                            } catch (java.lang.ArithmeticException e) {
                                // 进行除法出现无限循环小数时，就会抛异常，此处设置精度重新计算
                                numberStack.push(a.divide(b, this.scale,
                                        BigDecimal.ROUND_HALF_EVEN));
                            }
                            break;
                        default:
                            break;
                    }
                } // while循环结束

                if (ch != '=') {
                    // 符号入栈
                    symbolStack.push(new Character(ch));
                    // 去括号
                    if (ch == ')') {
                        symbolStack.pop();
                        symbolStack.pop();
                    }
                }
            }
        } // for循环结束

        // 返回计算结果
        return numberStack.pop();
    }


    /**=================================检查算数表达式是否合格======================================*/
    private boolean isStandard(String numStr) {
        // 表达式不能为空
        if (numStr == null || numStr.isEmpty())
            return false;
        // 用来保存括号，检查左右括号是否匹配
        Stack<Character> stack = new Stack<Character>();
        // 用来标记'='符号是否存在多个
        boolean b = false;
        for (int i = 0; i < numStr.length(); i++) {
            char n = numStr.charAt(i);
            // 判断字符是否合法
            if (!(isNumber(n) || "(".equals(n + "") || ")".equals(n + "")
                    || "+".equals(n + "") || "-".equals(n + "")
                    || "×".equals(n + "") || "÷".equals(n + "") || "=".equals(n
                    + ""))) {
                return false;
            }
            // 将左括号压栈，用来给后面的右括号进行匹配
            if ("(".equals(n + "")) {
                stack.push(n);
            }
            if (")".equals(n + "")) { // 匹配括号
                if (stack.isEmpty() || !"(".equals((char) stack.pop() + "")) // 括号是否匹配
                    return false;
            }
            // 检查是否有多个'='号
            if ("=".equals(n + "")) {
                if (b)
                    return false;
                b = true;
            }
        }
        // 可能会有缺少右括号的情况
        if (!stack.isEmpty())
            return false;
        // 检查'='号是否不在末尾
        if (!("=".equals(numStr.charAt(numStr.length() - 1) + "")))
            return false;
        return true;
    }

    /**=================================判断是否是0-9的数字========================================*/
    private boolean isNumber(char num) {
        if ((num >= '0' && num <= '9') || num == '.')
            return true;
        return false;
    }

    /**==============比较优先级，如果当前运算符比栈顶元素运算符优先级高则返回true,否则返回false==========*/
    private boolean comparePri(char symbol) {
        // 空栈返回ture
        if (symbolStack.empty()) {
            return true;
        }

        /*
         我设计得这个计算器加减乘除，lg，ln，括号，三角函数，正常得优先级就是有括号先算括号，然后再乘除，在加减
         第一级：（
         第二级： × ÷ sin cos tan lg ln
         第三级： + -
         第四级：）
         */

        // 查看堆栈顶部的对象
        char top = (char) symbolStack.peek();
        if (top == '(') {
            return true;
        }
        // 比较优先级
        switch (symbol) {
            case '(': // 优先级最高
                return true;
            // 优先级比'+'和'-'高
            case '×': {
                if (top == '+' || top == '-')
                    return true;
                else
                    return false;
            }
            // 优先级比'+'和'-'高
            case '÷':
                if (top == '+' || top == '-')
                    return true;
                else
                    return false;

            case '+':
                return false;
            case '-':
                return false;
            // 优先级最低
            case ')':
                return false;
            // 结束符
            case '=':
                return false;
            default:
                break;
        }
        return true;
    }

}
```

# 结束！（有需求的话还可以给按钮添加点击效果）
