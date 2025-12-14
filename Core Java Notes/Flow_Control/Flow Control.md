# Flow Control
* *Flow control describes the order in which the statements will be executed* at runtime.

![alt text](image.png)

---
# Selection Statements
## if-else
```java
if(b) { //b should be boolean type
    Action if b is true
}
else {
    Action if b is false
}
```
* The *argument to* the *if statement should be boolean* type. By mistake, *if* we are *trying to provide any other type* then, we *will get compile time error*.
```java
public class Test {
    public static void main(String[] args) {
        int x = 10;
        if (x) {
            System.out.println("Hello");
        }
        else{
            System.out.println("Hi");
        }
        /*
        error: incompatible types: int cannot be converted to boolean
        if (x) {
            ^
        */
    }
}

```
```java
public class Test {
    public static void main(String[] args) {
        int x = 10;
        if (x = 20) {
            System.out.println("Hello");
        }
        else{
            System.out.println("Hi");
        }
        /*
       error: incompatible types: int cannot be converted to boolean
        if (x = 20) {
              ^
        */
    }
}

```
```java
public class Test {
    public static void main(String[] args) {
        int x = 10;
        if (x == 20) {
            System.out.println("Hello");
        }
        else{
            System.out.println("Hi");   //Hi
        }
    }
}

```
```java
public class Test {
    public static void main(String[] args) {
        boolean b = true;
        if (b = false) {
            System.out.println("Hello");
        }
        else{
            System.out.println("Hi");   //Hi
        }
    }
}
```
```java
public class Test {
    public static void main(String[] args) {
        boolean b = false;
        if (b == false) {
            System.out.println("Hello");    //Hello
        }
        else{
            System.out.println("Hi");
        }
    }
}
```
* "*else*" part and *curly braces*({}) are *optional*. *Without curly braces*{}, *only one statement* is *allowed* under if *which should not be declarative statement*.
```java
public class Test {
    public static void main(String[] args) {
        if(true)
            System.out.println("Hello");    //Hello
    }
}
```
```java
public class Test {
    public static void main(String[] args) {
        if(true);
    }
}
```
```java
public class Test {
    public static void main(String[] args) {
        if(true)
            int x = 10;
        /*
        error: variable declaration not allowed here
            int x = 10;
                ^
        */
    }
}
```
```java
public class Test {
    public static void main(String[] args) {
        if(true)
        {
            int x = 10;
        }
    }
}
```
* *Semicolon*(;) is a *valid java statement* which is also *known as empty statement*.
* There is *no dangling else problem in java*. *Every else* is *mapped to the nearest if statment*.
```java
public class Test {
    public static void main(String[] args) {
        if(true)
            if (false) 
                System.out.println("Hello");
        else
            System.out.println("Hi");   //Hi
    }
}
```
## switch
* If several options are available, then it is not recommended to use nested if-else. Because, it reduces readability.
* To handle this requirement, we should go for switch statement.
```java
switch(x){
    case 1:
        Action-1;
        break;
    case 2:
        Action-2;
        break;
    .
    .
    .
    case n:
        Action-n;
        break;
    default:
        default Action
}
```
* The allowed argument types for the switch statement are byte, short, char, int until 1.4 version. But, from 1.5 version onwards, corresponding wrapper classes and enum type also allowed. From 1.7 version onwards, String type also allowed.

|Version 1.4|Version 1.5|Version 1.7|
|-----------|-----------|-----------|
|byte|Byte|
|short|Short|
|char|Character|
|int|Integer|
||enum|String|
* Curly braces({}) are mandatory. Except switch, everywhere curly braces({}) are optional.
* 