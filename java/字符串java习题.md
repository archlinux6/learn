### 1.字符串中方法的应用
【问题描述】按要求将程序填充完整
```java
class StringExample{

 public static void main(String[] args){

     String  s1 = new String("china");

     String  s2 = "china";

     if(   s1.equals(s2)                  ){   //判断s1和s2串值是否相同

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

      position =  path.lastIndexOf("\\")  ;         //获取path中最后出现目录分隔符号的位置

      System.out.println("\\ last position in path is:"+position);

      String fileName =  path.substring(22) ;         //获取path中的文件名"example.java"

      System.out.println("fileName = "+fileName);

      String s4="100";

      String s5="123.678";

      String s6 =    new StringBuffer(s5).reverse().toString();                  //将s5反转为"876.321"赋给s6



      int num1 =   Integer.parseInt(s4)     ;             //将字符串s4转化成int

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