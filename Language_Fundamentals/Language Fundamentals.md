# Language Fundamentals
>1. Identifiers
>2. Reserved Words
>3. Data Types
>4. Literals
>5. Arrays
>6. Type Of Variables
>7. var-arg Methods
>8. main Method
>9. Command Line Arguments
>10. Java Coding Standards
---
# Identifiers
* A name in java program is considered as **Identifier** which can be *used for identification purpose*.
* It can be a *Class name, Method name, Variable name or Label name*.
```java
public class Temp {
    public static void main(String[] args) {
        int x = 10;
    }
}
```
>* *Test* - Class name
>* *Main* - Method name
>* *String* - Predefined Java Class name
>* *args* - Array name
>* *x* - Variable name

## Rules For Defining Java Identifiers
>1. The only allowed characters in java identifiers are:
>>* a to z
>>* A to Z
>>* 0 to 9
>>* $
>>* _

>>If we are using any other character, we will get compile time error.
>>>**Ex:**
>>>>total_number ✔  
>>>>total# ❌
>2. Identifiers can not starts with digit.
>>>**Ex:**
>>>>total123 ✔  
>>>>123total ❌
>3. Java identifiers are **case sensitive**. Ofcourse, Java language itself is treated as **case sensitive programming language**.
>>>**Ex:**
```java
public class Temp {
    public static void main(String[] args) {
        int number = 10;
        int Number = 20;
        int NUMBER = 30; //We can differentiate with respect to case
    }
}
```
>4. There is no length limit for java identifiers. But, it is not recommended to take too lengthy identifiers.
>5. We **can not use reserved words** as identifiers.
>>>**Ex:**
```java
public class Temp {
    public static void main(String[] args) {
        int x = 10; ✔
        int if = 20; ❌
    }
}
 ```
>6. All predefined java class names and interface names we can use as identifiers. 
>>>**Ex:**
```java
public class Temp {
    public static void main(String[] args) {
        int String = 10;
        System.out.println(String);
        int Runnable = 999;
        System.out.println(Runnable);
    }
}
```
>>Even though it is valid, but it is not a good programming practice. Because, it reduces readability and creates confusion.

1. Which of the following are valid java identifiers
>>>* total_number ✔
>>>* total# ❌
>>>* 123total ❌
>>>* total123 ✔
>>>* ca$h ✔
>>>* $__$____$ ✔
>>>* all@hands ❌
>>>* Java2Share ✔
>>>* Integer ✔
>>>* Int ✔
>>>* int ❌
---
# Reserved Words
* In java some words are reserved to represent some meaning or functionality are called Reserved Words.
![alt text](image.png)
## Keywords For Datatypes (8):
>* byte
>* short
>* int
>* long
>* float
>* double
>* boolean
>* char
## Keywords For Flow Control (11):
>* if
>* else
>* switch
>* case
>* default
>* while
>* do
>* for
>* break
>* continue
>* return
## Keywords For Modifiers (11):
>* public
>* private
>* protected
>* static
>* final
>* abstract
>* synchronized
>* native
>* strictfp (Version 1.2)
>* transient
>* volatile
## Keywords For Exceptional Handling (6):
>* try
>* catch
>* finally
>* throw
>* throws
>* assert (Version 1.4)
## Keywords For Class Related (6):
>* class
>* interface
>* extends
>* implements
>* package
>* import
## Keywords For Object Related (4):
>* new
>* instanceof
>* super
>* this
## Keyword For Return Type (1):
>* void

* In java return type is mandatory. If a method won't return anything, then we have to declare that method with void return type.
* But in C language, return type is optional and default return type in int.
## Unused Keywords:
### goto:
>Usage of goto created several problems in old languages and hence, SUN people banned this keyword in java.
### const:
>Use final instead of const.  

