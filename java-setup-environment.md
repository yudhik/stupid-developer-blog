Title: Setting Up The Environment
Date: 2019-06-21 19:14
Category: Java

### Background

The first thing to do before you able to learn Java is to understand your computer environment. Nowadays, Java developers indulged by modern IDE, which that is not a wrong way either. However, that will become your stumbling block later when you have some complex things to solve, since everything have their own limitations so you can not depend to one particular solution.

To be able to solve those kind of problem, let's go back to the time when software developer doesn't have a modern IDE as now. With this, we will understand more deeper about the fundamental process how the process works. Trust me, to have a clear understanding about something, sometime we need to go to the "basic how to". 

### Setting up your environment

"So what tools they use before modern IDE ?". Well, they can use any text editor. Vim, vi, notedpad, etc all the basic editor only and they compile it manually too. I would like to demonstrate how the basic thing in java development, let's setup our environment first.

At the first you need to understand that your operating system have an environment named with **PATH** or **Path** _(depend on the OS they might case sensitive or not)_. This environment exists at all the operating system. The purpose of this environment is to be able to call some command without writing the complete path of the file. For instance, on linux based, when you type `ls`, actually it goes to the `/usr/bin/ls` or on windows base, `ping` command will goes to `C:\Windows\System32\PING.EXE`. 

In order to run easily a command in your console,  it is mean you need to put your java installation directory path to the **PATH** environment. But hold on, before you put the value of installed java directory path directly to **PATH**, let's create a new environment call **JAVA_HOME** and put the value to that environment variable at there. So later you can use the **JAVA_HOME** variable inside **PATH** variable. Below are the example how to do it on windows and linux videos :  
1. [Windows environment setup](https://duckduckgo.com)  
2. [Linux environment setup](https://duckduckgo.com)

### Experience the old java developer development life cycle hands-on

Below this paragraph section is the bridging to go to the next step of fundamental java development, you can skip this after viewing to setup environment video. But if you want to do some hands on, read this section below.

Once after your environment finish, that is mean you can directly use some java related command. For instance, `javac` for compile your code, `java` to run your application, etc.

Java programming language is a compiler base programming language, it is like c programming language, you need to do a compilation before you can run your application/code. Compile process will transform your code into some binary instruction for the computer to be able to process your code. Java use `javac` to compile java code into `.class` file.

Let's try to open any of your favorite text editor. Write this hello world code
```
public class HelloWorld {  
  public static void main(String[] args) {  
    System.out.println("Hello World");  
  }  
}  
```
save it as `HelloWorld.java`. Try to compile it by run this command
```
javac HelloWorld.java
```
try to look to your current directory where you run the `javac` command, you will find `HelloWorld.class` there. Run that program, simply by call `java` like this
```
java HelloWorld.class
```
And you will get 
```
Hello World
```
writen on your console. Good, you already know how to compile with `javac` command.

Let's move to more advance example. Somehow by design you have more than 1 `.java` files at there, then how will you compile those java files. More further to this example, you can clone from [git repository](https://github.com/stupid-developer/java-setup-env-hands-on) and put it on your computer. if you are don't know to setup git environment, you can go to [here](git-setup-environment.html)

After successfully getting the source you can try above `javac` command to compile it. Is it work? 
I bet you will unable to compile the classes. This is because the class have some dependencies to another. See below statement at `Geometry.java`
```
import sd.geo.Cube;
import sd.geo.Sphere;
import sd.geo.formula.GeometryFormula;
```
this is mean the class depend to other classes in order to be compile by javac, so before you able to compile this `Geometry.java` you need to compile other file as well. Please note this only happened when you using package on your project(definitely you will use package on your project)

Now, let's compile it one by one in sequence starting from the less dependency class which are: 
1. `sd/geo/formula/GeometryFormula.java`  
2. `sd/geo/Cube.java`  
3. `sd/geo/Sphere.java`  
4. `sd/Geometry.java`
   
If all has been compile you can run it by calling  
`java sd/Geometry 100 4`   
which 100 stand for radius value and 4 is for length value and you will get the value from your application.

Before we end this section, can you imagine if you have more classes and packages? if you curious about how to solve it,  you can go to [Apache Maven Tutorial](https://stupid-developer.net/apache-maven-tutorial.html) or [Apache ANT Tutorial](https://stupid-developer.net/apache-ant-tutorial.html)

Thank you for reading.. and happy coding.

