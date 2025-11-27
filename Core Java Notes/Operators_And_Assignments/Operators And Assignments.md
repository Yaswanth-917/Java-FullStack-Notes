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

* We can apply increment and decrement operators only for variables. But, not for constant values. If we are trying to apply for constant values, then we will get compile time error.
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
* Nesting of increment and decrement operators not allowed.
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
* 

































































