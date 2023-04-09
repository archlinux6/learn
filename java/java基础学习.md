### 1.配置Java环境
在archlinux下安装JDK，可以输入  
`sudo pacman -S jdk11-openjdk`  

### 2.编译运行命令
编译：`javac 文件名.java`  

运行：`java 文件名`  

### 3. 命名规则
源文件名应该与公共类名称相同  
类名首字母大写，方法名首字母小写，其余字母皆大写
### 4. Java程序的基本结构
```java
/**
 * 可以用来自动创建文档的注释
 */
public class Hello {
    public static void main(String[] args) {
        // 向屏幕输出文本:
        System.out.println("Hello, world!");
        /* 多行注释开始
        注释内容
        注释结束 */
    }
} // class定义结束
```
### 5. 数据类型
布尔类型boolean只有true和false两个值。  

对于float类型，需要加上f后缀。  

String字符串，System.out.println(sum)，首字母要大写。  
### 6. 数组类型
```java
   一维数组：
   int[] ns = new int[5];
   或
   int[] ns = { 1, 4, 9, 16, 25 }
   或
   int[] ns = new int[] { 68, 79, 91, 85, 62 };
   或
   int[] ns;
   ns = new int[] { 68, 79, 91, 85, 62 };
   二维数组：
   int[][] ns = {
            { 1, 2, 3, 4 },
            { 5, 6, 7, 8 },
            { 9, 10, 11, 12 }
   };

```
用数组名.length可获取数组大小：
```java
for (int i : 数组名) {
    System.out.print(i + ", ");
}
```
可以用来打印数组元素

### 7. String类
创建字符串：
```java
String str = "Runoob"; // String 直接创建

String str = new String("Runoob") //构造函数创建字符串

char[] helloArray = { 'r', 'u', 'n', 'o', 'o', 'b'};
String helloString = new String(helloArray);  
```
字符串长度:
```java
String site = "www.runoob.com";
int len = site.length();
```
###### String 方法
charAt() 方法 返回指定索引处的 char 值。
```java
public class Test {
    public static void main(String args[]) {
        String s = "www.runoob.com";
        char result = s.charAt(6);
        System.out.println(result);
    }
}
```
以上程序执行结果为：  
n

###  Java标准库
import java.util.Arrays;   

使用Arrays.toString(数组名)可以快速获取数组内容    

使用Arrays.sort(数组名)可以排序

### 其他 
println是print line的缩写，表示输出并换行。因此，如果输出后不想换行，可以用print() 。
一个Java源文件可以包含多个类的定义，但只能定义一个public类。