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

### 2.【问题描述】

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

