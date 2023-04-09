### 1.字符串中方法的应用
【问题描述】按要求将程序填充完整
```java
class StringExample{

 public static void main(String[] args){

     String  s1 = new String("china");

     String  s2 = "china";

     if(   s1.equals(s2)                  ){   //判断s1和s2串值是否相同
     /*
    在Java中，s1==s2判断的是s1和s2两个对象的引用是否相同，而不是它们所包含的字符串值是否相同。因此，即使s1和s2包含完全相同的字符串值，但如果它们是由不同的对象引用的，它们仍然被认为是不同的。要比较s1和s2的字符串值是否相同，应该使用s1.equals(s2)方法。这个方法会检查s1和s2所包含的字符串值是否相等。
     */

          System.out.println("s1=s2");

     }else{

          System.out.println("s1!=s2");

     } 

     String s3 = new String("320106199105120467");

     if(    s3.startsWith("320106")               ){   //判断s3的前缀是否是“320106”

           System.out.println("JiangShu Nanjing ID");

      }

      int position = 0;

      String path = "d:\\javaKK\\src\\Lesson3\\example.java";
       // '\\'转义字符
      position =  path.lastIndexOf("\\")  ;         //获取path中最后出现目录分隔符号的位置

      System.out.println("\\ last position in path is:"+position);

      String fileName =  path.substring(22) ;         //获取path中的文件名"example.java"，22是e在字符串里的index

      System.out.println("fileName = "+fileName);

      String s4="100";

      String s5="123.678";

      String s6 =    new StringBuffer(s5).reverse().toString();                  //将s5反转为"876.321"赋给s6
      /*
      该行代码将字符串变量 s5 转换成 StringBuffer 对象，然后对其进行翻转（reverse），最后再将翻转后的结果转换成 String 类型并赋值给新的字符串变量 s6。简而言之，该行代码的作用是将字符串 s5 反转，并把反转后的结果存储到 s6 中。
      */

      int num1 =   Integer.parseInt(s4)     ;             //将字符串s4转化成int
      //"parse" 是英文单词，意思是解析或分析。
      double num2 =       Double.parseDouble(s6)    ;      //将字符串s6转化成double
     
      double sum = num1+num2;

      System.out.println("sum = "+sum);

      String s7 = "ABCDEF";

     for(int i=0;i<s7.length();i++){

          System.out.print(s7.charAt(i));

      }
 System.out.print("\n");
      char arr[] =      s7.toCharArray();               //将s7存放到数组arr中

      for(int i=arr.length-1;i>=0;i--){

          System.out.printf("%3c",arr[i]);

      }

  }

}

```
【输入形式】

     无
【输出形式】 
``` 
s1=s2  
JiangShu Nanjing ID  
\ last position in path is:21  
fileName = example.java  
sum = 976.321  
ABCDEF  
  F  E  D  C  B  A
  ```