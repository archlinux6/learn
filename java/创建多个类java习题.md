
1. 补全java代码
```java
class Body{       
    //此处代码省略    
 }   //车身类

class Passenger{ 
     //此处代码省略    
}   //乘客类

class Wheel
{     
    //此处代码省略   
}   //车轮类

class Driver{   //司机类

      public String name;    //表示第几路公交车司机

      public Driver(String driverName){

             name = driverName;          
      }
}

class Engine{   //发动机类

      public String engineNo;   //发动机编号

      public Engine(String engineNo){

              this.engineNo = engineNo;

      }

}

public class car{   //汽车类

      static final int    (1)     =7;    //定义最多载客数

      static final int MAX_WHEELS=5;   //定义最多轮胎数

      private  int  number = 0;       //车上乘客数量

      protected Engine engine;

      protected Driver driver;

      protected Body body = new Body();

      protected wheel[] wheels;

      protected Passenger[]passengers;

      public Car(Driver driver){      //构造函数

                (2)  .driver = driver;

             engine = new Engine("TX6536型号引擎");

             wheels = new Wheel[MAX_WHEELS];

             passengers = new Passenger[MAX_PASSENGERS];

             for(int index =0; index <MAX_WHEELS; index++){

                     wheels[index] = new wheel();

             }

             for(int index =0; index <MAX_PASSENGERS; index++){

                     passengers[index] = null;

             }

       }

       public int getPassengerNumber(){  //获取车上乘客数量

               （3）   

       }

       public void getOnPassenger(Passenger aPassenger）{  //乘客上车

               （4）   

       }

       public void run{ //开车

             if(    (5)   ){

                  systern.out.printIln("司机尚未上车!");

                  return;

             }

             System.out.println("车子在开动!")

       }

}

 

public  class  Program{

       public static void main( String args[]){

             Driver driver = new Driver("第五路公交车司机");

             car car =new Car(    (6)    );

             for (int index = 0 ; index < MAX_PASSENGERS; index ++)

                  car. getOnPassenger(     (7)     Passenger());

             car.run();

       }

}

```
（1） MAX_PASSENGERS - 这是定义了最多载客数的静态常量，表示车辆最多能够同时搭载的乘客人数。

（2）this - 关键字“this”表示当前对象，“this.driver”是指Car类中的driver属性。

（3）return number; - 这段代码返回车上乘客数量（number属性）。

（4）passengers[number] = aPassenger; number++; - 这段代码将传入的aPassenger添加到passengers数组中，并增加车上乘客数量（number属性）。

（5）driver == null - 如果driver属性为null，则表示司机尚未上车，不能开车。

（6）driver - 这里将Driver实例作为参数传递给Car构造函数，以便初始化车辆时设置司机属性。

（7）new - 这里使用关键字“new”创建一个新的Passenger实例，并将其传递给getOnPassenger()方法，以便将其添加到passengers数组中。


在Java中，使用 "static final int" 来定义一个只读的常量（constant）。其中：

static 表示该常量属于类，而不是对象实例。
final 表示该常量的值不能被修改。
int 表示该常量的数据类型为整型。
下面是一个例子：

```java
public class MyClass {
    public static final int MY_CONSTANT = 123;
}
```
在其他类中可以通过 MyClass.MY_CONSTANT 访问该常量。

2.【问题描述】  
编写一个java应用程序，该程序中有3个类：Triangle,Rectangle和Circle,分别用来刻画“三角形”、“矩形”和“圆形”。具体要求如下：

l  Triangle类具有类型为double的三条边属性，具有返回周长、面积以及修改三个边的方法。另外，Triangle类还具有一个boolean型的属性，该属性用来判断三个数能否构成一个三角形。

l  Rectangle类具有类型为double的宽、高属性，具有返回周长和面积的方法。

l  Circle类具有类型为double的半径属性，具有返回周长、面积的方法。

