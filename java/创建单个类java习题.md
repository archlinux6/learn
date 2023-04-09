### 1.	类和对象定义和使用
【问题描述】

下面程序有三个类，补充完整代码，编译并调试。  
【样例输入】  
 无  
【样例输出】

    Thanks,Mom!

    My name is DingDing.

    I'm 5.

    Mom,I was hungry!

    Miao!Miao!I'm a pretty kitty.
```java
    class Dog{  //Dog类

	String name;
	int age;
	Dog(String name1, int age1){
		name = name1;
		age = age1;
		System.out.println("Thanks,Mom!");
	}

	void bark(){
		System.out.println("wang!wang!Dont't come over.");
	}
	void hungry(){
		System.out.println("Mom,I was hungry!");
	}

}
class Cat{   //Cat类
	String name;
	int age;
	void bark(){
		System.out.println("Miao!Miao!I'm a pretty kitty.");
	}
	void hungry(){
		System.out.println("Mom,I was hungry!");
	}


}

public class AnimalTest{ // AnimalTest类
	public static void main(String args[])
	{   
        //Dog
		Dog myDog = new Dog("DingDing",5); //创建Dog对象，name为"DingDing"，age为5
		System.out.println("My name is "+myDog.name+"."); //输出Dog的名字
		System.out.println("I'm "+myDog.age+".");
		myDog.hungry();//调用Dog的hungry()方法 
        //Cat
		Cat myCat = new Cat();//创建Cat对象
		myCat.name = "Alice"; //设置Cat的名字为Alice
		myCat.age = 1;
		myCat.bark(); //调用Cat的bark()方法 
		
		
	}

}

```

### 2. 矩形相交
【问题描述】

平面上有两个矩形A和B，其位置是任意的。编程求出其相交部分的面积。（0<=a，b<=1000）

【输入形式】

从标准输入读取两行以空格分隔的整数，格式如下：  

Ax1 Ay1 Ax2 Ay2  
Bx1 By1 Bx2 By2

其中（x1，y1）和（x2，y2）为矩形对角线上端点的坐标。各坐标值均为整数，取值在0至1000之间。
 
【输出形式】

向标准输出打印一个整数，是两矩形相交部分的面积（可能为0）。

【输入样例】

    0 0 2 2
    1 1 3 4
 
【输出样例】

1

    提示：输入的两点可以是矩形任一对角线上的端点，求相交的面积可以先求矩形在X轴和Y轴上的交集。矩形在X轴上的交集可以按照如下算法进行求解：假设AX1和AX2中的较大值为MAX_AX，较小值为MIN_AX；BX1和BX2中的较大值为MAX_BX，较小值为MIN_BX。用MAX_AX和MAX_BX中的较小者减去MIN_AX和MIN_BX中的较大者，结果为正表示两矩形在X轴上的交集，若为负则表示不相交。

【评分标准】要求将矩形设计成类Rectangle：

（1）它有四个参数的构造方法，完成定制初始化

（2）它有一个能与另一个矩形求相交面积的功能

主程序形如：

    Rectangle r1 = new Rectangle(0,0,2,2);

    Rectangel r2 = new Rectangle(1,1,3,4);

    int area = r1.intersect(r2);

    System.out.println(area);


```java
import java.util.Scanner;

public class Test {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int ax1 = scanner.nextInt();
        int ay1 = scanner.nextInt();
        int ax2 = scanner.nextInt();
        int ay2 = scanner.nextInt();
        int bx1 = scanner.nextInt();
        int by1 = scanner.nextInt();
        int bx2 = scanner.nextInt();
        int by2 = scanner.nextInt();

        Rectangle r1 = new Rectangle(ax1, ay1, ax2, ay2);
        Rectangle r2 = new Rectangle(bx1, by1, bx2, by2);

        int area = r1.intersect(r2);
        System.out.println(area);
    }
}

class Rectangle {
    private int x1;
    private int y1;
    private int x2;
    private int y2;

    public Rectangle(int x1, int y1, int x2, int y2) {
        this.x1 = Math.min(x1, x2);
        this.y1 = Math.min(y1, y2);
        this.x2 = Math.max(x1, x2);
        this.y2 = Math.max(y1, y2);
    }

    public int intersect(Rectangle other) {
        /*
        在Java中，Math是一个内置的数学类，它提供了许多用于执行各种数学计算的方法。这些方法包括基本的算术运算、三角函数、指数函数、对数函数、四舍五入、取整等。一些常用的Math方法包括sin（正弦）、cos（余弦）、tan（正切）、sqrt（平方根）、pow（次幂）等。可以通过使用“Math.方法名（参数）”的语法来调用这些方法。
        */
        int xOverlap = Math.max(0, Math.min(this.x2, other.x2) - Math.max(this.x1, other.x1));
        int yOverlap = Math.max(0, Math.min(this.y2, other.y2) - Math.max(this.y1, other.y1));
        return xOverlap * yOverlap;
    }
}



```
### 3.设计矩形类
【问题描述】定义一个矩形类 Rectangle，要求包含以下成员：