Note: goto and const are unused keywords. If we are trying to use, we will get compile time error.
## Reserved Literals:
>* true, false - values for boolean data type
>* null - default value for object reference
## enum Keyword:
>* It is released in version 1.5
>* We can use enum to define a group of named constants.
>**Ex:**
```java
 enum month{
        Jan, Feb, Mar, Apr, May, Jun, Jul, Aug, Sep, Oct, Nov, Dec
}
```
**Conclusions:**
* All 53 reserved words in java contains only lower case alphabet symbols.
* In java, we have only new keyword and there is no delete keyword because, destruction of useless objects is the responsibilty of garbage collector.
* The following are new keyowrds in java:
    * strictfp - version 1.2
    * assert - version 1.4
    * enum - version 1.5
* *strictfp* but not strictFp
* *instanceof* but not instanceOf
* *synchronized* but not synchronize
* *extends* but not extend
* *implements* but not implement
* *import* but not imports
* *const* but not constant
1. which of the following list contains only java reserved words?
>>* new, ~~delete~~
>>* goto, ~~constant~~
>>* break, continue, return, ~~exit~~
>>* final, finally, ~~finalize~~
>>* throw, throws, ~~thrown~~
>>* ~~notify, notifyall~~
>>* implements, extends, ~~imports~~
>>* ~~sizeof~~, instanceof
>>* ~~instanceOf, strictFp~~
>>* byte, short, ~~Int~~
>>* None of the above ✔

2. Which of the following are java reserved words?
>>* public ✔
>>* static ✔
>>* void ✔
>>* main - name of the method
>>* String - its a predefined class
>>* args  -  name of the variable

# Data Types
* In java, every variable and every expression has some type.
* Each and every data type is clearly defined.
* Every assignment should be checked by compiler for type compatibility.
* Because of above reasons, we can conclude java language is **strongly typed programming language**.
* Java is not considered as **pure object oriented programming language because, several OOP features are not satisfied** by java (like Operator Overloading, Multiple Inheritance, etc).
* Moreover, we are depending on primitive data types which are non-objects.
## Primitive Data Types
![alt text](image-1.png)
* Except *boolean and char, remaining data types* are considered as *signed data* types because, we can represent both positive and negative numbers.
### byte:
* size: 1 byte (8 bits)
* MAX_Value: +127
* MIN_Value: -128
* Range: -128 to 127

![alt text](image-2.png) 
* The most significant bit act as sign bit.
* 0 means +ve number and 1 means -ve number
* Positive number will be represented directly in a memory, whereas negative numbers will be represented in 2's complement form.
```java
public class Temp {
     public static void main(String[] args) {
          byte b = 10;
          System.out.println(b); //10
          byte c =127;
          System.out.println(c); //127
          byte d = 128;
          /*
          error: incompatible types: possible lossy conversion from int to byte
          byte d = 128;
                   ^
          */
          byte e = 10.5;
          /*
          error: incompatible types: possible lossy conversion from double to byte
          byte e = 10.5;
                   ^
           */
          byte f = true;
          /*
          error: incompatible types: boolean cannot be converted to byte
          byte f = true;
                   ^
           */
          byte g = "rudra";
          /*
          error: incompatible types: String cannot be converted to byte
          byte g = "rudra";
                   ^
           */
     }
}
```
* *Byte* is the best choice if we want to handle data in terms of *streams* either from the file or from the network (File supported form or network supported form is byte).
### short:
* This is the most rarely used data type in java.
* size: 2 byte (16 bits)
* Range: -2<sup>15</sup> to 2<sup>15</sup>-1 => [-32768 to 32767]
```java
public class Temp {
    public static void main(String[] args) {
        short s = 32767;
        System.out.println(s);
        short t = 32768;
        /*
        error: incompatible types: possible lossy conversion from int to short
        short t = 32768;
                  ^
         */
        short u = 10.5;
        /*
        error: incompatible types: possible lossy conversion from double to short
        short u = 10.5;
                  ^
         */
        short v = true;
        /*
        error: incompatible types: boolean cannot be converted to short
        short v = true;
                  ^
         */
    }
}
```
* Short data type is best *suitable for 16-bit processors* like 8085. But, the processors are completely outdated and hence, corresponding short data type is also outdated data type.
### int
* The most commonly used data type in java is int.
* size: 4 bytes (32 bits)
* Range: -2<sup>31</sup> to 2<sup>31</sup>-1 => [-2147483648 to 2147483647]
### long
* Sometimes int may not enough to hold big values, then we should go for long type.