```java
class Triangle{
    private double sideA,sideB,sideC;
    private boolean boo;
    public Triangle(double a,double b,double c){
                     sideA=a;
                     sideB=b;
                     sideC=c;
        boo = judge(a,b,c);
    }
    public double getPerimeter(){
                 if(boo)
                 {
                     return(sideA+sideB+sideC);
                 }
                 else
                 {
                     System.out.println("error,can not calculate perimeter");
                     return  0;
                 }
    }
    public double getArea(){
        if(boo){
            double p=(sideA+sideB+sideC)/2.0;
            double area=Math.sqrt(p*(p-sideA)*(p-sideB)*(p-sideC));
            return area;
        }else{
            System.out.println("error,can not calculate area");
            return 0;
        }
    }
    public void setABC(double a,double b,double c){
        sideA = a;  sideB = b; sideC = c;
        boo = judge(a,b,c);
    }
    public boolean judge(double a,double b,double c){
        if((a+b>c)&&(a+c>b)&&(b+c>a)&&(a-b<c)&&(a-c<b)&&(b-c<a)){
                         return  true;
        }else{
                         return false;
        }
    }
}
class Rectangle{
    private double width,height;
    Rectangle(double width,double height){
                 this.width=width;
                 this.height=height;
    }
    public double getPerimeter(){
        return  2*(width+height);
    }
    public double getArea(){
                return width*height;
    }
}

class Circle{
    private double radius;
    public Circle(double radius){
                  this.radius=radius;
    }
    public double getArea(){
      return  Math.PI * radius * radius;
    }
    public double getPerimeter(){
      return Math.PI * 2 * radius;
    }
    public double getRadius() {
        return radius;
    }
    public void setRadius(double radius) {
        this.radius = radius;
    }
}

public class ShapeTest {
    public static void main(String[] args){
        double perimeter,area;
        Circle c=null;
        Triangle t;
        Rectangle r;
        c=new Circle(5)   ;
        t=new Triangle(6,8,10) ;
        r=new Rectangle(7,3)  ;
        perimeter=c.getPerimeter() ;
        System.out.printf("circle's perimeter:%.2f",perimeter);
        area=c.getArea();
        System.out.printf("circle's area:%.2f",area);
        perimeter=t.getPerimeter() ;
        System.out.println("triangle's perimeter:"+perimeter);
        area=t.getArea()    ;
        System.out.println("triangle's area:"+area);
        perimeter=r.getPerimeter() ;
        System.out.println("rectangle's perimeter:"+perimeter);
        area= r.getArea() ;
        System.out.println("rectangle's area:"+area);
        t.setABC(12,34,1);
        area=t.getArea();
        System.out.println("triangle's area:"+area);
        perimeter=t.getPerimeter();
        System.out.println("triangle's perimeter:"+perimeter);
    }
}




```

3.【问题描述】  
在平面坐标系中，不在一条直线上的三个点确定一个三角形，设计点Point类，由点类组合创建三角形类Triangle，设计要求：

点类Point

     属性：

           x,y坐标

     方法：

          （1）两个参数的构造方法

          （2）计算与另一点的距离方法

三角形类Triangle

     属性：

           三个点
           三个边

     方法：

          （1）三个参数的构造方法

          （2）判断三个点能否构成一个合法三角形

          （3）计算周长方法

          （4）计算面积方法


【输入形式】

         一行6个由空格隔开的点数，依次表示三个点的坐标
【输出形式】

         两行，第一行周长，第二行面积。（当三点不能构成一个三角形时，输出一行相关信息，在下一行输出0）
【样例输入1】

  0 0 3 0 3 4

【样例输出1】

 12.00

 6.00

【样例输入2】

 1 1 2 2 3 3

【样例输出2】

 error,can not calculate perimeter

 0.00

 error,can not calculate area

 0.00

【样例说明】  


```java

import java.util.Scanner;
class Point 
{
               private double x,y;
               public Point(double x,double y)
               {
            	   this.x=x;
            	   this.y=y;
               }
               
               public double getDistance(Point o)
               {
            	   return Math.sqrt((this.x - o.x) *(this.x - o.x) +(this.y - o.y) * (this.y - o.y) );
               }

}
class Triangle{
	        Point p1;
		    Point p2;
		    Point p3;
		    double a;
		    double b;
		    double c;
		    Triangle(Point p1, Point p2, Point p3) {
		        this.p1 = p1;
		        this.p2 = p2;
		        this.p3 = p3;
		    }
		    boolean isTriangle(Point p1, Point p2, Point p3) {
		        this.a = p1.getDistance(p2);
		        this.b = p1.getDistance(p3);
		        this.c = p2.getDistance(p3);
		       if((a+b>c)&&(a+c>b)&&(b+c>a)&&(a-b<c)&&(a-c<b)&&(b-c<a)){
                         return  true;
                  }else{
                         return false;
                       }
		    }
		    
		    double getPerimeter() {
		        if (isTriangle(this.p1, this.p2, this.p3)) {
		          return this.a + this.b + this.c;
		        } else {
		            System.out.println("error,can not calculate perimeter");
		            return 0;
		        }
		    }
		    
		    double getArea() {
		       if (isTriangle(this.p1, this.p2, this.p3)) {
		           double s = getPerimeter() / 2;
		           return Math.sqrt(s * (s - this.a) * (s - this.b) * (s - this.c));
		       } else {
		           System.out.println("error,can not calculate area");
		           return 0;
		       }
		    }
}

public class ShapeTest {
	public static void main(String[] args){
	     Scanner in = new Scanner(System.in);
	     double x1,y1,x2,y2,x3,y3;
	     x1 = in.nextDouble();
	     y1 = in.nextDouble();
	     x2 = in.nextDouble();
	     y2 = in.nextDouble();
	     x3 = in.nextDouble();
	     y3 = in.nextDouble();
	     Triangle  t = new Triangle(new Point(x1,y1),new Point(x2,y2),new Point(x3,y3));
	     System.out.printf("%.2f\n",t.getPerimeter());
	     System.out.printf("%.2f\n",t.getArea());   
	}
}




```

4.【问题描述】