成员变量： 宽度width和高度height;

构造方法： 

          1、无参数的构造方法，生成边长都为1的单位矩形

          2、含有一个参数，构造长宽相等

          3、含有2个参数根据给出的参数a,b构造矩形

成员方法：

          1、 getPerimeter返回矩形的周长

          2 、getArea返回矩形的面积

          3 、getDiagonal返回矩形对角线长度

          4 、isSquare 返回是否是正方形

          5 、show()  用*形式画出该长方形，如果该矩形是边长为1的正方形，则打印图形为*

 【输入形式】  
 两个整数用空格隔开，代表矩形的宽度和高度


【输出形式】  
  矩形的周长，面积，主对角线长度（保留两位小数），是否是正方形及按要求画出矩形。

【样例输入】

  5  3  
【样例输出】
```
5 3
16
15
5.83
false
*****
*   *
*****
```
  ```java
import java.util.Scanner;
class Rectangle
{
            private int width;
            private int height;
	        Rectangle()
	         {
	             this.width = this.height = 1;
	         }
	        Rectangle(int x)
	        {
	            this.width = this.height = x;
	        }
	        Rectangle(int width, int height)
	        {
	            this.width = width;
	            this.height = height;
	        }
	        public int getPerimeter()
	        { 
	            return 2 * ( this.width + this.height );
	        }
	       public int getArea()
	        {  
	            return this.width * this.height;
	        }
	        public double getDiagonal()
	        {
	            return Math.sqrt(Math.pow (this.width, 2) + Math.pow(this.height, 2));
	        }
	       public boolean isSquare()
	        {  
	            return this.width == this.height;
	        }
	       public void show()
	        {
                for(int i = 0; i < this.height; i++)
                {
                    for(int j = 0; j < this.width; j++)
                        if(i == 0 || i == this.height - 1)
                            System.out.printf("*");
                        else if(j == 0 || j == this.width - 1)
                            System.out.printf("*");
                        else
                            System.out.printf(" ");
                    System.out.println();
                }
	        }

}
 
public class P9 {
        public static void main(String[] args) {
    	Scanner in = new Scanner(System.in);
    	int w = in.nextInt();
    	int h = in.nextInt();
    	Rectangle  r = new Rectangle(w,h);
    	System.out.println(r.getPerimeter());
    	System.out.println(r.getArea());
    	System.out.printf("%.2f\n",r.getDiagonal());
    	System.out.println(r.isSquare());
    	r.show();
    }
}

  ```

### 4.	设计分数类
【问题描述】设计一个表示分数的类Fraction要求如下：

class Fraction{

//成员变量

      两个int类型的变量分别表示分子和分母。

//成员方法

      1、Fraction(int a, int b);   //两个参数的构造方法，构造一个a/b的分数。

      2、double toDouble();        //将分数转换为double

      3、Fraction plus(Fraction r);//将自己和分数r相加，产生一个新的Fraction的对象。注意小学四年级学过两个分数如何相加的

      4、Fraction multiply(Fraction r);//将自己和分数r相乘，产生一个新的Fraction的对象。

      5、void print();  //将自己以“分子/分母”的形式输出到标准输出，并带有回车换行。如果分数是1/1，应该输出1。当分子大于分母时，不需要提出整数部分，即31/30是一个正确的输出。

}

注意，在创建和做完运算后应该化简分数为最简形式。如2/4应该被化简为1/2 ,求两个数的最大约数可以做成一个私有的方法供接口调用。


【输入形式】

      四个用空格逗开的整数，分别构成两个分数，依次是分子和分母

【输出形式】 

      输出一些算式，每个算式一 行

【输入样例】

     2 4 1 3

【输出样例】

    1/2

    1/3

    5/6

    1

    0.50

    0.33


