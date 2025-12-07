# Flow Control
* *Flow control describes the order in which the statements will be executed* at runtime.

![alt text](image.png)
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
* The *argument to* the *if statement should be boolean* type. By mistake, *if* we are* trying to provide any other type* then, we *will get compile time error*.
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
* There is *no dangling else problem in java*. *Every else* is m*apped to the nearest if statment*.
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