　　数轴上有一条长度为L（L为偶数)的线段，左端点在原点，右端点在坐标L处。有n个不计体积的小球在线段上，开始时所有的小球都处在偶数坐标上，速度方向向右，速度大小为1单位长度每秒。

　　当小球到达线段的端点（左端点或右端点）的时候，会立即向相反的方向移动，速度大小仍然为原来大小。

　　当两个小球撞到一起的时候，两个小球会分别向与自己原来移动的方向相反的方向，以原来的速度大小继续移动。

　　现在，告诉你线段的长度L，小球数量n，以及n个小球的初始位置，请你计算t秒之后，各个小球的位置。

提示：

　　因为所有小球的初始位置都为偶数，而且线段的长度为偶数，可以证明，不会有三个小球同时相撞，小球到达线段端点以及小球之间的碰撞时刻均为整数。

　　同时也可以证明两个小球发生碰撞的位置一定是整数（但不一定是偶数）。


【输入形式】

       输入的第一行包含三个整数n, L, t，用空格分隔，分别表示小球的个数、线段长度和你需要计算t秒之后小球的位置。

　　第二行包含n个整数a1, a2, …, an，用空格分隔，表示初始时刻n个小球的位置。

【输出形式】

      输出一行包含n个整数，用空格分隔，第i个整数代表初始时刻位于ai的小球，在t秒之后的位置。

【样例输入】

      3 10 5

      4 6 8

【样例输出】

      7 9 9

【样例说明】

 初始时，三个小球的位置分别为4, 6, 8。



一秒后，三个小球的位置分别为5, 7, 9。




两秒后，第三个小球碰到墙壁，速度反向，三个小球位置分别为6, 8, 10。



三秒后，第二个小球与第三个小球在位置9发生碰撞，速度反向（注意碰撞位置不一定为偶数），三个小球位置分别为7, 9, 9。



四秒后，第一个小球与第二个小球在位置8发生碰撞，速度反向，第三个小球碰到墙壁，速度反向，三个小球位置分别为8, 8, 10。


五秒后，三个小球的位置分别为7, 9, 9。


【样例输入】

    10 22 30

    14 12 16 6 10 2 8 20 18 4

【样例输出】

    6 6 8 2 4 0 4 12 10 2

【数据的规模与约定】

对于所有评测用例，1 ≤ n ≤ 100，1 ≤ t ≤ 100，2 ≤ L ≤ 1000，0 < ai < L。L为偶数。

　　保证所有小球的初始位置互不相同且均为偶数。

【评分标准】

   将球设计成类Ball,每个小球是一个对象，用一个对象数组来存放一组小球（如非此设计程序不得分）：

   属性：

        int  pos;    //坐标位置 

        int dx;       //运动方向及步长,+1向右，-1向左 

    方法：

        Ball（int pos);       //构造方法

        void next()；              //一秒运动一次

        boolean isTouch(Ball other)；//判断是否与另一球相碰

        boolean reachBorder(int L) ；//判断是否到达边界

        changeDir()；             //改变运动方向，向左变向右，向右变向左

        int  getPos();              //返回当前位置

     主程序思路：

       （1）根据输入创建并初始化一组小球

       （2）while(每秒循环一次）{

                         判断每个球当前有没有运动到边界，到边界的球，要改变其运动方向

                         判断任意两个球当前有没有碰撞，如碰撞则彼此都要改变运动方向

                         让每个球运动一次

                }

        （3）打印每个小球的位置


```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int n = scanner.nextInt();
        int L = scanner.nextInt();
        int t = scanner.nextInt();

        Ball[] balls = new Ball[n];
        for (int i = 0; i < n; i++) {
            int pos = scanner.nextInt();
            balls[i] = new Ball(pos);
        }

        // 每秒循环一次
        int i = 0;
        while ( i < t) {
             // 计算球之间的碰撞
             for (int j = 0; j < n; j++) {
                for (int k = j + 1; k < n; k++) {
                    if (balls[j].isTouch(balls[k])) {
                        balls[j].changeDir();
                        balls[k].changeDir();
                    }
                }
            }

            // 判断每个球当前有没有运动到边界，到边界的球，要改变其运动方向
            for (Ball ball : balls) {
                if (ball.reachBorder(L)) {
                    ball.changeDir();
                }
            }
           
            // 让每个球运动一次
            for (Ball ball : balls) {
                ball.next();
            }
            i++;
          
      }


        // 打印每个小球的位置
        for (Ball ball : balls) {
            System.out.print(ball.getPos() + " ");
        }
    }
}

class Ball {
    private int pos;
    private int dx;

    public Ball(int pos) {
        this.pos = pos;
        this.dx = 1;
    }

    public void next() {
        pos += dx;
    }

    public boolean isTouch(Ball other) {
        return Math.abs(pos - other.pos) == 0 && dx == -other.dx;
    }

    public boolean reachBorder(int L) {
        return pos == 0 || pos == L;
    }

    public void changeDir() {
        dx = -dx;
    }

    public int getPos() {
        return pos;
    }
}






```