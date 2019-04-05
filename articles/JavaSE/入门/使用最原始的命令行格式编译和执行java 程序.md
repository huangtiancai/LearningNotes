在工作中开发`java` 应用都会使用`eclipse`,`myeclipse`, `IntelliJ`,这里使用最原始的命令行格式编译和执行`java` 程序 

#### 准备项目目录

在D盘创建project目录，这里用d:/project/j2ee目录作为目录，java代码放在这个项目目录底下，并创建怒路src用于存放java源码.java文件

#### 创建一个java源文件

新建一个test.java并编辑

```java
public class test{
        //主方法，所有代码入口
	public static void main(String[] args){
                 //控制台输出
		System.out.println("Test");       
	}	
}
```

#### 编译

win+r ,输入cmd进入控制台界面

切换盘符为d盘  d:

切换目录为源文件目录 cd d:\javaproject\j2ee\src

`.java` 文件是`java`源文件，不能直接运行，必须被编译成.class文件才能执行

`java` 使用 `javac`命令进行编译:

```
语法：
javac filename.java
```

```
javac test.java
```

![](https://i.loli.net/2019/03/18/5c8f5d9a8c1bd.jpg)

`javac test.java`回车后如果没有报错的话，并且在`src`目录下得到一个class文件`test.class`

#### 运行

```
语法：
java classname
```

```java
java test.class
```

![](https://i.loli.net/2019/03/18/5c8f5f5102207.jpg)

运行成功后会看到字符串"Test"

