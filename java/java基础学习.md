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