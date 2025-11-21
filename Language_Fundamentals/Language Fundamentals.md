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
>3. Java identifiers are case sensitive. Ofcourse, Java language itself is treated as case sensitive programming language.
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
>5. We can not use reserved words as identifiers.
>>>**Ex:**
```java
public class Temp {
    public static void main(String[] args) {
        int x = 10; ✔
        int if = 20; ❌
    }
}
 ```
>6. All predefined java class names and interface names we can use as identifiers. But, 
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
>Ex:
```java
 enum month{
        Jan, Feb, Mar, Apr, May, Jun, Jul, Aug, Sep, Oct, Nov, Dec
}
```
Conclusions:
* All 53 reserved words in java contains only lower case alphabet symbols.
* In java, we have only new keyword and there is no delete keyword because, destruction of useless objects is the responsibilty of garbage collector.
* The following are new keyowrds in java:
    * strictfp - version 1.2
    * assert - version 1.4
    * enum - version 1.5
* strictfp but not strictFp
* instanceof but not instanceOf
* synchronized but not synchronize
* extends but not extend
* implements but not implement
* import but not imports
* const but not constant
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
* Because of above reasons, we can conclude java language is strongly typed programming language.
* Java is not considered as pure object oriented programming language because, several OOP features are not satisfied by java (like Operator Overloading, Multiple Inheritance, etc).
* Moreover, we are depending on primitive data types which are non-objects.
## Primitive Data Types
![alt text](image-1.png)
* Except boolean and char, remaining data types are considered as signed data types because, we can represent both positive and negative numbers.
### Byte:
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
          System.out.println(d);
          /*
          error: incompatible types: possible lossy conversion from int to byte
          byte d = 128;
                   ^
          */
          byte e = 10.5;
          System.out.println(e);
          /*
          error: incompatible types: possible lossy conversion from double to byte
          byte e = 10.5;
                   ^
           */
          byte f = true;
          System.out.println(f);
          /*
          incompatible types: boolean cannot be converted to byte
          byte f = true;
                   ^
           */
          byte g = "rudra";
          System.out.println(g);
          /*
          error: incompatible types: String cannot be converted to byte
          byte g = "rudra";
                   ^
           */
     }
     
}
```



















