
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

