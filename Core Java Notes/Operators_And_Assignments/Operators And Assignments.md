# Operators & Assignments
1. Increment and Decrement Operators
2. Arithmetic Operators
3. String Concatenation Operator
4. Relational Operators
5. Equality Operators
6. instanceof Operator
7. bitwise Operators
8. short circuit Operators
9. type cast Operator
10. assignment Operators
11. consitional Operator
12. new Operator
13. [] Operator
14. operator precedence
15. Evaluation Order of Operands
16. new Vs newInstance()
17. instanceof Vs isInstance()
18. ClassNotFoundException Vs NoclassDefFoundError

# Increment and Decerement Operators
|Expression|Initial Value of x|Value of y|Final Value of x|
|----------|:----------------:|:--------:|:--------------:|
|y = ++x;  |10                |11        |11              |
|y = x++;  |10                |10        |11              |
|y = --x;  |10                |9         |9               |
|y = x--;  |10                |10        |9               |

* We *can apply increment and decrement operators only for variables*. But, *not for constant values*. If we are *trying to apply for constant values*, then we *will get compile time error*.
```java
public class Main {
    public static void main(String[] args) {
        int x = 10;
        int y = ++10;
        System.out.println(y);
        /*
        error: unexpected type
        int y = ++10;
                  ^
  required: variable
  found:    value
        */
        int z = ++x;
        System.out.println(z);  //11
    }
}
```
* *Nesting of increment and decrement operators not allowed*.
```java
public class Main {
    public static void main(String[] args) {
        int x = 10;
        int y = ++(++x);
        System.out.println(y);
        /*
        error: unexpected type
        int y = ++(++x);
                   ^
  required: variable
  found:    value
        */
    }
}
```
* *For final variables*, we *can not apply increment and decrement operators*.
```java
public class Main {
    public static void main(String[] args) {
        final int x= 10;
        x++;
        System.out.println(x);
        /*
        error: cannot assign a value to final variable x
        x++;
        ^
        */
    }
}
```
* We *can apply increment and decrement operators for every primitve type except boolean*.
```java
public class Main {
    public static void main(String[] args) {
        int x = 10;
        x++;
        char ch = 'a';
        ch++;
        double d = 10.5;
        d++;
        boolean b = true;
        b++;
        System.out.println(x);  //11
        System.out.println(ch); //b
        System.out.println(d);  //11.5
        System.out.println(b);
        /*
        error: bad operand type boolean for unary operator '++'
        b++;
         ^
        */
    }
}
```
## Difference Between b++ and b = b+1
* *If we apply any arithmetic operator between 2 variables* a and b, the *result type is* always *max(int, type of a, type of b)*.
```java
public class Main {
    public static void main(String[] args) {
        byte a =10;
        byte b = 20;
        byte c = a+b;
        System.out.println(c);
        /*
        error: incompatible types: possible lossy conversion from int to byte
        byte c = a+b;
                  ^
        */
       byte d = (byte)(a+b);
       System.out.println(d);   //30 
    }
}
```
```java
public class Main {
    public static void main(String[] args) {
        byte b = 10;
        b = b+1;
        System.out.println(b);
        /*
        error: incompatible types: possible lossy conversion from int to byte
        b = b+1;
             ^
        */
        byte c = (byte)(b+1);
        System.out.println(c);  //11
    }
}
```
* But, *in case of increment and decrement operators*, *internal typecasting will be performed automatically*.
>>b++ => (type of b)(b+1)
```java
public class Main {
    public static void main(String[] args) {
        byte b = 10;
        b++;
        System.out.println(b);  //11
    }
}
```

# Arithmetic Operators (+, -, *, /, %)
* *If we apply any arithmetic operator between 2 variables* a and b, the *result type is* always *max(int, type of a, type of b)*.
>* byte+byte = int
>* byte+short = int
>* short+short = int
>* byte+long = long
>* long+double = double
>* float+long = float
>* char+char = int
>* char+double = double

![alt text](image.png)
```java
public class Main {
    public static void main(String[] args) {
        System.out.println('a'+'b');    //195
        System.out.println('a'+0.89);   //97.89
    }
}
```
## Infinity
* *In integral arithmetic* (byte, short, int, long) there is *no way to represent infinity*. Hence, *if infinity is the result*, we *will get arithmetic exception* in integral arithmetic.
```java
public class Main {
    public static void main(String[] args) {
        System.out.println(10/0);
        //Exception in thread "main" java.lang.ArithmeticException: / by zero
    }
}
```
* But, *in floating point arithmetic* (float and double) there *is a way to represent infinity*. For this *Float and Double classes contains following 2 constants POSITIVE_INFINTY and NEGATIVE_INFINITY*. Hence, even though result is infintiy, we won't get any arithemtic exception in floating point arithmetic.
```java
public class Main {
    public static void main(String[] args) {
        System.out.println(10/0.0); //Infinity
        System.out.println(-10/0.0); //-Infinity
    }
}
```
## NaN (Not a Number)
* *In integral arithmetic* (byte, short, int, long) there is *no way to represent undefined results*. Hence, *if the result is undefined*, we *will get runtime exception saying arithmetic exception by zero*.
```java
public class Main {
    public static void main(String[] args) {
        System.out.println(0/0);
        //Exception in thread "main" java.lang.ArithmeticException: / by zero
    }
}
```
* But, *in floating point arithemtic* (float and double), there *is a way to represent undefined results*. For this, *Float and Double classes contains Nan constant*. Hence, if the result is undefined, we won't get any arithmetic exception in floating point arithmetic.
```java
public class Main {
    public static void main(String[] args) {
        System.out.println(0.0/0);  //NaN
        System.out.println(-0.0/0);  //NaN
    }
}
```
**Note:** *For any x value including NaN*, the *following expressions returns false*.
>* x<NaN
>* x<=NaN
>* x>NaN
>* x>=NaN
>* x==NaN
*For any x value including NaN*, the *following expression returns true*.
>* x!=NaN
```java
public class Main {
    public static void main(String[] args) {
        System.out.println(10<Float.NaN);           //false
        System.out.println(10<=Float.NaN);          //false
        System.out.println(10>Float.NaN);           //false
        System.out.println(10>=Float.NaN);          //false
        System.out.println(10==Float.NaN);          //false
        System.out.println(Float.NaN==Float.NaN);   //false
        System.out.println(10!=Float.NaN);          //true
        System.out.println(Float.NaN!=Float.NaN);   //true
    }
}
```
## Arithmetic Exception
* It is *Runtime Exceptio*n but *not compile time error*.
* It is *possible only in integral arithmetic* but *not in floating point arithmetic*.
* The only *operators which cause Arithmetic Excetion* are */* and *%*.







































