```java
import java.util.Scanner;
class Fraction{
      int fenzi;
          int fenmu;
          public Fraction(int a, int b) {
              fenzi=a;
              fenmu=b;
          }
          double toDouble(){
              return    (double)fenzi/fenmu;
          }
          void print(){
              int x=0;
              for (int i = 1; i <=(fenzi<=fenmu?fenzi:fenmu) ; i++) {
                  if((fenzi%i==0)&&(fenmu%i==0)){
                      x=i;
                  }
              }
              int a=fenzi/x;
              int b=fenmu/x;
              if(a==b) System.out.println("1");
              else System.out.println(a+"/"+b);
          }
       
          public Fraction plus(Fraction b) {
              int fenzi1=this.fenzi*b.fenmu+b.fenzi*this.fenmu;
              int fenmu1=this.fenmu*b.fenmu;
              return new Fraction(fenzi1,fenmu1);
          }
       
          public Fraction multiply(Fraction b) {
              int fenzi1=this.fenzi*b.fenzi;
              int fenmu1=this.fenmu*b.fenmu;
              return new Fraction(fenzi1,fenmu1);
          }

}
public class Main {
    public static void main(String[] args) {
		    Scanner in = new Scanner(System.in);
		    Fraction a = new Fraction(in.nextInt(),in.nextInt());
		    Fraction b = new Fraction(in.nextInt(),in.nextInt());
		    a.print();
		    b.print();
		    a.plus(b).print();
		    a.multiply(b).plus(new Fraction(5,6)).print();
		    System.out.printf("%.2f\n",a.toDouble());
		    System.out.printf("%.2f\n",b.toDouble());
		    in.close();
    }
}



```


### 5. 自定义日期MyDate类
【问题描述】自定义日期MyDate类，要求：

（1）任意给定一个日期，求n天后是哪一天？

（2）任意给定两个日期，它们相差多少天？  

【输入形式】

    第一行，第一个日期

    第二行，一个整数n

    第三行，第二个日期  

【输出形式】

    第一行，一个日期（表示第一个日期n天后的日期）

    一个整数（表示第一个日期与第二个日期相差的天数）  

【样例输入】

    2023-3-27

    10

    2024-3-26

【样例输出】

    2023-04-06

    365

【样例说明】

 如果第一个日期小于第二个日期，则两者相差的天数n是正数，反之则为负数

 ```java
import java.util.*;

class  MyDate{
        private int year;
        private int month;
        private int  day;
        public MyDate(int year,int month,int day){
                
                        this.year = year;
                        this.month = month;
                        this.day = day;
        }
        public MyDate  next(){   //求当前天的下一天
                 int[] daysInLeapYearMonth = { 0, 31, 29, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31 };
                      int[] daysInNonLeapYearMonth = { 0, 31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31 };
                      boolean isLeapYear = (year % 4 == 0 && year % 100 != 0) || (year % 400 == 0);
                      int[] daysInMonth = isLeapYear ? daysInLeapYearMonth : daysInNonLeapYearMonth;
              
                      if (day < daysInMonth[month]) {
                          return new MyDate(year, month, day + 1);
                      } else if (month < 12) {
                          return new MyDate(year, month + 1, 1);
                      } else {
                          return new MyDate(year + 1, 1, 1);
                      }
        }
        public MyDate  next( int  n){   //求当前天过n天后是哪一天
               
                       MyDate result = this;
                       for (int i = 0; i < n; i++) {
                           result = result.next();
                       }
                       return result;

        }
        public int getDays(MyDate other){ //求当前天与other天之间相关的天数
                 if ((this.year - other.year) == 0 && (this.month - other.month) == 0 && (this.day - other.day) == 0)
                           return 0;
               
                       if ((this.year - other.year) < 0 || (this.month - other.month) < 0 || (this.day - other.day) < 0) {
               
                           int days = 0;
                           MyDate temp = new MyDate(year, month, day);
                           temp = temp.next();
                           while ((other.year - temp.year) != 0 || (other.month - temp.month) != 0
                                   || (other.day - temp.day) != 0) {
                               days++;
                               temp = temp.next();
                           }
                           return days + 1;
                       } else {
                           int day = other.getDays(this);
                           return -1 * day;
                       }
        }
        public void show(){
               System.out.printf("%d-%02d-%02d\n",year,month,day);
        }
        public static MyDate  getDate(String str){ //将字符串分解后生成一个日期对象
              String[]  words = str.split("-");
              
              
                      int year = Integer.parseInt(words[0]);
                      int month = Integer.parseInt(words[1]);
                      int day = Integer.parseInt(words[2]);
              return  new MyDate( year, month, day);
        }
}
public class Main{
	public static void main(String[] args){
                Scanner in = new Scanner(System.in);
                String str1 = in.next();
                int n = in.nextInt();
                String str2 = in.next();
                MyDate d1 = MyDate.getDate(str1);
                MyDate d2 = MyDate.getDate(str2);
                d1.next(n).show();
                System.out.println(d1.getDays(d2));
    }
}



 ```