**Ex:**
1. The amount of distance travelled by light in 1000 days, to hold this value int may not enough. We should go for long data type.
>>>long l = 126000 * 60 * 60 * 24 *1000
2. The number of characters present in a big file may exceed int range. Hence, the return type of length method is long (but not int).
>>>long l = f.length()
* size: 8 bytes (64 bits)
* Range: -2<sup>63</sup> to 2<sup>63</sup>-1

**Note:**
* All the above data types(byte, short, int, long) meant for representing integral values.
* If we want to represent floating point values, then we should go for floating point data types.
## Floating Point Data Types
|                   |**float**         |**double**          |
|-------------------|:-----------------|--------------------|
|Accuracy           |5 to 6            |14 to 15            |
|Following Precision|Single Precision  |Double Precision    |
|Size               |4 bytes           |8 bytes             |
|Range              |-3.4e38 to 3.4e38 |-1.7e308 to 1.7e308 |
### boolean Data Type
* Size: Not applicable (virtual Machine Dependent)
* Range: Not applicable (But allowed values are true or false)
```java
public class Temp {
    public static void main(String[] args) {
        boolean b = true;
        boolean c = 0;
        /*
        error: incompatible types: int cannot be converted to boolean
        boolean c = 0;
                    ^
        */
       boolean d = True;
       /*
           error: cannot find symbol
           boolean d = True;
                       ^
        symbol:   variable True
        location: class Temp
       */
        boolean e = "True";
        /*
        error: incompatible types: String cannot be converted to boolean
        boolean e = "True";
        */
    }
}
```
```java
public class Temp {
    public static void main(String[] args) {
        int x = 0;
        int y = 1;
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
        while (y) {
            System.out.println("Bye");
        }
        /*
        error: incompatible types: int cannot be converted to boolean
        while (y) {
               ^
        */
    }
}
```
### char Data Type
* *Old languages (like C/C++)* are *ASCII* code based and the number of different allowed ASCII code characters are <= 256.
* To represent these 256 characters, 8 bits are enough. Hence, the size of char in old languages is 1 byte (8 bits).
* But **java** is **unicode** based and the number of different unicode characters are greater than 256 and less than or equal to 65536.
* To represent, these many characters 8 bits may not enough and compulsory we should go for 16 bits.
* Hence, the size of char is 2 bytes.
* size: 2 bytes
* Range: 0 to 65535
### Summary of Java Primitive Data Types
|Data Type|Size   |Range                                                                  |Wrapper Class|Default Value|
|---------|-------|-----------------------------------------------------------------------|-------------|-------------|
|byte     |1 byte |-2<sup>7</sup> to 2<sup>7</sup>-1 (128 to 127)                         |Byte         |0            |
|short    |2 bytes|-2<sup>15</sup> to 2<sup>15</sup>-1 (-32768 to 32767)                  |Short        |0            |
|int      |4 bytes|-2<sup>31</sup> to 2<sup>31</sup>-1 (-2147483648 to 2147483647)        |Integer      |0            |
|long     |8 bytes|-2<sup>63</sup> to 2<sup>63-1                                          |Long         |0            |
|float    |4 bytes|-3.4e38 to 3.4e38                                                      |Float        |0.0          |
|double   |8 bytes|-1.7e308 to 1.7e308                                                    |Double       |0.0          |
|boolean  |NA     |NA (But allowed values are true/false)                                 |Boolean      |false        |
|char     |2 bytes|0 to 65535                                                             |character    |" "          |

Note: *null* is the *default value for object reference* and we *can not apply for primitives*. If we are trying to use for primitive, then we will get compile time error.
```java
public class Temp {
    public static void main(String[] args) {
        char ch = null;
        /*
        error: incompatible types: <null> cannot be converted to char
        char ch = null;
                  ^
        */
    }
}
```
 



















