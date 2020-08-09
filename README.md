# C_Notes
# C Programing Language

## About

> ### Year 
>
> Fall 2020
>
> ### Level
>
> Beginner and Advanced  

> # BY 
>
> ### A. S.  Eldesouky

## Topics  of  The Course 

[TOC]

*****

## Introduction 

### History of Computers

Before along time ago, there was no any programing language except binary representation **(0 & 1)** , so in this time, if we need to present a word like **"hello"** we represented like that .. **(01001000 01100101 0110110 0110110 00100001)**

### Why C

1. Portable (It can be run on any machine)

2. Less line of code (let's take an example) 

   ```c
   // adding 2 + 3
   //assembly					//C
   mov b,2						res = 2 + 3 ; 
   mov c,3
   ADD b,c
   mov res,b
   ```

###  Programing Language Level 

High level vs. Low level programing language 

- High level has less effort, so I don't know what the machine do and how my code run, like **Java & Python**
- Low level has more efforts, so I do every thing and put every value in the machine by myself, like **Assembly**

Here we need a meddle level between them so here we have the **Meddle level** programing language  

### Meddle Level Features 

1. Direct access to memory 
2. Using bitwise operators
3. Can write assembly language inside of code 

### Features of C

1. Procedural Programing 

2. Middle level language 

3. Popular choice for system level apps

4. C language facilitates a structured and disciplined approach to computer program 

5. Wide variety of built in functions, standard libraries and header files 

   ```c
   stdio.h / math.h / string.h / conio.h / stdlib.h / time.h / ctype.h
   scanf / printf / isdigit / sqrt / strcat / malloc 
   //and more of them
   ```

### First Application 

```c
#include <stdio.h> 
int main ()
{
    printf ("Hello World!")  ;
    return 0 ;
}
```

1. #include < >

   Here we doing a preprocessor process, this main "replaces text (starting with **#** with the actual content)"

   - Replace before the compilation begins 

   - Output of preprocessing is expanding source code

     <img src="https://bharathisubramanian.files.wordpress.com/2010/03/compile.png" alt="GCC Compilation Process | Bharathi Subramanian" style="zoom: 67%;" />

2. stdio.h (header file)

   - Standard input/output file
   - Contains declarations of functions like **printf & scanf**

3. int main () {     }   (function)

   We write here the body of our code and the compiler run the statement inside in it 

4. printf () 

   This function declaration set at header file that you included in begin of the code, and we use it to print a something in our screen (console window)

5. return 0 

   We write it to make sure the programing is ending

6. **;**

   This must written at the end of all statement in c language, it main the end of instructions

The output of this program is ...![1](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\1.PNG)

### Comment 

We used comments to help other people read and understand our program, but too many comments can make the program difficult to read, C compiler ignore the comments

1. One Line **// comment**
2. Bold one line **/// comment**
3. Multiple Line **/* comments */**
4. Documentation **/* *Dec1 *Dec2 *...*/** 

```c
// One Line Comment 

/// Bold one line comment

/*
Multiple 
Line
Comment 
*/

/*
* Dec 1
* Dec 2
* Dec 3
*/
```

*****

## Variables 

Variables like a cup and we put some values in it like the water in the cup, in reality, variables are names that points to some memory location in your machine, so let's go started 

<img src="https://www.atnyla.com/library/images-tutorials/variable-in-java-2.PNG" alt="Variable in C programming Language | atnyla" style="zoom:50%;" />

### Declaration

Announcing the properties of the variables to the compiler memory and we most declare the variables before we use 

> Properties: 1. size of variables		 2. name of the variables 

### Definition 

allocating memory to a variables 

> most of the time declaration and definition will be done at the same time, but not at all time, this depend on variables modifiers 

### How We Declare a variables 

```c
int var ;
```

1. int 

   - **Data Type:** how mush space a variables is going to occupy in memory
   - The size of <int> is depend on the machine **(2 bytes or 4 bytes)**

2. var 

   Name of variable, and we can name it whatever you like, but there is some rules we'll mention letter

### Initialization

We locate some values to the variable and we usually can change it letter at any place in our code

```c
#include <stdio.h>
int main ()
{
    int var = 3 ; 
    var = 5 ; 
    printf ("%d" , var) ;
    return 0 ;
}
```

> every variable can be declare one time in his scope, but we can able to use multilabel time in you program (variable scope)

The output of this program is ...![2](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\2.PNG)

You can also assign variable to another one 

```c
#include <stdio.h>
int main ()
{
    int var1 = 3 ; 
    int var2 ; 
    var2 = var1 ;
    printf ("%d" , var2) ;
    return 0 ;
}
```

The output of this program is ...![3](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\3.PNG)

You can also declare variables in one line and initialize them in another one

```c
#include <stdio.h>
int main ()
{
    int var1 , var2 , var3 ; 
    var1 = var2 = var3 = 4 ;
    printf ("%d" , var1) ;
    printf ("%d" , var2) ;
    printf ("%d" , var3) ;
    return 0 ;
}
```

The output of this program is ...![4](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\4.PNG)

### Variables Naming Rules

Variable name: composed of **Letters** or combination of **Letters & digits** 

1. Don't start variables name with digit 
2. Beginning with underscore is valid but not recommended, but we can use it between the variable name
3. UPPERCASE letters different from lowercase letters, because C language is case sensitive
4. special characters and Blanks or white spaces not allowed **(@ , # , % , ^ , & , * , - , , ...)**
5. Don't use C keywords to name your variables **(if , else , for , while , int , double , ...)**, but you can use them if you change one letter to UPPERCASE
6. Using looooooooooooooonnnnnnggggg name is not recommended, because it'll difficult to used again 

### Scope of Variables 

- **Definition of Scope**

  The area under which a variable is applicable or alive (scope = lifetime), or we can say strictly, a block or a region where a variable is **declared, defined and used**, and when a block or region ends .. variable is automatically **destroyed** 

  ```c
  // note what's happened  
  #include <stdio.h>
  int main ()
  {
      int var = 33 ;
      printf ("%d", var) ;
      return 0 ;
  }
  int fun ()
  {
      printf("%d", var)
  }
  ```

  Error message ... ![14](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\14.PNG)

  > - **int var = 33 ;**
  >
  >   scope of the variable is within **main()** function, is called **Local** to main() function 
  >
  > - The error happened because in **fun()** function, we trying to access variable **var** outside **main()** function

- **Local Variables**

  Is a variable defined inside function or block, let's see some example ... 

  ```c
  /* contents of outer block upto this **flag** are visible to the internal block,
     because the internal block is a part from the outer block, but we need to know,
     contents of internal block are not visible to the outer block
  */
  {
      .....
      //flag
      {
          .....
      }
  }
  
  // contents of any of these blocks is not visible to any blocks outside these blocks 
  {
      .....
  }
  {
      .....
  }
  ```

  ```c
  #include <stdio.h>
  int main ()
  {
      int var = 33 ;
      int var = 43 ;
      printf ("%d", var) ;
      printf ("%d", var) ;
      return 0 ;
  }
  ```

  Error message ... ![](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\15.PNG) we can't declare and define the same variable in same scope

  ```c
  #include <stdio.h>
  int main ()
  {
      int var = 33 ;
      {
          int var = 43 ;
          printf ("%d", var) ;
      }
      printf ("%d", var) ;
      return 0 ;
  }
  ```

  The output of this program is ... ![16](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\16.PNG)

- **Global Variables**

  Is a variable defined outside all function and blocks, let's see some example ... 

  ```c
  int Global_Variable ; 
  {
      .....
      {
          .....
          {
              .....
          }
      }
  }
  {
      .....
  }
  {
      .....
  }
  // all of this black can use *Global_Variable*
  ```

  ```c
  #include <stdio.h>
  int fun () ; 
  int var = 10 ;
  int main ()
  {
      int var = 33 ;
      printf ("%d\n", var) ;
      fun() ;
      return 0 ;
  }
  int fun()
  {
      printf ("%d\n", var) ;
  }
  ```

  The output of this program is ... ![17](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\17.PNG)

  > we'll know about fun() function letter, and how we can create and use functions

### Modifiers

There're five type of modifiers in C:	1.Sign		2.Storage 		3.Size 		4.Constant 		5.Volatiity 

1. **Sign Modifiers**

   - **Signed**

     Can hold negative and positive numbers

   - **Unsigned**

     Can hold only zero and positive numbers

2. **Storage Modifiers**

   - **Auto** 

     Auto main Automatic, variables declared inside a scope by default are automatic variables, after variable scope the variable is destroyed and this gives us the advantage that it does not waste any memory

     - There's no different between **auto int var ;** and **int var ;**

     - If you wants to initialize auto variable, by default it will be initialized with some garbage (random) value

     - Global variable by default initialized to **0**  

       ```c
       #include <stdio.h>
       int fun () ;
       int var ;
       int main ()
       {
           auto int var ;
           printf ("%d\n", var) ;
           fun() ;
           return 0 ;
       }
       int fun()
       {
           printf ("%d\n", var) ;
       }
       ```

       The output of this program is ...![18](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\18.PNG)

   - **Extern** 

     Previously when we talk about **declaration and definition**, we said *"most of the time declaration and definition will be done at the same time, but not at all time, this depend on variables modifiers"* , so here, when we use **extern** we just declared the variables and tell the compiler don't reserve any bit of memory, because the variable already there in some file in my project 

     - Extern is short name for external 
     - Used when a particular file needs to access a variable from another file 

     ```c
     //main.c
     #include <stdio.h>
     extern int var ;
     int main ()
     {
         printf ("%d\n", var) ;
         return 0 ;
     }
     ```

     ```c
     //others.c
     int var = 10 ;
     ```

     The output of this program is ...![19](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\19.PNG)

     > - This progress done by the linker not the compiler 
     > - You can declare the variable mutable time in your code but not able to defined 
     > - If you initialize extern variable, the memory for this variable is allocated and it will be considered defined 
     > - When we use extern modifier the compiler search for the value of the variable inside the same file then the other files in the program 
     > - If there's no such variable exist the compiler produce no error, but the linker throws an error

     

   - **Register**

     ![Memory Organization | Computer Architecture Tutorial | Studytonight](https://www.studytonight.com/computer-architecture/images/memory-heirarchy.png)

     Register keyword hints the compiler to store a variable in register memory, this's done because access time reduces greatly for most frequently referred variables, this's the choice of compiler whether is pits the given variable in register or not, usually compiler themselves do the necessary optimizations

     > **Syntax:** register Some_data_type Some_variable_name ; 

     

   - **Static**

     Let's take some examples before we started ...

     ```c
     // main.c
     #include <stdio.h>
     
     int main ()
     {
         int var ;
         var = increment () ;
         var = increment () ;
         var = increment () ;
         printf ("%d\n", var) ;
         return 0 ;
     }
     ```

     ```c
     // others.c
     int increment ()
     {
         int count = 0 ;
         count = count  + 1 ;
         return count ;
     }
     ```

     The output of this program is ...![20](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\20.PNG)

     > Here the output is **1** because every time we called the function the variable **count** is declared and initialized to **0** and incremented by **1**, so there's no different

      

     ```c
     // main.c
     #include <stdio.h> 
     int main ()
     {
         int var ;
         var = increment () ;
         var = increment () ;
         var = increment () ;
         count = count + 3 ;
         var = count ;
         printf ("%d\n", var) ;
         return 0 ;
     }
     ```

     ```c
     // others.c
     int count ;
     int increment ()
     {
         count = count  + 1 ;
         return count ;
     }
     ```

     The output of this program is ...![21](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\21.PNG)

     > Here the output is **3** because we make the variable **count** Global variable, so every time we called the function, it'll be incremented by **1**, and we call it three time

     

     ```c
     // main.c
     #include <stdio.h>
     extern int count ;
     int main ()
     {
         int var ;
         var = increment () ;
         var = increment () ;
         var = increment () ;
         printf ("%d\n", var) ;
         return 0 ;
     }
     ```

     ```c
     // others.c
     int count = 0 ;
     int increment ()
     {
         count = count  + 1 ;
         return count ;
     }
     ```

     The output of this program is ...![22](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\22.PNG)

     >  Here we have a problem, because variable **count** is visible to all file in the program and we can change it, there's no security here, and this's disadvantage for your program 

     So we had to think about solving the security problem, and for that there's **static** modifier to solve this problem

     Static make the variable in his file only and you can't access it at any file in you program 

     ```c
     // main.c
     #include <stdio.h>
     extern int count ;
     int main ()
     {
         int var ;
         var = increment () ;
         var = increment () ;
         var = increment () ;
         printf ("%d\n", var) ;
         return 0 ;
     }
     ```

     ```c
     // others.c
     static int count ;
     int increment ()
     {
         count = count  + 1 ;
         return count ;
     }
     ```

     Error message ...![23](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\23.PNG)

     - When you declared **Local static variable** it will be act like **Global static variable** but in his **scope only**, in strictly word, this variable only available in his scope 
     - static variable assigned to constant values only, if you assigned to any variable or functions return, you got an error 
     - static variables remains in memory even it's declared within a block

3. **Size Modifiers**

   - **Short**

     It limits user to store small integer values from -32768 to 32767, it can be used only on **int** data type

   - **Long**

     It allows user to stores very large number (something like 9 Million Trillion) from -9223372036854775808 to 9223372036854775807,  it can be used only on **int & double** data types

     > Syntax “long long” is used instead of “long int”

   

4. **Constant Modifiers**

   Constant main: something that never change, ones you defined can't be modified later in code 

   - **Const**

     ```c
     //const Some_data_type Some_variable_name ; 
     #include <stdio.h>
     int main ()
     {
         const int var = 57 ;
         printf ("%d\n", var) ;
         return 0 ;
     }
     ```

     The output of this program is ...![29](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\29.PNG)

     ```c
     //const Some_data_type Some_variable_name ; 
     #include <stdio.h>
     int main ()
     {
         const int var = 57 ;
         var = 20 ;
         printf ("%d\n", var) ;
         return 0 ;
     }
     ```

     Error message ...![30](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\30.PNG)

     > We can declare the const variable as Global variable and there's no function can be able to change it

     

5. **Volatility Modifiers**

   - **Volatile**

     C's volatile keyword is a qualifier that is applied to a variable when it is declared, it tells the compiler that the value of the variable may change at any time without any action being taken by the code the compiler finds nearby

     This keyword used in Embedded Systems a lot  


******

## Basic Output Function - printf ()

Let's take a look at different print statement 

```c
#include <stdio.h>
int main ()
{
    int var1 , var2 , var3 ; 
    var1 = 3 , var2 = var3 = 4 ;
    printf ("Hello World!") ;
    printf ("%d" , var1) ;
    printf ("%d%d" , var2 , var3) ;
    return 0 ;
}
```

The output of this program is ...![5](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\5.PNG)

 >**%d** is placeholder for variable (take the second argument at printf and replace me with it)
 >
 >**d** main decimal 

example 

```c
#include <stdio.h>
int main ()
{
    int two = 2 , three = 3 , six = 6 ;
    int res = (two + three) * six / three ;
    printf("i know how to write this expression: (%d + %d) * %d / %d ", two, three, six, three) ;
    printf("and the result = %d" , res) ;
}
```

The output of this program is ...![6](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\6.PNG)

******

## Basic Input Function - scanf ()

Stands for Scan Formatted String, accept character, string and numeric data from the user using standard input (keyboard), scanf() also use format specifiers same as printf(), like %d, %c and %s 

- Take integer from user 

  ```c
  #include <stdio.h>
  int main ()
  {
      int var ;
      scanf("%d", &var) ;
      return 0 ;
  }
  ```

  > **&** is so important 

- Why **&**

  Because we need to save this input data,  scanf () function need to know the memory location of the variable, so that's the role of **&**, and also **&** called as **address-of** operator 

  > We'll this topic strictly in **Pointers**

- Example 

  ```c
  #include <stdio.h>
  int main ()
  {
      int var1 , var2 ;
      printf("Please Enter Number 1: ") ;
      scanf("%d", &var1) ;
      printf("Please Enter Number 2: ") ;
      scanf("%d", &var2) ;
      printf("Sum of Number 1 and Number 2 = %d" , var1 + var2) ;
      return 0 ;
  }
  ```

  The output of this program is ...![31](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\31.PNG)
  
  > You must take space before **%c** to avoid the bug in scanf()
  >
  > ```c
  > char c1 , c2 ;
  > printf ("Enter a charcter 1: ")
  > scanf (" %c" , &c1) ;
  > printf ("Enter a charcter 2: ")
  > scanf (" %c" , &c2) ;
  > ```

******

## Data Types

Data type it is divided into 3 sections: 

1. Primitive

   int - char - float - double - void (function return , function input , void pointer)

2. Userdefind 

   struct - union - enum 

   Later, we'll take about it in separate section 

3. Derived

   Function - Array - Pointer

   Later, we'll take about each of them separately 

In this section we'll take about primitive data type

### integer

- The size of Integer is depend on the machine **(2 bytes or 4 bytes)**

- We can find the size of integer in our machine using **sizeof()** operator 

  ```c
  #include <stdio.h>
  int main ()
  {
      printf("%d" , sizeof(int)) ;
      return 0 ;
  }
  ```

  The output of this program is ...![7](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\7.PNG)

- **Range** is upper and lower limit of some set of data 

  Examples (find the range) 

  1. {0, 1, 2, 3, 4}	          Range: 0 to 4
  2. 4 bit data                    Range: 0 to 15
  3. signed 2 bytes            Range: -32768 to 32767
  4. unsigned 2 bytes        Range: 0 to 65535
  5. signed 4 bytes            Range: -2147483648 to 2147483647
  6. unsigned 4 bytes        Range: 0 to 4294967295

- **Modifier Integer** (short, long, signed, unsigned) 

  1. If integer is 4 bytes, then short maybe 2 bytes
  2. If integer is 4 bytes, then long maybe 8 bytes
  3. sinned integer variables is defined by default and has positive and negative values
  4. unsigned integer allows only positive values and you must write it like that **(unsigned int)**
  5. If **sizeof(long int)** = 4 bytes, then **sizeof(long long int)** = 8 bytes
  6. If **sizeof(long int)** = 8 bytes, then **sizeof(long long int)** = 8 bytes
  7. **%d** is used to print "signed integer"
  8. **%u** is used to print "unsigned integer"
  9. **%ld** is used to print "signed long integer"
  10. **%lu** is used to print "unsigned long integer"
  11. **%lld** is used to print "signed long long integer"
  12. **%llu** is used to print "unsigned long long integer"

- **Exceeding the valid Range** 

  It'll be return again to beginning and start counting like the clock or cycle

  ```c
  #include <stdio.h>
  int main ()
  {
      int var1 = 2147483648  ;
      printf("%d\n" , var1) ;
      int var2 = -2147483649  ;
      printf("%d\n" , var2) ;
      unsigned int var3 = 4294967296  ;
      printf("%u\n" , var3) ;
  }
  ```

  The output of this program is ...![8](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\8.PNG)

### Character

- **Char Represented at ASCII table** 

  <img src="https://i.pinimg.com/originals/75/28/b1/7528b199208cc9078adfa6830be7f072.jpg" alt="ASCII Table PDF | Ascii, Coding, Pdf" style="zoom: 25%;" />

- **Declaration and Initialization** 

  ```c
  //char some_variable_name = 'value' ; 
  #include <stdio.h>
  int main ()
  {
      char c1 = 65 ;
      char c2 = 'A' ;
      printf("%c\n", c1) ;
      printf("%c\n", c2) ;
      printf("%d\n", c1) ;
      printf("%d\n", c1) ;
  }
  ```

  The output of this program is ...![9](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\9.PNG)

  > - If we use **%c** and don't use **' '** so this's depend on your compiler to be integer or character 
  > - If we use **%d** it'll be represented like integer number 

- **Size and Range of Character**

  - size: 1 byte = 8 bits 

  - range: 

    1. unsigned: 0 to 255
    2. signed: -128 to +127

    > there's **Extended ASCII table** for the other 8 bits in unsigned char 
    >
    > <img src="https://theasciicode.com.ar/american-standard-code-information-interchange/ascii-codes-table.png" alt="The complete table of ASCII characters, codes, symbols and signs ..." style="zoom:50%;" />

- **Signed and Unsigned**

  When we convert char from signed to unsigned representation, we're doing like exceeding the range, let's take example and see 

  ```pseudocode
  -128 = 0b10000000 and +128 = 0b10000000
  -127 = 0b10000001 and +129 = 0b10000001
  -126 = 0b10000010 and +130 = 0b10000010
  .
  .
  -1 = 0b11111111 and +255 = 0b11111111
  ```
  
  ![sc](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\sc.jpeg)

### Float, Double and Long Double

For representing fractional number (3.14, 0.654, -324.56, 0.00000015)

- **Size** (depend on the machine)

  1. float: 4 bytes = 32 bits
  2. double: 8 bytes = 64 bits
  3. long double: 12 bytes = 96 bits

- **Represent Fraction Number**

  1. float: IEEE 754 single precision floating point 
  2. double: IEEE 754 double precision floating point
  3. long double: extended precision floating point 

- **Fixed and Floating point**

  <img src="C:\Users\A-ELDESOUKY\AppData\Roaming\Typora\typora-user-images\image-20200715015703312.png" alt="image-20200715015703312" style="zoom: 50%;" />

- **Precision**

  1. float: 6 digit after point 
  2. double: 15 digit after point 
  3. long double: 18 digit after point

- **Using float Data Type**

  ```c
  #include <stdio.h>
  int main ()
  {
      // note the different 
      int var = 9 / 4 ;
      float var1 = 9 / 4 ;
      float var2 = 9.0 / 4.0 ;
      float var3 = 9.0 / 4 ;
      printf("%0.2f\n", var) ;
      printf("%0.2f\n", var1) ;
      printf("%0.2f\n", var2) ;
      printf("%0.2f\n", var3) ;
      return 0 ;
  }
  ```

  The output of this program is ...![10](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\10.PNG)

- **%f** is used to print "float"

- **%lf** is used to print "double"

- **%lLf** is used to print "long double"

> We use **%.number_of_fraction fraction_data_type** to print a specific fraction number after the decimal point
>
> ```c
> printf ("%.3f" , 5.47926) ;				// prints 5.479
> printf ("%.6lf" , 5.48963583) ;			// prints 5.489635
> printf ("0.10lLf", 6.59712364789521)	// prints 6.5971236478
> ```

### Void

There're three usage for void data type 

1. function return
2. function input
3. void pointer

We'll take about each of them in their sections 

### typedef

We use it to create a new name for any data type in C, it gives the user the freedom to create their own types

```c
typedef old_data_type new_data_type ;
```

```c
typedef int INTEGER ;	// Now I can use INTEGER instead of int 
INTEGER var = 10 ;
printf ("%d" , var) ; 	// prints 10
```

There's a great usage for **typedef**, as we take in variables some of it's compiler depends or machine depends for their size, so if we write a code on a compiler have a specific sizes for the primitive data type and need to run our code in another compiler have biggest sizes for the the primitive data type, then it will be consuming the memory for something I don't need it, therefore we use **typedef** to declare our data type as a bits, then change it to be suitable in any compiler our machine I use it, that make your code **more portable**

```c
// this work in gcc compiler and 64 bit machine 
typedef unsigned char uint8 ; 
typedef signed char int8 ;

typedef unsigned short uint16 ;
typedef signed short int16 ;

typedef unsigned long uint32 ;
typedef signed long int32 ;

typedef unsigned long long uint64 ;
typedef signed long long int64 ;

typedef float float32 ;
typedef double float64 ;
```

We use typedef in many places, but the same concept, we'll see that in previous sections 

### Typecasting

Converting one datatype into another is known as type casting or, type-conversion. For example, if you want to store a 'double' value into a simple integer then you can type cast 'double' to 'int'. You can convert the values from one type to another explicitly using the **cast operator** 

```pseudocode
(new type name) variable_name ; 
```

```c
#include <stdio.h>
int main ()
{
    int x = 10 ;
    printf ("%d\n" , x / 3) ;
    printf ("%lf\n" , (double)x / 3) ;
}
```

The output of this program is ...![114](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\114.PNG)

### Data Type Range 

This's values depends from machines to machines or compilers 

- Integer Types

  |      Type      |     Size     |                        Range                         |
  | :------------: | :----------: | :--------------------------------------------------: |
  |      char      |    1 byte    |               -128 to 127 or 0 to 255                |
  | unsigned char  |    1 byte    |                       0 to 255                       |
  |  signed char   |    1 byte    |                     -128 to 127                      |
  |      int       | 2 or 4 bytes | -32,768 to 32,767 or -2,147,483,648 to 2,147,483,647 |
  |  unsigned int  | 2 or 4 bytes |          0 to 65,535 or 0 to 4,294,967,295           |
  |     short      |   2 bytes    |                  -32,768 to 32,767                   |
  | unsigned short |   2 bytes    |                     0 to 65,535                      |
  |      long      |   8 bytes    |     -9223372036854775808 to 9223372036854775807      |
  | unsigned long  |   8 bytes    |              0 to 18446744073709551615               |

- Floating-Point Types

  |    Type     |   Size   |          Rang          |     Precision     |
  | :---------: | :------: | :--------------------: | :---------------: |
  |    float    | 4 bytes  |   1.2E-38 to 3.4E+38   | 6 decimal places  |
  |   double    | 8 bytes  |  2.3E-308 to 1.7E+308  | 15 decimal places |
  | long double | 10 bytes | 3.4E-4932 to 1.1E+4932 | 19 decimal places |

******

## Questions Set 1

### Question 1

What the output of the following c program 

```c
#include <stdio.h>
int main ()
{
    int var = 052 ;
    printf("%d" , var) ;
    return 0 ;
}
```

a) 52 

b) 56

**c) 42**

d) Compiler error

> If we add **0** before the value it represented as octal number 

### Question 2

What the output of the following c program 

```c
#include <stdio.h>
int main ()
{
    int var = 052 ;
    printf("%o" , var) ;
    return 0 ;
}
```

**a) 52 **

b) 56

c) 42

d) Compiler error

> If we use **%o** it'll be represented like octal number 

### Question 3

What the output of the following c program 

```c
#include <stdio.h>
#define STRING "%s\n"
#define NOTES "welcome to C notes by Abdelrahman Eldesouyk!"
int main ()
{
    printf(STRING, NOTES) ;
    return 0 ;
}
```

**a) welcome to C notes by Abdelrahman Eldesouyk! **

b) compiler error

c) garbage value

d) "welcome to C notes by Abdelrahman Eldesouyk!"

> - If we use **%s** it'll be represented string to the screen
> - String must be in double quotes 

### Question 4

What the output of the following c program

```c
#include <stdio.h>
int main ()
{
    int var = 0x04AF ;
    printf("%x" , var) ;
    return 0 ;
}
```

The output of this program is ...![32](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\32.PNG)

> - If we use **%x** it'll be represented like hexadecimal number with lower case letters
> - If we use **%X** it'll be represented like hexadecimal number with UPPER case letters
> - When we initialize hexadecimal number, we can use **0x** or **0X**
> - If we change **%X** to **%d** the output will be a decimal 

### Question 5

What the output of the following c program

```c
#include <stdio.h>
static int i ;
static int i = 27 ;
static int i ;
int main ()
{
    static int i ;
    printf("%d" , i) ;
    return 0 ;
}
```

before we solve it we need to see this picture ...

![Memory Layout Of C Program - EmbHack](https://i1.wp.com/www.embhack.com/wp-content/uploads/2018/06/memory_layout_of_c_program.png)

> - **static int i ;** it save in **bss** 
> - **static int i = 0 ;** it save in **bss** 
> - **static int i = 27 ;** it save in **data** 
> - **static int i ; static int i = 27 ;** it save in **data** and no change in **bss**
> - **static int i ; static int i = 27 ;  static int i = 22 ;** we'll have **re-definition error**, because there's to two time we initialize the same variables 
> - **static int i ; static int i = 27 ;  static int i = 0;** we'll have **re-definition error**, because there's to two time we initialize the same variables, we initialize **static int i = 0;** to **0** by ourselves not by **bss**
> - **static int i ;  static int i ;** it save in **bss** and no errors 
> - Inside the main () function we can re-defined the variable **i** depend on scope behavior 

The output of this program is ...![33](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\33.PNG)

### Question 6

What the output of the following c program 

```c
#include <stdio.h>
int main ()
{
    printf ("%d" , printf("%s", "Hello World!")) ;
    return 0 ;
}
```

- **%s** is used to print "string"
- printf not only prints the content on the screen, it also returns the number of character that it successfully prints on the screen 

The output of this program is ... ![11](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\11.PNG)

### Question 7

What the output of the following c program 

```c
#include <stdio.h>
int main ()
{
    printf ("%10s" , "Hello") ;
    return 0 ;
}
```

The output of this program is ... ![12](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\12.PNG)

### Question 8

What the output of the following c program 

```c
#include <stdio.h>
int main ()
{
    char c = 255 ; 
    c = c + 10 ;
    printf ("%d" , c) ;
    return 0 ;
}
```

The output of this program is ... ![](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\13.PNG)

### Question 9

Which of the following statement is correct integer name 

```c
1. signed int i ;
2. signed i ;		//the compiler assumed it's integer 
3. unsigned i ;		//the compiler assumed it's integer 
4. long i ;
5. long int i ;
6. long long i ;
```

a) only 1 and 5

b) only 1

**c) All are correct**

d) only 4, 5, 6

### Question 10

What dose the following c program print

```c
#include <stdio.h>
int main ()
{
    unsigned i = 1 ; 
    int j = -4 ;
    printf ("%u" , i + j) ;
    return 0 ;
}
```

a) garbage

b) -3

**c) depend on machine**

d) none of the above

*****

## Operators 

### Operators type in C

1. Arithmetical Operator (Binary)
2. Arithmetical Operator (Unary)
3. Relational Operator 
4. Logical Operator 
5. Bitwise Operator 
6. Assignment Operator 
7. Escape Operator
8. Others

### Arithmetical Operators (Binary)

- Operator

  Two operand are required to preform operation 

  1. Addition **+**

     To add to number together 

  2. Subtraction **-**

     To subtract to number together 

  3. Multiplication *****

     To multiplicate to number together 

  4. Division **/**

     To divide to number together 

  5. Modules **%**

     To get the reminder of division from divide number together

     > We can also make modules for negative number but we need to make the general formula
     >
     > **General Formula** 
     >
     > A % B = A - (dec(A / B) * B) 
     >
     > But we can conclude that, if the Numerator is negative, we put a negative sign for (|A| % |B|), Otherwise we deal without negative signs

- Precedence and Associativity

  | Precedence |    Operators     | Associativity |
  | :--------: | :--------------: | :-----------: |
  |  Level 1   | brackets **( )** |     ----      |
  |  Level 2   |    * , / , %     | Left to Right |
  |  Level 2   |      + , -       | Left to Right |

  > Associativity is used only when two or more operators at the same Precedence (level)

  ```c
  #include <stdio.h>
  // note the different 
  int main ()
  {
      int a = 2 , b = 3 , c = 4 , d = 5 ;
      printf("a * b / c = %d\n" , a * b / c) ;
      printf("a + b - c = %d\n" , a + b - c) ;
      printf("a + b * d - c %% a = %d" , a + b * d - c % a) ;
      return 0 ;
  }
  ```

  The output of this program is ...![34](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\34.PNG)

  > We use **%%** because if we write just **%** the compiler think it's a place holder 

### Arithmetical Operators (Unary)

- Operator

  One operand are required to preform operation 

  1. Increment **++**

     Increment the variable by one (var++ like var = var + 1)

  2. Decrement **--**

     decrement the variable by one (var-- like var = var - 1)

- pre-operator 

  means first increment or decrement then assign to another variable, the operation done before the operand 

- post-operator

  means first assign to another variable then increment or decrement, the operation done after the operand 

- You can't use **rvalue** before of after increment or decrement operator 

  <img src="C:\Users\A-ELDESOUKY\AppData\Roaming\Typora\typora-user-images\image-20200715214104663.png" alt="image-20200715214104663" style="zoom:50%;" />

- Lexical Analysis

  <img src="C:\Users\A-ELDESOUKY\AppData\Roaming\Typora\typora-user-images\image-20200715222739650.png" alt="image-20200715222739650" style="zoom:50%;" />

  ```c
  #include <stdio.h>
  int main ()
  {
      int a = 2 , b = 3 ;
      printf("%d" , a+++b) ; 
      return 0 ;
  }
  ```

  1. at **a** the left is equal **+**, so it will be (a)(+++b)
  2. at **+** the left is equal to **+** and we have **++** in C programing, so it will be (a)(++)(+b) 
  3. at **+** the left is equal to **b**, so it will be (a)(++)(+)(b)
  4. there's no thing after **b**, so it'll be returned the equation
  5. the equation (a)(++)(+)(b) is right

  The output of this program is ...![35](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\35.PNG)

  ```c
  #include <stdio.h>
  int main ()
  {
      int a = 2 , b = 3 ;
      printf("%d" , a + ++b) ; 
      return 0 ;
  }
  ```

  1. at **a** the left is equal space, so it will be (a)(+ ++b)
  2. at **+** the left is equal to space, so it will be (a)(+)(++b) 
  3. at **+** the left is equal to **+** and we have **++** in C programing, so it will be (a)(+)(++)(b)
  4. there's no thing after **b**, so it'll be returned the equation
  5. the equation (a)(++)(+)(b) is right

  The output of this program is ...![36](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\36.PNG)

  ```c
  #include <stdio.h>
  int main ()
  {
      int a = 2 , b = 3 ;
      printf("%d" , a+++++b) ; 
      return 0 ;
  }
  ```

  1. at **a** the left is equal space, so it will be (a)(+++++b)
  2. at **+** the left is equal to **+** and we have **++** in C programing, so it will be (a)(++)(+++)(b)
  3. at **+** the left is equal to **+** and we have **++** in C programing, so it will be (a)(++)(++)(+b)
  4. at **+** the left is equal to **b**, so it will be (a)(++)(+)(b)
  5. there's no thing after **b** the equation
  6. the equation (a)(++)(+)(b) is wrong

  Error message...![37](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\37.PNG)

### Relational Operation

Used to compare two values and return **True or False**

1. Equal **==**

   To check equally between two number

2. Not Equal **!=**

   To check not-equally between two number 

3. Less Than or Equal **<=**

   To check the lowest or equally between two number

4. Greater Than or Equal **>=**

   To check the greatest or equally between two number

5. Less Than **<**

   To check the lowest between two number

6. Greater Than **>**

   To check the greatest between two number

> False = 0 
>
> True = Anything rather than 0, Most often return 1

### Logical Operators

return **True or False**

1. AND **&&**

   return True when all conditions under consideration is True, and return False when any of conditions is False 

2. OR **||**

   return True when any of conditions is True, and return False when all conditions under consideration are any of conditions is False 

3. NOT **!**

   return True when conditions is False, and return False is True

> False = 0 
>
> True = Anything rather than 0, Most often return 1

### Bitwise Operators

It dose **Bitwise Manipulation**

- Operator

  1. AND **&**

     - It takes two bits at a time and preform AND operation 

     - AND (&) is a binary operator, it takes two number and preform bitwise AND

     - Result of AND is 1 when both bits are 1 (Like Multiplication)

       |  A   |  B   |  &   |
       | :--: | :--: | :--: |
       |  0   |  0   |  0   |
       |  0   |  1   |  0   |
       |  1   |  0   |  0   |
       |  1   |  1   |  1   |

     - We use it to make bit **X** equal 0, and I didn't know what the value for **X** (Clearing)

  2. OR **|**

     - It takes two bits at a time and preform OR operation 

     - OR (|) is a binary operator, it takes two number and preform bitwise OR

     - Result of OR is 0 when both bits are 0 (Like Summation)

       |  A   |  B   |  &   |
       | :--: | :--: | :--: |
       |  0   |  0   |  0   |
       |  0   |  1   |  1   |
       |  1   |  0   |  1   |
       |  1   |  1   |  1   |

     - We use it to make bit **X** equal 0, and I didn't know what the value for **X** (Setting)

  3. NOT **~**

     - It's job to complement each bit one by one

     - NOT (!) is a unary operator, it takes one number and preform bitwise NOT

     - Result of NOT is 1 when bit are 0, and 0 when bit are 1

       |  A   |  &   |
       | :--: | :--: |
       |  0   |  1   |
       |  1   |  0   |

     - We use it to reverse all bits from 1 to 0 or 0 to 1

  4. XOR **^**

     - It takes two bits at a time and preform XOR operation 

     - XOR (^) is a binary operator, it takes two number and preform bitwise XOR

     - Result of XOR is 0 when both bits are equal

       |  A   |  B   |  &   |
       | :--: | :--: | :--: |
       |  0   |  0   |  0   |
       |  0   |  1   |  1   |
       |  1   |  0   |  1   |
       |  1   |  1   |  0   |

     - We use it to reverse the bit **X** from 1 to 0 or 0 to 1, and I didn't know what the value for **X** (Toggling)

  5. Left Shift **<<**

     - It takes two bits at a time and preform Left Shift operation 
     - Left Shift (<<) is a binary operator, it takes two number and preform bitwise Left Shift
     - Result of Left Shift is equal (number * 2^shift)
     - We shifted all bits to the left and put **0** instead of the missing bits

  6. Right Shift **>>**

     - It takes two bits at a time and preform Right Shift operation 
     - Right Shift (>>) is a binary operator, it takes two number and preform bitwise Right Shift
     - Result of Left Shift is equal (number / 2^shift)
     - We shifted all bits to the right and put **0** instead of the missing bits

- Different between **Logical & Bitwise** operator 

  ```c
  #include <stdio.h>
  int main ()
  {
      int a = 1 , b = 2 ;
      if (a & b)                // 1 = 0b00000001 , 2 = 0b00000010 , 1 & 2 = 0b00000000 = 0 = False
          printf("x & y is True") ;
      if (a && b)              // 1 && 2 = True && True = 1 = True
          printf("x && y is True") ;
      return 0 ;
  }
  ```

  The output of this program is ...![38](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\38.PNG)

- **Example**

  ```c
  #include <stdio.h>
  int main ()
  {
      int a = 4, b = 3 ; 
      a = a ^ b ; 
      b = a ^ b ;
      a = a ^ b ;
      printf("After XORing, a = %d , b = %d", a , b) ;
      return 0 ;
  }
  /* 
  Solution
  	a = 0b00000100
  	b = 0b00000011
  	a = a ^ b
  	a = 0b00000111
  	b = 0b00000011
  	b = a ^ b
  	a = 0b00000111
  	b = 0b00000100
  	a = a ^ b
  	a = 0b00000011 = 3
  	b = 0b00000100 = 4
  Output 
  	After XORing, a = 3 , b = 4
  */
  ```
  
- Applications

  1. Set Bit (make bit equal 1)

     If we need to make any bit equal 1, we will perform the **OR operation** between **X value** and **(1 shifted left by number of bit we need to set)**

     ```c
     int x = 3 ;
     int set = 2 ;
     int res = 3 | (1 << set) ;
     ```

     **Example**

     ```c
     #include<stdio.h>
      int main()
      {
         int x , set ;
         printf ("Enter an Integer: ") ;
         scanf ("%d" , &x) ;
         printf ("Enter the number of bit you need to set: ") ;
         scanf ("%d" , &set) ;
         printf ("Your result is: %d" , (x | (1 << set))) ;
      }
     /*
     Input
     x = 3 , set = 2
     	x = 0b00000011
     	set = 0b00000010
         1 << set = 0b00000100
         x | (1 << set) = 0b00000111 = 7
     Output
     res = 7
     */
     ```

  2. Clear Bit (make bit equal 0)

     If we need to make any bit equal 0, we will perform the **AND operation** between **X value** and **The complement of (1 shifted left by number of bit we need to clear)**

     ```c
     int x = 3 ;
     int clear = 2 ;
     int res = 3 & ~(1 << clear) ;
     ```

     **Example**

     ```c
     #include<stdio.h>
      int main()
      {
         int x , clear ;
         printf ("Enter an Integer: ") ;
         scanf ("%d" , &x) ;
         printf ("Enter the number of bit you need to Clear: ") ;
         scanf ("%d" , &clear) ;
         printf ("Your result is: %d" , (x & ~(1 << clear))) ;
      }
     /*
     Input
     x = 7 , set = 2
     	clear = 0b00000010
         1 << clear = 0b00000100
         ~(1 << clear) = 0b11111011
         x = 0b00000111
         x & ~(1 << clear) = 0b00000011 = 3
     Output
     res = 3
     */
     ```

  3. Toggle Bit (make bit equal 0 if it equal 1 and 1 if it equal 0)

     If we need to make any bit equal 0 if it equal 1 and 1 if it equal 0, we will perform the **XOR operation** between **X value** and **(1 shifted left by number of bit we need to toggle)**

     ```c
     int x = 3 ;
     int toggel = 2 ;
     int res = 3 & ~(1 << toggel) ;
     ```

     **Example**

     ```c
     #include<stdio.h>
      int main()
      {
         int x , toggel ;
         printf ("Enter an Integer: ") ;
         scanf ("%d" , &x) ;
         printf ("Enter the number of bit you need to toggle: ") ;
         scanf ("%d" , &toggel) ;
         printf ("Your result is: %d" , (x ^ (1 << toggel))) ;
      }
     /*
     Input
     x = 4 , toggel = 2
     	x = 0b00000100
     	toggel = 0b00000010
         1 << toggel = 0b00000100
         x ^ (1 << toggel) = 0b00000000 = 0
     Output
     res = 0 
     */
     ```

### Assignment Operators

Assigned value to operator can be using assigned operator 

1. **=**

   To assign value to operator

2. **+=**

   First addition then assignment

3. **-=**

   First subtract then assignment

4. ***=**

   First multiplicate then assignment

5. **/=**

   First divide then assignment

6. **%=**

   First modules then assignment

7. **<<=**

   First bitwise Left Shift then assignment

8. **>>=**

   First bitwise Right Shift then assignment

9. **&=**

   First bitwise AND then assignment

10. **|=**

    First bitwise OR then assignment

11. **^=**

    First bitwise XOR then assignment

**Example**

```c
#include <stdio.h>
int main ()
{
    char a = 7 ; 
    a ^= 5 ;
    printf("%d" , printf("%d" , a += 3)) ;
    return 0 ;
}
/* 
Solution
	a = 0b00000111
	5 = 0b00000101
	a = a ^ 5
	a = 0b00000010 = 2
	first printf() return 1
Output 
	51
*/
```

### Escape Operators

| Operator |                Description                 |
| :------: | :----------------------------------------: |
|  **\n**  |                  New Line                  |
|  **\t**  |               Horizontal Tab               |
|  **\v**  |                Vertical Tab                |
|  **\\**  |  Display backslash character in a string   |
|  **\'**  | Display single-quote character in a string |
| **\\"**  | Display double-quote character in a string |
|  **%%**  |   Display modules character in a string    |
|  **\a**  |        Alert, sound the system bell        |

### Others

1. **Conditional Operator *? :*** (Ternary)

   It's trinary operator, it takes three operand and preform operation

   ```c
   /*
   	Expression 1 ? Expression 2 : Expression 3 ;
   	if Expression 1 is True then return Expression 2 
   	if Expression 1 is False then return Expression 3
   	we can replace Expression 2 or Expression 3 with True or False if there's no Expression
   */
   #include <stdio.h>
   int main ()
   {
       int res , in ;
       printf("Enter your degree: ") ;
       scanf("%d" , &in) ;
       res = (in > 30) ? in : 0 ;
       printf("Your degree is: %d" , res) ;
       return 0 ;
   }
   ```

   The output of this program is ...![39](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\39.PNG)

   Problem 

   ```c
   #include <stdio.h>
   int main ()
   {
       int var = 75 ;
       int var2 = 56 ;
       int num ;
       num = sizeof(var) ? (var2 > 23 ? ((var == 75) ? 'A' : 0) : 0) : 0 ;
       printf("%d" , num) ;
       return 0 ;
   }
   /* 
   Solution
   	first -> True and return second
   	second -> True and return Third
   	Third -> True and return A
   Output 
   	65
   */
   ```

2. **Comma Operator** 

   - Comma operator can be used as a "separator" (multiple definition in single line)

     ```c
     int a = 3 , b , c = 5 ;
     // the same of 
     int a = 3 ; 
     int b ;
     int c = 5 ;
     ```

   - Comma operator can be used as an "operator"

     returns the **rightmost** operand in the expression and it **simply evaluates the rest of the operands** and finally reject them

     ```c
     int a = (3 , 5 , 6) ; 
     printf("%d" , a) ;
     // output is 6
     int var = (printf("Hello") , 5) ;
     printf("%d" , a) ;
     // output is Hello5
     ```

   - Comma operator is having least precedence among all the operators available in C Language 

     ```c
     int a = 3 , 4 , 5 ;
     printf("%d" , a) ;		// error because it's equal to int a = 3 ; int 4 ; int 5 ;
     ```

   - Problem 

     ```c
     #include <stdio.h>
     int main ()
     {
         int var ;
         int num ;
         num = (var = 15 , var + 35) ;
         printf("%d" , num) ;
         return 0 ;
     }
     /* 
     Solution
     	return var + 35
     	evaluate var = 15
     	assign 15 + 35 to num
     Output 
     	50
     */
     ```

### Precedence and Associativity of Operators

| Precedence |       Category       |               Operators                | Associativity |
| :--------: | :------------------: | :------------------------------------: | :-----------: |
|  Level 1   | Parenthesis/brackets |         **( ) [ ] -> . ++ --**         | Left to Right |
|  Level 2   |        Unary         | **! ~ ++ -- + - * & (type) sizeof()**  | Right to Left |
|  Level 3   |    Multiplicative    |               *** / %**                | Left to Right |
|  Level 4   |       Additive       |                **+ -**                 | Left to Right |
|  Level 5   |   Bitwise Shifting   |               **<< >>**                | Left to Right |
|  Level 6   |      Relational      |             **< <= > >=**              | Left to Right |
|  Level 7   |       Equality       |               **== !=**                | Left to Right |
|  Level 8   |     Bitwise AND      |                 **&**                  | Left to Right |
|  Level 9   |     Bitwise XOR      |                 **^**                  | Left to Right |
|  Level 10  |      Bitwise OR      |                   \|                   | Left to Right |
|  Level 11  |     Logical AND      |                   &&                   | Left to Right |
|  Level 12  |      Logical OR      |                  \|\|                  | Left to Right |
|  Level 13  |     Conditional      |                **? :**                 | Right to Left |
|  Level 14  |      Assignment      | **= += -= *= /= %= &= \|= ^= <<= >>=** | Right to Left |
|  Level 15  |        Comma         |                 **,**                  | Left to Right |

> - Associativity can only help if there are two or more operator of same Precedence and not when there is just om=ne operator 
> - Operators with same Precedence have same Associativity as well

- Problems 

  ```c
  #include <stdio.h>
  int main ()
  {
      int a = 10 , b = 20 , c = 30 , d = 40 ;
      (a <= b == d > c) ? printf("TRUE") : printf("FALSE") ;
      return 0 ;
  }
  /* 
  Solution
  	<= it's a highest level from == so a <= b return True
      > it's a highest level from == so d > c return True
      == return True 
  Output 
  	TRUE
  */
  ```

  ```c
  #include <stdio.h>
  int main ()
  {
      int i = 5 ;
      int var = sizeof(i++) ; 
      printf("%d %d" , i , var) ; 
      return 0 ;
  }
  ```

  **a) 5 4**

  b) 6 4

  c) 5 8

  d) compiler error

  <img src="C:\Users\A-ELDESOUKY\AppData\Roaming\Typora\typora-user-images\image-20200716014512941.png" alt="image-20200716014512941" style="zoom:50%;" />

  ```c
  #include <stdio.h>
  int main ()
  {
      int a = 1 , b = 1 ;
      int c = ++a || b++ ; 
      int d = b-- && --a ;
      printf("%d %d %d %d" , a , b , c , d) ;
      return 0 ;
  }
  /* 
  Solution
  	line1 : a = 1 , b = 1 
      line2 : a = 2 , b = 1 , c = 1 	
      "b doesn't increment because in OR opertor if the first operand return True then don't 			evaluate the reast of condtions "
      line3 : a = 1 , b = 0 , c = 1 , d = 1
  Output 
  	1 0 1 1
  */
  ```

*****

## Questions Set 2

### Question 1

sizeof() operator returns size in ? 

a) Bits

**b) Bytes**

c) Kilobytes

d) Megabytes

### Question 2

Which of the following is the correct declaration of variables ? 

a) int a ; b ; c ;

b) int a , int b , int c ;

**c) int a , b , c ;**

### Question 3

what does print function returns ?

a) Size of integer 

b) Size of character 

c) Size of variable 

**d) Number of character printed on the screen**

### Question 4

ASCII deciaml range of charcters from A to Z is ?

**a) 65 - 90**

b) 97 - 122

c) 100 - 127

d) 1 -28

### Question 5

Size of integer ?

a) 32 bytes

b) 8 bytes

c) 16 bytes  

**d) Depends from machine to machine**

### Question 6

Which of the following are correct ?

```c
i) int 39 = 1 ; 
ii) int var_39 = 2 ;
iii) int var_ = 3 ;
```

a) i & ii

b) Only ii

**c) ii & iii**

d) None

### Question 7

Which of the following are correct ?

```c
i) int var ; 
ii) extern int var ;
```

a) i & ii only declare variable and not define them 

b) i & ii declare and define variable 

c) i declares variable and ii defines variable

**d) i declares variable and defines variable and ii only declare variable**

### Question 8

What the output of the following c program

```c
#include <stdio.h>
int var = 5 ; 
int main ()
{
    int var = var ;
    printf ("%d" , var) ; 
}
```

a) 5

b) Compiler error

**c) Garbage value**

d) None

### Question 9

What the output of the following c program

```c
#include <stdio.h>
int main ()
{
    {
        int var = 10 ;
    }
    printf ("%d" , var) ; 
}
```

a) 5

**b) Compiler error**

c) Garbage value

d) None

### Question 10

What the output of the following c program

```c
#include <stdio.h>
int main ()
{
    unsigned int var = 10 ;
    printf ("%d" , ~var) ; 
}
```

a) 10

**b) -11**

c) -10

d) -5

******

## Conditional Statement 

C provides three types of selection structures in the form of statements. The **if selection** statement either performs (selects) an action if a condition is true or skips the action if the condition is false, the **if…else selection** statement performs an action if a condition is true and performs a different action if the condition is false, the **switch** selection statement performs one of many different actions depending on the value of an expression

> **sequential execution**: statements in a program are executed one after the other in the order in which they’re written
>
> **transfer of control**: the next statement to be executed may be other than the next one in sequence
>
> **goto statement**: that allows programmers to specify a transfer of control to one of many possible destinations in a program, the notion of so-called structured programming became almost synonymous with “goto_elimination.”
>
> **control structures**, namely the **sequence structure**, the **selection structure** and the **repetition structure**, the **sequence structure** is built into C

1. **if syntax**

   if structure is called **single-selection** structure, because it selects or ignores a single action

   The if statement is a single-entry/single-exit structure

   ```c
   if (condition)
   {
       /*
       	Actions
       */
   }
   ```

2. **if / else syntax**

   The if…else statement is called a double-selection statement, because it selects between two different actions

   ```c
   if (condition_1)
   {
       /*
       	Actions_1
       */
   }
   else 
   {
       /*
       	Action_2
       */
   }
   ```

   If there's multiple condition, we can use this structure

    ```c
   if (condition_1)
   {
       /*
       	Actions_1
       */
   }
   else 
       if (condition_2)
       {
           /*
               Actions_2
           */
       }
   	else
           if (condition_3)
           {
               /*
                   Actions_3
               */
           }
   		else
               if (condition_4)
               {
                   /*
                       Actions_4
                   */
               }
   		   else 
               {
                  /* 
                  		Actions_5
                  */
            }
    ```

   But we can write better to make it more readable 
   
   ```c
   if (condition_1)
   {
       /*
       	Actions_1
       */
   }
   else if (condition_2)
   {
       /*
         Actions_2
       */
   } 
   else if (condition_3)
   {
       /*
         Actions_3
       */
   }   
   else if (condition_4)
   {
       /*
         Actions_4
       */
   }
   else 
   {
      /* 
 	 Actions_5
      */
   }
   ```
   
   >- C provides the conditional operator (?:) which is closely related to the if…else statement. The conditional operator is C’s only ternary operator—it takes three operands, the operands together with the conditional operator form a conditional expression, the first operand is a condition. The second operand is the value for the entire conditional expression if the condition is true and the third operand is the value for the entire conditional expression if the condition is false.
   >
   >- The if selection statement expects only one statement in its body, to include several statements in the body of an if, enclose the set of statements in braces ({ and }). A set of statements contained within a pair of braces is called a compound statement or a block

### If  Statement Rules 

1. **else if** is optional and can repeated 

2. **else is** optional and can't be repeated 

3. No cade between **if & else if & else**

   > ```c
   > if (condition)
   > {
   >     ....
   > }
   > int x ; 
   > else if 
   > {
   >     ....
   > }
   > // error
   > ```

4. **Nested if** is allowed, but no more than 3 level

   > ```c
   > if (condition)
   > {
   >     ....
   >     if (condition)
   >     {
   >         if (condition)
   >         {
   >             ....
   >         }
   >         else
   >         {
   >             
   >         }
   >     }
   >     else if (condition)
   >     {
   >         ....
   >     }
   >     else
   >     {
   >         ....
   >     }
   > }
   > // just 3 levels
   > ```

5. If the condition is a combination of multi-statements  use round brackets **( )**

   > ```c
   > if ((x == 3) && (y != 5))
   > {
   >     ....
   > }
   > ```

6. In case of one statement as action, you can ignore **{ }**, but always use **{ }** to avoid mistakes

### switch Statement

Switch is a great replacement to long else if statement

The switch statement is called a multiple-selection statement, because it selects among many different actions

```c
switch (condition)
{
    case condition_1 : 
        /*
        	Action_1
        */
   	break ;
    case condition_2 : 
        /*
        	Action_2
        */
   	break ;
    case condition_3 : 
        /*
        	Action_3
        */
   	break ;
    default :
        /*
        	Default Action
        */
   	break ; 
}
```

> The expression of each case must be an integer constant expression, even if the variable are constant 

We can use range in switch case instead of single number or character

```c
case condition 1 ... condition 2
```

```c
case low ... high ;			// we'll see it in enum   

case 'A' ... 'R' ; 

case 1 ... 5 ;
case 6 ... 10 ;
```

### Case Statement Rules 

1. **case** constant must be unique, can’t be a variable and must be integral value (int , char , enum) or macro 
2. Only one default is allowed
3. **default** label is Optional, can be placed anywhere in the switch
4. **break** Statement ends the switch
5. If you don't write break statement, the following cases will be evaluated until the end of the switch or until it finds a break statement without checking the case constant
6. Nesting (switch within switch) is allowed
7. The statement written above cases are never executed
8. Two cases labels can't have same value

### goto Keyword

The goto statement is a jump statement which is sometimes also referred to as unconditional jump statement. The goto statement can be used to jump from anywhere to anywhere within a function, also it's an unconditional branch, we don't use it and it not recommended, because it make your code not readable and we can't track the code, also it makes the program logic very complex, we can make a loop by using **goto** keyword, when the compiler read **goto** , he jump to label and skip any thing between goto and the label, use of goto can be simply avoided using break and continue statements.

```c
// Syntax 1
goto label;
.
.
.
label:
/*
	In the above syntax
    the first line tells the compiler to go to or jump to the statement marked as a label
*/
// Syntax 2
label:
.
.
.
goto label: 
/*
	In the above syntax
    the second line tells the compiler to go to or jump to the statement marked as a label
*/
```

```c
#include <stdio.h>
int main ()
{
    char c ;
    printf ("to print name enter 0 or any code to continuo\n") ;
    scanf (" %c" , &c) ;
    if (c == '0')
    {
        goto Name ;
    }
    else 
    {
        return 0 ;
    }
    Name: printf ("Desouky") ;
    printf ("your code after name lable") ;
}
```

*****

## Loops

We use it when we need to repeat some instruction multiple time, we have 3 types of loop:

1.  for Loop
2. while Loop
3. do-while Loop

> C has only seven control statements: sequence, three types of selection and three types of repetition.

### for Loop

We use it when we know the number of iteration or repetition (like, I need to print statement 10 times)

- Syntax

  ```c
  for (initialization ; condition ; increment/decrement)
  {
      // if the condition True, do these instruction
      statement 1 ; 
      statement 2 ; 
      ....
      ....
  }
  ```

- Example

  ```c
  #include <stdio.h>
  int main ()
  {
  	int i ;
  	for (i = 3 ; i > 0 ; i--)
      {
          printf("i now equal = %d\n" , i) ;
      }
  }
  /* 
  i = 3 so the condition is True
  First Loop
  	the instruction is done
  decrement i, i = 2 so the condition is True
  second Loop
  	the instruction is done
  decrement i, i = 1 so the condition is True
  Third Loop
  	the instruction is done
  decrement i, i = 0 so the condition is False
  The loop is ending
  */
  ```
  

The output of this program is ...![40](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\40.PNG)

### while Loop

We use it when we're waiting for event or any change in my condition to break the loop (like, I need to print statement, while **i > x / 9 * y + 5** or any change)

- Syntax

  ```c
  initialization
  while (condition)
  {
      // if the expression True, do these instruction
      statement 1 ; 
      statement 2 ; 
      ....
      ....
      increment/decrement
  }
  ```

- Example

  ```c
  #include <stdio.h>
  int main ()
  {
  	int i = 3 ;
  	while (i > 0)
      {
          printf("i now equal = %d\n" , i) ;
          i-- ;
      }
  }
  /* 
  i = 3 so the expression is True
  First Loop
  	the instruction is done, i = 2 so the expression is True
  second Loop
  	the instruction is done, i = 1 so the expression is True
  Third Loop
  	the instruction is done, i = 0 so the expression is False
  The loop is ending
  */
  ```
  

The output of this program is ...![40](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\40.PNG)

### do-while Loop

We used to do the instruction one time first, then check the expression

- Syntax

  ```c
  initialization
  do
  {
      // do it first time, then if the expression True, do these instruction
      statement 1 ; 
      statement 2 ; 
      ....
      ....
      increment/decrement
  } while (condition) ;
  ```

  >Don't forget **;** after **while (expression)**

- Example

  ```c
  #include <stdio.h>
  int main ()
  {
  	int i = 3 ;
  	do
      {
          printf("i now equal = %d\n" , i) ;
          i-- ;
      } while (i > 0) ;
  }
  /* 
  First Loop without checking the expression and doing the instruction
  i = 2 so the expression is True
  second Loop
  	the instruction is done
  i = 1 so the expression is True
  Third Loop
  	the instruction is done
  i = 0 so the expression is False
  Third Loop
  	the instruction is done, 
  The loop is ending
  */
  ```
  

The output of this program is ...![40](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\40.PNG)

- When should use **do-while** over **while**

  ```c
  #include <stdio.h>
  int main ()
  {
  	int i ;
  	do
      {
          printf("Enter an Integer: ") ;
          scanf("%d" , i) ;
      } while (i != 0) ;
      printf ("You're now out of the loop") ; 
  }
  ```

  ```c
  #include <stdio.h>
  int main ()
  {
  	int i ;
      printf("Enter an Integer: ") ;
      scanf("%d" , i) ;
  	while (i != 0) ;
      {
          printf("Enter an Integer: ") ;
          scanf("%d" , i) ;
      } 
      printf ("You're now out of the loop") ; 
  }
  ```
  

absolutely we should choose do-while loop 

> We can use any type of loops in any code, regardless of conditions

### Infinite Loop

It is an infinite loop which will run till a break statement is issued explicitly, a simple usage of infinite loop can be in the Client-Server program, in the program, the server runs in an infinite while loop to receive the packets sent from the clients, or it can be in embedded systems application, but it is not advisable to use infinite loop in real-world because it increases the CPU usage and also blocks the code, we can't come out from the infinite loop until the program is closed manually, infinite loop can be used at a place where condition needs to be true always

There're too many way to implement infinite loop , the compiler will be run for ever, let's take a look 

```c
// 1
for ( ; ; )
{
    // action 
}
// 2
for ( ; ; ) ;
// 3
for ( ; 1 ; )
{
    // action 
}
// 4
for ( ; 1 ; ) ;
// 5
while ()
{
    // action 
}
// 6
while () ;
// 7
while (1)
{
    // action 
}
// 8
while (1) ;
// 9
do
{
    
}while () ;
// 10
do
{
    
}while (1) ;
```

### Nested Loop

Nested loop means a loop statement inside another loop statement, that is why nested loops are also called as “loop inside loop“, we use nested loops for many programs and algorithms, like 2D & 3D array, sorting algorithm, some searching algorithm, to print all prime factors of a number, and so on 

1. for nested loop 

   ```c
   for (initialization1 ; condition1 ; increment/decrement1)
   {
       // if condition1 True, do these instruction
       statement 1 ; 
       .....
       for (initialization2 ; condition2 ; increment/decrement2)
       {
           // if condition2 True, do these instruction
           statement 2 ; 
           ....
           ....
       }
       ....
   }
   ```

2. while nested loop 

   ```c
   initialization
   while (condition1)
   {
       // if condition1 True, do these instruction
       statement 1 ;
       while (condition2)
       {
           // if condition2 True, do these instruction
           statement 2 ; 
           ....
       }
       ....
       increment/decrement
   }
   ```

3. do-while nested loop

   ```c
   initialization
   do
   {
       // do it first time, then if condition1 True, do these instruction
       statement 1 ; 
       do
       {
           // do it first time, then if condition2 True, do these instruction
           statement 2 ; 
           ....
       } while (condition2) ;
       ....
       increment/decrement
   } while (condition1) ;
   ```

4. Compound nested loop 

   ```c
   initialization
   do
   {
       // do it first time, then if condition1 True, do these instruction
       statement 1 ; 
       while (condition)
       {
           // if condition2 True, do these instruction
           statement 2 ; 
           for (initialization3 ; condition3 ; increment/decrement3)
           {
               // if condition3 True, do these instruction
               statement 3 ; 
               ....
               ....
           }
           ....
       }
       ....
       increment/decrement
   } while (condition1) ;
   ```
### Loops Control Statements 

1. **break**

   Used to terminate from the loop

   ```c
   #include <stdio.h>
   int main ()
   {
   	int i = 9 ;
   	while (i > 0)
       {
           printf ("I'm in the loop\n") ;
           if ((i + 2) % 2 == 0)
           {
               printf ("This a dead end\n") ;
               break ;
           }
           i-- ;
       }
       printf ("You're now out of the loop") ;
   }
   // when this equation: (i + 2) % 2 == 0 is achived , the loop will be terminated 
   ```

   The output of this program is ...![41](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\41.PNG)

> If we use break statement in simple loop, then it will out of it, but if we use it in nested loop,then it will out of the loop that write inside it, also we can write a break statement inside an infinite loop to get out of it under a specific condition 

1. **continue**

   Similar to break but instead of terminating from the loop, it forces to execute the next iteration of the loop, the continue statement can be used with any other loop also like while or do while in a similar way as it is used with for loop

   ```c
   // print all odd number from 1 to 10
   #include <stdio.h>
   int main ()
   {
   	int i = 10 ;
   	while (i > 0)
       {
           if (i  % 2 == 0)
           {
               i-- ;
               continue ;
           }
           printf ("I'm in the loop, and i = %d\n" , i) ;
           i-- ;
       }
       printf ("You're now out of the loop") ;
   }
   // when this equation: i % 2 == 0 is achived, the loop will go to chech the condition again
   ```

   The output of this program is ...![42](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\42.PNG)

******

## Questions Set 3

### Question 1

How many time ''Hello, World" be printed in your program 

```c
#include <stdio.h>
int main ()
{
	int i = 1024 ;
	for ( ; i ; i >>= 1)
    {
        printf ("Hello, World\n") ;
    }
}
/*
    1st -> i = 0b10000000000
    2nd -> i = 0b01000000000
    3rd -> i = 0b00100000000
    4th -> i = 0b00010000000
    5th -> i = 0b00001000000
    6th -> i = 0b00000100000
    7th -> i = 0b00000010000
    8th -> i = 0b00000001000
    9th -> i = 0b00000000100
    10th -> i = 0b00000000010
    11th -> i = 0b00000000001
    12th -> i = 0b00000000000
*/
```

- the initialization happened before the loop **int i = 1024**, but we must to mention **;**
- We check is i is True or False **(not zero)**, but we must to mention **;**

a) 10

**b) 11**

c) infinite

d) compiler error

### Question 2

What the output of the following c program

```c
#include <stdio.h>
int main ()
{
	int i ;
	for (i = 0 ; i < 20 ; i ++)
    {
        switch (i)
        {
            case 0 : i += 5 ;
            case 1 : i += 2 ;
            case 5 : i += 5 ;
            default : i += 4 ;
        }
        printf ("%d  " , i) ;
    }
}
/*
	There's no **break** statement after any case, so he will do all instructions in all cases
*/
```

a) compiler error

b) 5 10 15 20

**c) 16 21**

d) 7 12 17 22

### Question 3

How many time ''Neso" be printed in your program 

```c
#include <stdio.h>
int main ()
{
	int i = -5 ;
	while (i <= 5)
    {
        if (i >= 0)
        {
            break ;
        }
        else
        {
            i++ ;
            continue ;
        }
        printf ("Neso\n") ;
    }
}
/* 
	the program will not be able to reach the printf instruction 
```

a) Infinite Times

b) 10 Times

c) 5 Times

**d) 0 Times**

### Question 4

What the output of the following c program

```c
#include <stdio.h>
int main ()
{
	int i = 0 ;
	for (printf ("One\n") ; i < 3 && printf ("") ; i ++)
    {
        printf ("Hi\n") ;
    }
}
/*
	printf ("") ; will be returned 0, so the condition (True && False) is False
*/
```

The output of this program is ...![43](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\43.PNG)

### Question 5

What the output of the following c program, assuming size of unsigned int equal 4 bytes 

```c
#include <stdio.h>
int main ()
{
	unsigned int i = 500 ;
	while (i++ != 0) ;
    printf ("%d" , i) ;
}
/*
	the while loop will be running until i = 4294967296, then it get overflow and returns to 0
	but i will be incremented, so after the loop i = 1, and print 1 on the screen
*/
```

a) compiler error

b) 0

c) infinite loop

**d) 1**

> **;** after while loop mean, there's no body for the while loop, and prinf() function not a part of while loop

### Question 6

What the output of the following c program

```c
#include <stdio.h>
int main ()
{
	int x = 3 ;
	if (x == 2); x = 0 ;
	if (x == 3) x++ ;
	else x += 2 ;

	printf("x = %d" , x) ;
	return 0 ;
}
/*
The program will be like that: 
	int x = 3 ;
	x = 0 ;
	if (x == 3) 
	{
		x++ ;
	}
	else
    {
    	x += 2 ;
    }
	printf("x = %d" , x) ;
	return 0 ;
*/
```

a) compiler error

b) x = 0

c) x = 3 

**d) x = 2**

> **;** after if statement mean, there's no body for the if statement, and **x = 0** not a part of if statement

### Question 7

Print a pyramid of stars in your screen

```c
#include <stdio.h>
int main ()
{
	int high, i , j ;
	printf ("Please enter the hieght of the pyramid: ") ;
	scanf ("%d" , &high) ;
	for (i = 1 ; i <= high ; i++)
	{
		for (j = 1 ; j <= high - i ; j++)
		{
			printf (" ") ;
		}
		for (j = 1 ; j <= (i + i - 1) ; j++)
		{
			printf ("*") ;
		}
		printf ("\n") ;
	}
}
```

The output of this program is ...![44](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\44.PNG) 

### Question 8

Check If The Number Is Palindrome Number

A **palindromic number** (also known as a numeral **palindrome** or a numeric **palindrome**) is a **number** that remains the same when its digits are reversed. Like 16461

```c
#include <stdio.h>
int main ()
{
	int num, rev = 0 , cpy ;
	printf ("Please Enter an Integer: ") ;
	scanf ("%d" , &num) ;
	cpy = num ;
	while (cpy != 0)
    {
        rev = rev * 10 + cpy % 10 ;
        cpy /= 10 ;
    }
    if (rev == num)
    {
        printf ("Your Number is a Palindrome Number") ;
    }
    else
    {
        printf ("Your Number is Not a Palindrome Number") ;
    }
}
```

The output of this program is ...![46](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\46.PNG)![47](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\47.PNG)

### Question 9

Check If The Number Is Armstrong Number

**Armstrong number** is a **number** that is equal to the sum of cubes of its digits. For example 0, 1, 153, 370, 371 and 407 are the **Armstrong numbers**

```c
#include <stdio.h>
int main ()
{
	int num, res = 0 , cpy , digit = 0 , i , rem , pow ;
	printf ("Please Enter an Integer: ") ;
	scanf ("%d" , &num) ;
	cpy = num ;
	while (cpy != 0)
    {
        digit++ ;
        cpy /= 10 ;
    }
    cpy = num ;
	while (cpy != 0)
    {
        i = digit ;
        rem = cpy % 10 ;
        pow = 1 ;
        while (i != 0)
        {
            pow *=  rem ;
            i-- ;
        }
        res += pow ;
        cpy /= 10 ;
    }
    if (res == num)
    {
        printf ("Your Number is a Armstrong Number") ;
    }
    else
    {
        printf ("Your Number is Not a Armstrong Number") ;
    }
}
```

The output of this program is ...![48](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\48.PNG)![49](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\49.PNG)

### Question 10

Check If The Number Is Strong Number

**Strong number** is a special **number** whose sum of factorial of digits is equal to the original **number**. For example: 145

The **factorial** of a **number** is the product of all the integers from 1 to that **number**. For example, the **factorial** of 6 (denoted as 6!) is 1*2*3*4*5*6 = 720. **Factorial** is not defined for negative **numbers** and the **factorial** of zero is one, 0! = 1

```c
#include <stdio.h>
int main ()
{
	int num, res = 0 , cpy , fact = 1 , rem;
	printf ("Please Enter an Integer: ") ;
	scanf ("%d" , &num) ;
	cpy = num ;
	while (cpy != 0)
    {
        rem = cpy % 10 ;
        fact = 1 ;
        while (rem != 0)
        {
            fact *=  rem ;
            rem-- ;
        }
        res += fact ;
        cpy /= 10 ;
    }
    if (res == num)
    {
        printf ("Your Number is a Strong Number") ;
    }
    else
    {
        printf ("Your Number is Not a Strong Number") ;
    }
}
```

The output of this program is ...![50](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\50.PNG)![51](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\51.PNG)

### Question 11

Check If The Number Is Prime Number

A **Prime Number** is a natural number greater than 1 that is not a product of two smaller natural numbers. A natural number greater than 1 that is not prime is called a composite number. For example, 5 is prime because the only ways of writing it as a product, 1 × 5 or 5 × 1, involve 5 itself

A **Composite Number** is a positive integer that can be formed by multiplying two smaller positive integers. Equivalently, it is a positive integer that has at least one divisor other than 1 and itself.

> **1 is not a prime number**

```c
#include <stdio.h>
int main ()
{
	int num, cpy , flag = 1;
	printf ("Please Enter an Integer: ") ;
	scanf ("%d" , &num) ;
	cpy = num - 1 ;
	while (cpy > 1)
    {
        if (num % cpy == 0)
        {
            flag = 0 ;
            break ;
        }
        cpy-- ;
    }
    if (flag == 1 && num != 0 && num != 1)
    {
        printf ("Your Number is a Prime Number") ;
    }
    else
    {
        printf ("Your Number is Not a Prime Number") ;
    }
}
```

The output of this program is ...![52](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\52.PNG)![53](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\53.PNG)

> It's not necessary to check the modules from 2 to **num**, you can check from 2 to square root of **num**
>
> In C Libraries there's a function called **sqrt( )**, it **take double and retune double**, we can find it at **math.h** library, so we must **include** this library if we use it
>
> There's another function we use it make this solution right, **ceil( )** function, it **take double and retune double**, it returns a smallest integer greater than or equal to **num** 

### Question 12

 Adding Two Numbers Without Using The Plus Operator

We can do that with **increment & decrement** operator 

```c
#include <stdio.h>
int main ()
{
	int num1, num2;
	printf ("Please Enter an Number 1: ") ;
	scanf ("%d" , &num1) ;
	printf ("Please Enter an Number 2: ") ;
	scanf ("%d" , &num2) ;
	while (num2 > 0)
    {
        num1++ ;
        num2-- ;
    }
    printf ("Sum of Two Numbers Without Using The Plus Operator is %d" , num1) ;
}
```

The output of this program is ...![54](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\54.PNG)

We can make this code more portable with negative operand

```c
#include <stdio.h>
int main ()
{
	int num1, num2;
	printf ("Please Enter an Number 1: ") ;
	scanf ("%d" , &num1) ;
	printf ("Please Enter an Number 2: ") ;
	scanf ("%d" , &num2) ;
	if (num2 < 0)
    {
        while (num2 < 0)
        {
            num1-- ;
            num2++ ;
        }
    }
    else
    {
        while (num2 > 0)
    {
        num1++ ;
        num2-- ;
    }
    }
    printf ("Sum of Two Numbers Without Using The Plus Operator is %d" , num1) ;
}
```

The output of this program is ...![55](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\55.PNG)

### Question 13

Adding Two Numbers with using **HALF ADDER**

|  A   |  B   | S (A ^ B) | C (A & B) |
| :--: | :--: | :-------: | :-------: |
|  0   |  0   |     0     |     0     |
|  0   |  1   |     1     |     0     |
|  1   |  0   |     1     |     0     |
|  1   |  1   |     0     |     1     |

```c
#include <stdio.h>
int main ()
{
	int a, b, s , c ;
	printf ("Please Enter an Number 1: ") ;
	scanf ("%d" , &a) ;
	printf ("Please Enter an Number 2: ") ;
	scanf ("%d" , &b) ;
	while (b != 0)
    {
        s = a ^ b ;
        c = (a & b) << 1 ;
        a = s ;
        b = c ;
    }
    printf ("Sum of Two Numbers With HALF ADDER is %d" , num1) ;
}
/*
a = 5 , b = 10
	a = 0b0101
	b = 0b1010
	s = 0b1111
	c = 0b0000 
a = s , b = c 
loop stop and print the sum 

a = 7 , b = 2 
	a = 0b0111
	b = 0b0010
	s = 0b0101
	c = 0b0010 << 1 = 0b0100 
a = s , b = c 
loop continue
	a = 0b0101
	b = 0b0100
	s = 0b0001
	c = 0b0100 << 1 = 0b1000 
a = s , b = c 
loop continue
	a = 0b0001
	b = 0b1000
	s = 0b1001
	c = 0b0000 << 1 = 0b0000 
a = s , b = c 
loop stop and print the sum 
*/
```

The output is ...![56](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\56.PNG)![57](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\57.PNG)

### Question 14

Generate Fibonacci Series up to n number of terms 

a series of numbers in which each number ( *Fibonacci number* ) is the sum of the two preceding numbers. The simplest is the series 0, 1, 1, 2, 3, 5, 8, etc.

```c
#include <stdio.h>
int main ()
{
	int num1 = 0 , num2 = 1 , feb = 0 , n ;
	printf ("Please Enter the Number of Terms: ") ;
	scanf ("%d" , &n) ;
	printf ("Fibonacci Series is ") ;
	while (n > 0)
    {
        printf("%d  " , feb) ;
        num1 = num2 ;
        num2 = feb ;
        feb = num1 + num2 ;
        n-- ;
    }
}
```

The output of this program is ...![58](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\58.PNG)

### Question 15

Floyd's Triangle

**Floyd's triangle** is a right-angled **triangular** array of natural numbers, used in computer science education. It is named after Robert **Floyd**. It is defined by filling the rows of the **triangle** with consecutive numbers, starting with a 1 in the top left corner

```c
#include <stdio.h>
int main ()
{
	int n , i , j , q = 1 ;
	printf ("Please Enter the Number of Rows: ") ;
	scanf ("%d" , &n) ;
	printf ("Floyd's Triangle is\n") ;
	for (i = 1 ; i <= n ; i++)
    {
        j = i ;
        while (j > 0)
        {
            printf ("%d " , q) ;
            q++ ;
            j-- ;
        }
        printf ("\n") ;
    }
}
```

The output of this program is ...![59](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\59.PNG)

### Question 16

Binary to Decimal Conversion 

```c
#include <stdio.h>
int main ()
{
	int n , pow = 1 , dec = 0 ;
	printf ("Please Enter Binary Number: ") ;
	scanf ("%d" , &n) ;

    while (n != 0)
    {
        dec += (n % 10) * pow ;
        pow *= 2 ;
        n /= 10 ;
    }
    printf ("The Decimal Number is %d" , dec) ;
}
```

The output of this program is ...![60](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\60.PNG)

### Question 17

Calculating Power of an Integer

```c
#include <stdio.h>
int main ()
{
	int n , pow ;
	printf ("Please Enter the Base Number: ") ;
	scanf ("%d" , &n) ;
    printf ("Please Enter the Exponent Number: ") ;
	scanf ("%d" , &pow) ;
	if (pow < 0)
    {
        double res = 1.0 ;
         while (pow != 0)
        {
            res *= (1.0 / n) ;
            pow++ ;
        }
        printf ("The Result is %lf" , res) ;
    }
    else
    {
        int res = 1 ;
        while (pow != 0)
        {
            res *= n ;
            pow-- ;
        }
        printf ("The Result is %d" , res) ;
    }
}
```

The output of this program is ...![61](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\61.PNG)![62](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\62.PNG)

### Question 18

Check Leap Year (has 366 days)

Every *year* that is exactly divisible by four is a leap year, except for *years* that are exactly divisible by 100, but these centurial *years* are *leap years* if they are exactly divisible by 400. For example, the *years* 1700, 1800, and 1900 are not leap years

```c
#include <stdio.h>
int main ()
{
	int n ;
	printf ("Please Enter the Year: ") ;
	scanf ("%d" , &n) ;
    if (n % 400 == 0)
    {
        printf ("%d is a Leap Year" , n) ;
    }
    else if (n % 100 == 0)
    {
        printf ("%d isn't a Leap Year" , n) ;
    }
    else if (n % 4 == 0)
    {
        printf ("%d is a Leap Year" , n) ;
    }
    else
    {
        printf ("%d isn't a Leap Year" , n) ;
    }
}
```

The output of this program is ...![63](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\63.PNG)![64](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\64.PNG)

### Question 19

Check If The Number Is Perfect Number

**Perfect number**, a positive integer that is equal to the sum of its proper divisors. The smallest **perfect number** is 6, which is the sum of 1, 2, and 3. Other **perfect numbers** are 28, 496, and 8,128.

```c
#include <stdio.h>
int main ()
{
	int n , res = 0 , i ;
	printf ("Please Enter an Integer: ") ;
	scanf ("%d" , &n) ;
    for (i = 1 ; i < n ; i++)
    {
        if (n % i == 0)
        {
            res += i ;
        }
    }
    if (res == n)
    {
        printf ("Your Number is a Perfect Number") ;
    }
    else 
    {
        printf ("Your Number is not a Perfect Number") ;
    }
}
```

The output of this program is ...![65](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\65.PNG)![66](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\66.PNG)

### Question 20

Generate Factorial Number

```c
#include <stdio.h>
int main ()
{
	int num , fact = 1 , i = 1 ;
	printf ("Enter an integer: ") ;
	scanf ("%d" , &num) ;
	do 
	{
		fact *= i ; 
		i++ ;
	}while (i <= num) ;
	printf ("%d" , fact) ;
}
```

The output of this program is ...![92](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\92.PNG)![93](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\93.PNG)

*****

## Functions 

A set of statement that takes inputs, perform some computation and produces output, there're two important reasons of why we're using function:

1. **Reusability:** Once the function is defined, it can be reused over and over again 
2. **Abstraction:** If you're just using the function, you don't worry about how is works inside like **scanf( ), printf( )**

### Declaration  

Like when we declare a variable, we declare it's properties to the compile, for example: **int var ;** , so the properties are the type of variable **int** and the name of variable **var** , similarly, function declaration (also called **function prototype**) means declaring the properties of a function to the compiler, let's see an example

```c
Return_Type function_name (Input_Return_Type input_name, .... ) ;
int fun (int x , char y) ;
```

So the properties are:

1. Name function **fun**
2. Return type **int**
3. Number of inputs **2**
4. Input return type 1 **int**
5. Input return type 1 **char**

- It's not important to put the number of the parameters in function prototype, but it's important in function definition 

  ```c
  // like you see we can write input return type without mention their names
  int fun (int , char) ; 
  ```

- We write the declaration before the main function or before any file we use it in

  ```c
  #include <stdio.h>
  char fun () ;
  int main ()
  {
  	char c = fun() ;
  	printf("%c" , c) ;
  }
  
  char fun ()
  {
      return 'a' ;
  }
  ```

  The output of this program is ...![67](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\67.PNG)

- We can write all the declaration we'll used in one header file and include it in the source file

- We declare the function before we use it to let the compiler know some information for the function before I use it, like the return type of the function and the number of parameters and their data type

  ```c
  #include <stdio.h>
  
  int main ()
  {
  	char c = fun() ;
  	printf("%c" , c) ;
  }
  
  char fun ()
  {
      return 'a' ;
  }
  ```

  Error message...![68](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\68.PNG)
  
  >  If we don't write the prototype before the main function, so it's a compiler dependent 
  >
  > - some compiler get a warning message, then guess the prototype and run the program 
  > - some compiler get a error message

### Definition 

Function definition consists of blocks of code which is capable of performing some specific task

```c
// For example
int add (int a , int b)
{
    int sum ;
    sum = a + b ;
    return sum ; 
}
```

So let us use this function 

```c
#include <stdio.h>
int add (int , int) ;
int main ()
{
    int x = 20 , y = 30 ;
    int z = add (x , y) ;
    printf ("The sum of %d + %d = %d" , x , y , z) ; 
}
int add (int a , int b)
{
    int sum = a + b ;
    return sum ;
}
```

The output of this program is ...![69](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\69.PNG)

Now let's take notes about the previous example:

1. Don't forget to mention the prototype of a function before call it to declare the function 
2. There's no need to mention names of parameters 
3. When you call the function, you should not mention the return type of the function, also the data type of the arguments, you only mention the name of the function
4. It's important to mention both data type and name of parameters when you define it
5. at the line **int z = add (x , y) ;** ,the compiler will go to the function definition and then executes it
6. After execute the function, it will be return something and the return will be replaced with it place 
7. So the line after calling will be **int z = 50 ;** 

### Type of Function 

1. Return Function 

   A function return some value, and we use in this function **return** keyword

   **return: **We use this keyword to get out from a function, like if we want to end this function, same as **break** in loops, therefor we use it in last line of **main ()** function to make sure the program is end and we out of main function, or we can use it to return some value if a condition happened in function, there're many uses for it

   The return type of this type can be any data type like (int , char , float , ....)

2. Void Function 

   If you need to create function doesn't return any values to the caller, or If you need this function doesn't take any parameters, we write **void** in any position of them 

   ```c
   void fun1 (void) ;		//this function doesn't return or take any values 
   void fun2 (int, char) ; //this function doesn't return any values, but it has some parameters
   int fun3 (void) ;	   //this function returns a values, but it doesn't take any values
   ```

   > **int fun3 (void)** this function is a return function, but it doesn't take any values

   If we try to take a return from void function, we will get a **compiler error**

   ```c
   void sum (int a , b)
   {
       int sum = a + b ;
       return sum ;
   }
   int summation = sum (4 , 3) ;
   // **compiler error**
   ```

   When we call a void function, we just write the function name and two brackets 

   ```c
   void fun (void)
   {
       printf ("Desouky") ;
   }
   int main ()
   {
       fun () ;
   }
   // This program will print "Desouky" on the screen
   ```

   If you won't return, use void function, and don't treat it like returned function 

### Arguments vs. Parameters 

Argument: is the actual value of the parameters that's gets passed to the function, it's called as **Actual Parameter**

Parameter: is a variable declaration and definition of the function, it's called as **Former Parameter**

Like we see in example bello

```c
#include <stdio.h>
int add (int , int) ;
int main ()
{
    // a , b , sum are a local variable in main function 
    int a = 20 , b = 30 ;
    int sum = add (a , b) ;
    printf ("The sum of %d + %d = %d" , a , b , sum) ; 
}
int add (int a , int b)
{
    // a , b , sum are a local variable in add function 
    int sum = a + b ;
    return sum ;
}
```

**a & b**  in main function are the actual parameters, **a & b** in add function are the formal parameters

### Call By Value & Call By Reference 

Actual Parameter: The parameters passed to a function 

Former Parameter: The parameters received by a function 

1. **Call By Value**

   Here values of actual parameters will be copied to formal parameters and these two different store values in different location 

   ```c
   #include <stdio.h>
   int swap (int , int) ;
   int main ()
   {
       int a = 10 , b = 20 ;
       swap (a , b) ;
       printf ("a = %d , b = %d" , a , b) ;
   }
   int swap (int a , int b)
   {
       a = 20  ;
       b = 10 ;
   }
   ```

   The output of this program is ...![70](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\70.PNG)

   So we conclude from that we don't change in **a , b** values, because they're in different location and different scope 

2. **Call By Reference **

   Here both actual and formal parameters refers to same memory location, therefore, any change made to the formal parameters will get reflected to actual parameters 

   **Here instead of passing values, we pass addresses**

   ```c
   #include <stdio.h>
   int swap (int * , int *) ;
   int main ()
   {
       int a = 10 , b = 20 ;
       swap (&a , &b) ;
       printf ("a = %d , b = %d" , a , b) ;
   }
   int swap (int * a , int * b)
   {
       * a = 20  ;
       * b = 10 ;
   }
   ```

   The output of this program is ...![71](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\71.PNG)

   Notes here we require a **Special Variable** to access the location called **Pointer**, we'll talk about it later, but let's know, these variables store address not values

   So when we write *** a , * b**, we received the location of the actual parameters and you can change the content of these locations, we can say, we **mapping the location** and get access of content, then change the values 

   > Don't worry if you don't understand this part, after we're talking about **Pointer**, you will get it

### Static Functions

In C language, function are global by default, this means if we want to access the function outside from the file where it is declared, we can access it easily

So, now if you want to restrict this access, then you make your function static by simply putting a keyword **static** in front of the function return type, let's see the usefulness of static function with example 

```c
#include <stdio.h>
int fun (int , int) ;
int main ()
{
    int sum = fun (3 , 4) ;
    printf ("%d" , sum) ;
    return 0 ;
}
```

```c
// fun.c file 
int fun (int a , int b)
{
    return a + b ;
}
```

The output of this program is ...![73](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\73.PNG)

Now if we make **fun** function static 

```c
// main.c file 
#include <stdio.h> 
int fun (int , int) ;
int main ()
{
    int sum = fun (3 , 4) ; 
    printf ("%d" , sum) ;
    return 0 ;
}
```

```c
// fun.c file 
static int fun (int a , int b)
{
    return a + b ;
}
```

Error message...![74](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\74.PNG)like you see the main function didn't recognize **fun** function 

>- Static function are restricted to the files where they declared
>- Reuse of the same function in anther file is possible 

### Static and Dynamic Scoping in C

C Language use static scoping 

Scoping is necessary if you want to reuse variable names 

<img src="https://media.geeksforgeeks.org/wp-content/uploads/memoryLayoutC.jpg" alt="Memory Layout of C Programs - GeeksforGeeks" style="zoom:80%;" />

- Let's talk about **Stack** first

  1.   We have a part in out memory called **stack** (we'll talk about it letter)

  2. Stack is a container (or memory segment) which hold some data 

  3. Data is retrieved in **Last in-First out** (LIFO) fashion 

  4. Stack has many operation like **POP & PUSH**

  5. When we called any function it will get stored inside stack, and if you call another function, this function will be pushed inside the stack and the **Pointer** will move to this function you called, after completion of any function the function will be popped outside the stack

  6. only the **Activation Record** is store in stack

     Activation Record: is a portion of a stack which is generally composed of: 

     1. Locals of the callee
     2. Return address to the caller
     3. Parameters of the callee 

  <img src="https://i.ytimg.com/vi/2ZH_1d8TYVg/maxresdefault.jpg" alt="JavaScript Call Stack - YouTube" style="zoom: 50%;" />

> If we don't put a base condition for a recursion function, we'll get an infinite loop, and the function will be called until stack full, here we get a popular error called **stack overflow**

- **Static Scoping** (Lexical Scoping)

  Here definition of a variable is resolved by searching it's contacting block or function, if that fails, then searching the outer containing block and so on 

  ```c
  #include <stdio.h> 
  int a = 10 , b = 20 ;
  void fun (void) ;
  int main ()
  {
      fun () ;
  }
  void fun (void)
  {
      int a = 5 ;
      {
          int c = b / a ;
          printf ("%d" , c) ;
      }
  }
  /*
  here... 
  	we declare a , b as globle variables and redefine a , c inside fun function 
  	but we don't define b in function scope so the function search ouside it block 
  	and get value of b from the global variable b (20 / 5 = 4)
  */
  ```

  The output of this program is ...![75](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\75.PNG)

  ```c
  #include <stdio.h>
  int a = 5 ;
  int fun1 (int) ;
  int fun2 (int) ;
  int main ()
  {
      int a  = 10 ;
      a = fun1 (a) ;
      printf ("%d" , a) ;
  }
  int fun1 (int b)
  {
      b = b + 10 ;
      b = fun2 (b) ;
      return b ;
  }
  int fun2 (int b)
  {
      int c = a + b ;
      return c ;
  }
  /*
  global variable a will be in data segment, main function will be pushed in stack
  in main we called fun1 function and pass variable a = 10, it will be pushed in stack
  in fun1 we called fun2 function and pass variable b = 20, it will be pushed in stack
  in fun2 we declare and initialize variable c and equal to a + b
  b is known in fun2 scope, but a isn't
  fun2 function search outside it block and get value of a from the global variable a = 5
  fun2 will be returned c = a + b = 5 + 20, it will be popped from stack
  fun1 will be returned b = 5 + 20 = 25, it will be popped from stack
  main will be printed a = 25 to the screen, and it will be popped from stack
  now the stack is empty and the program finished
  */
  ```

  The output of this program is ...![76](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\76.PNG)

  > Don't Forget that, **C Language use static scoping**

  

- **Dynamic Scoping**

  Here definition of a variable is resolved by searching it's contacting block, if that fails, then searching it's calling function, and if still not found then the function which called that calling function will be searched and so on 

  Like in previse example when **fun2** function need value of **a** , it will be return to **fun1** because it's caller and the value of **a**  not found in **fun1** , then **fun1** it will be return to **main** function and the value of **a = 10** , so it will be returned to **fun1** then **fun2** , and it will be used in **fun2** and return **c = 30** to **fun1** , return **b = 30** to **main** and print the value of **a = 30** on the screen

  In C language we didn't use this sequence 

> * In most of the programing languages, static scoping is followed instead of dynamic scoping 
>
>   (most of modern languages static scoping is followed, most of old languages dynamic scoping is followed)
>
> * Languages including Algol, Pascal, C, Haskell, Scheme, etc. are statically scoped 
>
> *  Languages including SNOBOL, APL, Lisp, etc. are dynamically scoped 
>
> * As we know, C follows static scoping, so it's not possible to see programmatically, how dynamic scopeing works in C
>
> * Perl is a programing language which supports both static as well as dynamic scoping 
>
>   ```perl
>   $x = 50 ;				# global variable x = 50 
>   sub fun2
>   {
>   	return $x ;			# function returns variable x 
>   }
>   sub fun1
>   {
>   	local $x = 10 ;		# local variable x = 10 
>   	my $y = fun2() ;	# y = fun2 (), my makes variable visible only where it's declare
>   	return $y ;		    # funtion returns variable x 
>   }
>   print fun1 () ;			# fun2 () will search first in the caller function fun1
>   					   # x at fun1 is equal 10 
>   # output is : 10 
>   # first search in caller function, then search in global variables 
>   ```

### Recursion 

Recursion is a process in which a function calls itself directly or indirectly 

```c
int fun ()
{
    ....
    fun () ;
}
```

Let's take an example to understand 

```c
#include <stdio.h>
int fun (int x)
{
    if (x == 1)
        return 1 ;
    else
        return 1 + fun (x - 1) ;
}
int main ()
{
    int x = 3 ;
    printf("%d" , fun (x)) ;
    return 0 ;
}
/*
This program print the value of x using recursion 
in main we print the return of fun function and pass variable x = 3 to the function 
in fun we check if x == 1 return 1, else return 1 + fun (x - 1)
so x = 3, return 1 + fun (2)
x = 2, return 1 + fun (1)
x = 1, return 1 to the previous caller 
sum 1 + 1 and return 2 to the previous caller 
sum 1 + 2 and return 3 to the printf function
*/
```

The output of this program is ...![78](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\78.PNG)

> **You must make condition to break the recursion, or the program will be crashed**

- How to write Recursive Function 

  1. Divide the Problem into smaller sub-problem 

  2. Specify the base condition to stop the recursion 

     **Base Condition: **is the one which doesn't require to call the same function again and it help in stopping the recursion 

  Every Recursive Function must have this body 

  ```c
  return_type function_name (paramters)
  {
      if (base condition)
      {
          // base case
          // second TO WRITE 
      }
      else 
      {
          // Recursive procedure 
          // FIRST TO WRITE 
      }
  }
  ```

  Let's take example to find **Factorial** recursively

  ```c
  #include <stdio.h> 
  int fact (int x) ;
  int main ()
  {
  	int x ; 
  	printf ("Enter Num: ") ;
  	scanf ("%d" , &x) ;
  	printf ("num Factorial is: %d" , fact (x)) ;
  }
  int fact (int x) 
  {
  	if (x == 0)		// factorial 0 is 1
  	{
  		return 1 ;
  	}
  	return x * fact(x - 1) ;
  }
  /*
  fact (4)								  return 24
  	x = 4 	x != 0	return 4 * fact (3)		return 4 * 6 to the previous caller
  fact (3)
  	x = 3 	x != 0	return 3 * fact (2)		return 3 * 2 to the previous caller
  fact (2)
  	x = 2 	x != 0	return 2 * fact (1)		return 2 * 1 to the previous caller
  fact (1)
  	x = 1 	x != 0	return 1 * fact (0)		return 1 * 1 to the previous caller
  fact (0)
  	x = 0 	x == 0	return 1	to the previous caller
  */
  ```

  The output of this program is ...![79](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\79.PNG)

- **Type of Recursion**

  1. Direct Recursion 

     A function is called direct recursive if it calls the same function again 

     ```c
     int fun ()
     {
         // some code 
         fun () ;
         // some code
     }
     ```

     Example: Factorial Number 

  2. Indirect Recursion 

     A function is called indirect recursive if it calls the another function and this another function called original function again directly or indirectly

     ```c
     int fun1 ()
     {
         // some code 
         fun2 () ;
         // some code
     }
     int fun2 ()
     {
         // some code 
         fun1 () ;
         // some code
     }
     ```

     Example: print numbers from 1 to 10 in such a way that when number is odd, add 1 and when number is even, subtract 1 

     ```c
     #include <stdio.h>
     void odd (void) ;
     void even (void) ;
     int a = 10 ;
     int main ()
     {
         odd () ;
     }
     void odd (void)
     {
         if (n <= 10)
         {
             printf ("%d " , n + 1) ;
             n++ ;
             even () ;
         }
         return ;
     }
     void even (void)
     {
         if (n <= 10)
         {
             printf ("%d " , n - 1) ;
             n++ ;
             odd () ;
         }
         return ;
     }
     /*
     	global variable a will be in data segment, main function will be pushed in stack
         in main we called odd function, it will be pushed in stack
         in odd we print n + 1 = 1 + 1 = 2
         then increment n by 1 and called even function, it will be pushed in stack
         in even we print n - 1 = 2 - 1 = 1
         then increment n by 1 and called odd function, it will be pushed in stack
         in odd we print n + 1 = 3 + 1 = 4
         then increment n by 1 and called even function, it will be pushed in stack
         in even we print n - 1 = 4 - 1 = 3
         then increment n by 1 and called odd function, it will be pushed in stack
         in odd we print n + 1 = 5 + 1 = 6
         then increment n by 1 and called even function, it will be pushed in stack
         in even we print n - 1 = 6 - 1 = 5
         then increment n by 1 and called odd function, it will be pushed in stack
         in odd we print n + 1 = 7 + 1 = 8
         then increment n by 1 and called even function, it will be pushed in stack
         in even we print n - 1 = 8 - 1 = 7
         then increment n by 1 and called odd function, it will be pushed in stack
         in odd we print n + 1 = 9 + 1 = 10
         then increment n by 1 and called even function, it will be pushed in stack
         in even we print n - 1 = 10 - 1 = 9
         then increment n by 1 and called odd function
         it will be returned to even and popped from stack
         all odd, even functins will be pooped from stack until returned to main function
         the main will be popped, now the stack is empty and the program finished
     */
     ```

     The output of this program is ...![80](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\80.PNG)

  3. Tail Recursion 

     A recursive function is said to be tail recursive if the recursive call is the last thing done by the function, there's no need to keep record of the previous state  

     ```c
     #include <stdio.h>
     void fun (int n) ;
     int main ()
     {
         int n = 3 ;
         fun (n) ;
     }
     void fun (int n)
     {
         if (n == 0)
         {
            return ;
         }
         else 
         {
             printf ("%d " , n) ;
         }
         return fun (n - 1) ;
     }
     ```

     The output of this program is ...![81](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\81.PNG)

  4. Non-Tail Recursion 

     A recursive function is said to be tail recursive if the recursive call is not the last thing done by the function, after returning back, there's something left to evaluate

     ```c
     #include <stdio.h>
     void fun (int n) ;
     int main ()
     {
         int n = 3 ;
         fun (n) ;
     }
     void fun (int n)
     {
         if (n == 0)
         {
            return ;
         }
         fun (n - 1) ;
         printf ("%d " , n) ;
     }
     ```

     The output of this program is ...![82](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\82.PNG)

     Example: Factorial Number 

- Advantage and Disadvantage of Recursion

  Every program written in **recursive program**, can be written in **iterative program**

  1. **Advantage: **Every recursive program, can be modeled into an iterative program, but recursive programs are **more elegant and requires relatively less lines of code**

  2. **Disadvantage: **Recursive programs require more space than iterative programs

     > Don't use recursive programs if you have small memory 

*****

## Questions Set 4

### Question 1

Consider the function **func** shown below, what's the value returned by **func(435)** ?

```c
int func (int num) 
{
    int count = 0 ;
    while (num)
    {
        count++ ;
        num >>= 1 ;
    }
    return (count) ;
}
/*
befor while loop
	0th -> num = 435 		   count = 0
in while loop 
    1st -> num = 0b110110011	count = 1	num = 0b011011001
    2nd -> num = 0b011011001	count = 2	num = 0b001101100
    3rd -> num = 0b001101100	count = 3	num = 0b000110110
    4th -> num = 0b000110110	count = 4	num = 0b000011011
    5th -> num = 0b000011011	count = 5	num = 0b000001101
    6th -> num = 0b000001101	count = 6	num = 0b000000110
    7th -> num = 0b000000110	count = 7	num = 0b000000011
    8th -> num = 0b000000011	count = 8	num = 0b000000001
    9th -> num = 0b000000001	count = 9	num = 0b000000000
    10th ->num = 0b000000000	the loop end here
*/
```

The return of this function is **9**

Now if we change this line **num >>= 1 ;** with this **num >>= 2 ;** , what's the return of this function 

```c
int func (int num) 
{
    int count = 0 ;
    while (num)
    {
        count++ ;
        num >>= 2 ;
    }
    return (count) ;
}
/*
befor while loop
	0th -> num = 435 		   count = 0
in while loop 
    1st -> num = 0b110110011	count = 1	num = 0b001101100
    2nd -> num = 0b001101100	count = 2	num = 0b001101100
    3rd -> num = 0b000011011	count = 3	num = 0b000000110
    4th -> num = 0b000000110	count = 4	num = 0b000000001
    5th -> num = 0b000000001	count = 5	num = 0b000000000
    6th -> num = 0b000000000	the loop end here
*/
```

The return of this function is **5**

### Question 2

What the output of the following c program

```c
#include <stdio.h>
void f1 (int a , int b)
{
    int c ;
    c = a ; a = b ; b = c ;
}
void f2 (int * a , int * b)
{
    int c ;
    c = * a ; * a = * b ; * b = c ;
}
int main ()
{
    int a = 4 , b = 5 , c = 6 ;
    f1 (a , b) ;
    f2 (&b , &c) ;
    printf ("%d" , c - a - b) ;
}
/*
in f1
	there's no action happened
in f2
	a = 4 , b = 6 , c = 5
	c - a - b = 5 - 4 - 6 = -5
*/
```

The output of this program is ...![72](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\72.PNG)

### Question 3

What the output of the following c program

```c
#include <stdio.h>
int fun () 
{
    static int num = 16 ; 
    return num-- ;
}
int main ()
{
    for (fun() ; fun () ; fun ())
        printf ("%d" , fun());
    return 0 ;
}
/*
for loop initialization 
	fun return 16	num = 15 
in for loop 
    1st -> condition: fun return 15	num = 14	action: fun return 14	num = 13
    update_value_1: fun return 13	num = 12
    2nd -> condition: fun return 12	num = 11	action: fun return 11	num = 10
    update_value_2: fun return 10	num = 9
    3rd -> condition: fun return 9	num = 8		action: fun return 8	num = 7
    update_value_3: fun return 7	num = 6
    4th -> condition: fun return 6	num = 5		action: fun return 5	num = 4
    update_value_4: fun return 4	num = 3
    5th -> condition: fun return 3	num = 2		action: fun return 2	num = 1
    update_value_4: fun return 1	num = 0
    5th -> condition: fun return 0	num = -1		the loop end here
*/
```

a) Infinite loop

b) 13 10 7 4 1

**c) 14 11 8 5 2**

d) 15 12 8 5 2

### Question 4

What the output of the following c program

```c
#include <stdio.h>
int a , b ;
void print ()
{
    printf ("%d %d" , a , b) ;
}
int fun1 ()
{
    int a , c ;
    a = 0 ; b = 1 ; c = 2 ;
    return c ;
}
int fun2 ()
{
    int b ;
    a = 3 , b = 4 ;
    print() ;
}
int main ()
{
    a = fun1 () ;
    fun2 () ;
}
/*
With Static Scoping 
	global variable a , b will be in data segment, main function will be pushed in stack 
	in main we called fun1 function, it will be pushed in stack
	fun1 it make some changing in globle variables, b = 1 because it not declared in fun1 scope
	fun1 will be returned c = 2 and assign it to a = 2, , and it will be popped from stack
	now global variable a = 2 , b = 1
	in main we called fun2 function, it will be pushed in stack
	fun2 it make some changing in globle variables, a = 3 because it not declared in fun2 scope 
	but there's no change in global variable b because it declared in fun2 scope (Local variable)
	in fun2 we called print function, it will be pushed in stack
	in print function a , b not decaled in function scope
    so print will search outside it block and get value from the global variable a = 3 , b = 1
    and will be printed a = 3 , b = 1 on the screen, and it will be popped from stack
	fun2 will be popped from stack, then main will be popped from stack
	now the stack is empty and the program finished
With Dynamic Scoping
	global variable a , b will be in data segment, main function will be pushed in stack 
	in main we called fun1 function, it will be pushed in stack
	fun1 it make some changing in globle variables, b = 1 because it not declared in fun1 scope
	fun1 will be returned c = 2 and assign it to a = 2, , and it will be popped from stack
	now global variable a = 2 , b = 1
	in main we called fun2 function, it will be pushed in stack
	fun2 it make some changing in globle variables, a = 3 because it not declared in fun2 scope 
	but there's no change in global variable b because it declared in fun2 scope (Local variable)
	in fun2 we called print function, it will be pushed in stack
	in print function a , b not decaled in function scope
    so print will search in caller function fun2 and get value from fun2 function a = 3 , b = 4
    and will be printed a = 3 , b = 4 on the screen, and it will be popped from stack
    fun2 will be popped from stack, then main will be popped from stack
	now the stack is empty and the program finished
*/
```

With Static Scoping

a) 2    4

**b) 3    1**

c) 2    5

d) 3    4

With Dynamic Scoping

a) 2    4

b) 3    1

c) 2    5

**d) 3    4**

### Question 5

Consider the program bellow in a **hypothetical programing language** which allows global variables and a choice of static or dynamic scoping 

Let x be the value printed under static scoping and y be the value printed under dynamic scoping

```c
int i ;					// global variable 
program main ()
{
    i = 10 ;			// change the value of global variable i = 0 to be i = 10
    call f () ;			// call function f () 
}
procedure f ()
{
    int i = 20 ;		// local variable in f function 
    call g () ;			// call function g () 
}
procedure f ()
{
    print i ;			// print i value  
}
/*
With Static Scoping
	in main we called f function 
	in f we called g function 
	in g we print i, and i is not declared in g function, so it will be search outside the function
	it get global variable i = 10 and returned to f function, then to main function
	print 10 on the screen 
With Dynamic Scoping
	in main we called f function 
	in f we called g function 
	in g we print i, and i is not declared in g function, so it will be search in caller function 
	it get local variable i = 20 and returned to f function, then to main function
	print 20 on the screen
*/
```

a) x = 10 , y = 10

b) x = 20, y = 10

**c) x = 10 , y = 20**

d) x = 20, y = 20

### Question 6

What will be the output of the following pseudocode when parameters are passed by reference and dynamic scoping is assumed 

```pseudocode
a = 3 ;
void n (x)
{
	x = x * a ;
	print (x) ;
}
void m (y)
{
	a = 1 ;
	a = y - a ;
	n (a) ;
	print (a) ; 
}
void main ()
{
	m (a) ;
}
```

a) 6 , 2

b) 6 , 6

c) 4 , 2

**d) 4 , 4**

### Question 7

Consider the following recursive program, if get(6) function called in main() then how many times will get() function be invoked before returning to the main()

```c
void get (int n)
{
    if (n < 1) 
    {
        return ;
    }
    get (n - 1) ;
    get (n - 3) ;
    printf ("%d" , n) ;
}
```

a) 15

**b) 25**

c) 35

d) 45

### Question 8

Determine, how many number of times the star will be printed on the screen

```c
void fun1 (int n)
{
    int i = 0 ;
    if (n > 1)
    {
        fun1 (n - 1) ;
    }
    for (i = 0 ; i < n ; i++)
    {
        printf (" * ") ;
    }
}
```

a) n

**b) n * (n - 1) / 2**

c) n * n

d) None of the above 

### Question 9

Consider the C function given bellow, which statement is correct 

```c
int f (int j)
{
    static int i = 50 ;
    int k ;
    if (i == j)
    {
        printf ("Something") ;
        k = f (i) ;
        return 0 ;
    }
    else 
    {
        return 0 ;  
    }
}
```

a) The function returns 0 for all values of j

b) The function prints for all values of j

c) The function returns 0 when j = 50

**d) The function will exhaust the runtime stack or run into an infinite loop when j = 50**

### Question 10

Consider the C function given bellow, find the return value of fun(5)

```c
int fun (int n)
{
    int x = 1 , k ;
    if (n == 1)
    {
        return x ;
    }
    for (k = 1 ; k < n ; ++k)
    {
        x = x + fun (k) * fun (n - k) ;
    }
    return x ;
}
/*
	1th -> fun (5) = 1 + fun (1) * fun (4)
	2nd -> fun (5) = 1 + fun (1) * fun (4) + fun (2) * fun (3)
	3rd -> fun (5) = 1 + fun (1) * fun (4) + fun (2) * fun (3) + fun (3) * fun (2)
	4 th ->fun (5) = 1 + fun (1) * fun (4) + fun (2) * fun (3) + fun (3) * fun (2) +fun (4) * fun (1)
	
	fun (5) = 1 + 2 * [fun (1) * fun (4) + fun (2) * fun (3)]
	fun (5) = 1 + 2 * [fun (4) + fun (2) * fun (3)]
	
	fun (2) = 1 + fun (1) * fun (1) = 1 + 1 = 2
	fun (3) = 1 + fun (1) * fun (2) + fun (2) * fun (1) = 1 + 2 + 2 = 5
	fun (4) = 1 + fun (1) * fun (3) + fun (2) * fun (2) + fun (3) * fun (1) = 1 + 5 + 4 + 5 = 15
	
	fun (5) = 1 + 2 * [15 + 5 * 2] = 1 + 2 * [25] = 51
*/
```

a) 0

**b) 51**

c) 71

d) 81

### Question 11

Consider the C function given bellow, find the return value of fun(3)

```c
void fun (int n)
{
    static int d = 1 ;
    printf ("%d " , n) ;
    printf ("%d " , d) ;
    d++ ; 
    if (n > 1)
    {
        fun (n - 1) ;
    }
    printf ("%d " , d) ;
}
```

**a) 3 1 2 2 1 3 4 4 4**

b) 3 1 2 1 1 1 2 2 2

c) 3 1 2 2 1 3 4

d) 3 1 2 1 1 1 2

### Question  12

Which of the following statement is true about static functions in C

a) Static functions are global functions 

**b) Static functions are restricted to the files where they are declared **

c) There's no concept like static functions in c

d) None of the above

### Question 13

State true or false, in C, it's mandatory to declare a function before use 

a) True

**b) False**

### Question 14

Which keyword is used to come out of loop only for that iteration 

a) break

b) return

**c) continuo**

d) None of the above

### Question 15

Which of the following ways to write a function prototype is correct 

I) int fun (int a , int b)

II) int fun (int , int)

III) fun (int , int)

a) Only I

b) Only II & III

**c) Only I & II**

d) All

### Question 16

In C, parameters are always 

**a) Passed by value**

b) Passed by reference 

c) Both

d) None of the above

> Parameters always passed by value, pass by reference is simulated in C explicitly passing pointer values 

### Question 17

In C, what the meaning of the following function prototype with empty parameters list

a) Function can only called with out any parameters 

**b) Function can only called with any number of parameters of any type**

c) Function can be called with any number of integer parameters 

d) Function can be called with one integer parameter

### Question 18

Assuming int size is 4 bytes, what's going to happen when the following program runs 

```c
#include <stdio.h>
int main ()
{
    printf ("Hi\n") ;
    main () ;
    return 0 ;
}
```

a) We can't use main () inside main ()

b) Hi will be printed 2147483647 times 

**c) Hi would be printed until stack overflow happens for this program**

d) Hi would be printed only once, because when main () is used inside main (), it's ignored n]by compiler at run time 

### Question 19

Which of the following statement is the best statement in C

a) "break" , "continuo" can be used in "for", "while", "do-while" loop body and "switch" body

**b) "break" , "continuo" can be used in "for", "while", "do-while" loop body, but only "break" can be used in "switch" body**

c)  "break" , "continuo" can be used in "for", "while", "do-while" loop body and "switch", "if-else" body

d) None of the above

### Question 20

What the output of the following c program

```c
#include <stdio.h>
int main ()
{
    int i = 9 ;
    for ( ; i ; )
    {
        printf ("Hi\n") ;
        i-- ;
    }
    return 0 ;
}
```

a) Hi will be printed 10 times 

**b) Hi will be printed 9 times**

c) Compiler error

d) None of the above

*******

## Project 1

Write a C program to act as simple calculator, first it will ask the user to enter the operation ID, depending on the operation, the program will ask the user either to enter 1 operand or 2 operands and the program will execute the operation and print the result.

|  ID  | Operation | Number of Operands |
| :--: | :-------: | :----------------: |
|  1   |    add    |         2          |
|  2   | subtract  |         2          |
|  3   | multiply  |         2          |
|  4   |  divide   |         2          |
|  5   |    AND    |         2          |
|  6   |    OR     |         2          |
|  7   |    NOT    |         1          |
|  8   |    XOR    |         2          |
|  9   | reminder  |         2          |
|  10  | increment |         1          |
|  11  | decrement |         1          |

```c
// main.c file
#include <stdio.h>
#include "Project_1.h"		// include prototype of the function from the header file
int main ()
{
	int ID ;
    char flag ;
	do
	{
		printf	("Enter Operation ID: ") ;
		scanf	("%d" , &ID) ;
		switch 	(ID)
		{
			case 1 : Scan2Value() ; 	Add			(); break ;
			case 2 : Scan2Value() ; 	Subtract	(); break ;
			case 3 : Scan2Value() ; 	Multiply	(); break ;
			case 4 : Scan2Value() ; 	Divide		(); break ;
			case 5 : Scan2Value() ; 	And			(); break ;
			case 6 : Scan2Value() ; 	Or			(); break ;
			case 7 : Scan1Value() ;		Not			();	break ;
			case 8 : Scan2Value() ; 	Xor			(); break ;
			case 9 : Scan2Value() ; 	Reminder	(); break ;
			case 10 : Scan1Value() ;	Increment	();	break ;
			case 11: Scan1Value() ;		Decrement	();	break ;
			default: printf ("ID is not valid\n");		break ;
		}
		printf	("Enter 0 to exit, any key to continue ") ;
		scanf	(" %c" ,  &flag) ;
	} while 	(flag != '0') ;
}
```

```c
// Project_1.h file (Declaration of functions)
void Scan2Value	(void) ;		// Declaration of function takes 2 values from user
void Scan1Value	(void) ;		// Declaration of function takes 1 value from user
void Add 		(void) ;	    // Declaration of function adding 2 values 
void Subtract 	(void) ;		// Declaration of function subtracting 2 values 
void Multiply	(void) ;		// Declaration of function multiplying 2 values
void Divide		(void) ;		// Declaration of function dividing 2 values
void And 		(void) ;		// Declaration of function anding 2 values
void Or	 		(void) ;		// Declaration of function oring 2 values
void Not 		(void) ;		// Declaration of function complementing 1 value
void Xor 		(void) ;		// Declaration of function xoring 2 values
void Reminder 	(void) ;		// Declaration of function give reminder after divide 2 values
void Increment 	(void) ;		// Declaration of function incrementing 1 value
void Decrement 	(void) ;		// Declaration of function decrementing 1 value
```

```c
// Project_1.c file (Definition of functions)
#include <stdio.h>			// include stdio library to use printf , scanf
int num1 , num2 ;			// initialize 2 global variable 
void Scan2Value	(void)		// Definition of function takes 2 values from user
{
				printf	("Enter Operand 1: ") ;
				scanf	("%d" , &num1) ;
				printf	("Enter Operand 2: ") ;
				scanf	("%d" , &num2) ;
}
void Scan1Value	(void)		// Definition of function takes 1 value from user
{
				printf	("Enter the Operand : ") ;
				scanf	("%d" , &num1) ;
}
void Add 		(void)		// Definition of function adding 2 values
{
				printf ("The Operation Result is: %d\n" , num1 + num2) ;
}
void Subtract 	(void)		// Definition of function subtracting 2 values
{
				printf ("The Opernum1tion Result is: %d\n" , num1 - num2) ;
}
void Multiply	(void)		// Definition of function multiplying 2 values
{
				printf ("The Operation Result is: %d\n" , num1 * num2) ;
}
void Divide		(void)		// Definition of function dividing 2 values
{
				printf ("The Opernum1tion Result is: %d\n" , num1 / num2) ;
}
void And 		(void)		// Definition of function anding 2 values
{
				printf ("The Operation Result is: %d\n" , num1 & num2) ;
}
void Or	 		(void)		// Definition of function oring 2 values
{
				printf ("The Operation Result is: %d\n" , num1 | num2) ;
}
void Not 		(void)		// Definition of function complementing 1 value
{
				printf ("The Opernum1tion Result is: %d\n" , ~num1) ;
}
void Xor 		(void)		// Definition of function xoring 2 values
{
				printf ("The Operation Result is: %d\n" , num1 ^ num2) ;
}
void Reminder 	(void)		// Definition of function give reminder after divide 2 values
{
				printf ("The Operation Result is: %d\n" , num1 % num2) ;
}
void Increment 	(void)		// Definition of function incrementing 1 value
{
				printf ("The Operation Result is: %d\n" , ++num1) ;
}
void Decrement 	(void)		// Definition of function deccrementing 1 value
{
				printf ("The Operation Result is: %d\n" , --num1) ;
}
```

This Project output is...![94](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\94.PNG)

*****

## Arrays

An array is a data structure containing a number of data values (all of which are of same type)

- Data Structure: is a format for organizing and sorting data, also each data structure is designed to suit a specific purpose 
- Array contain a number of data value, like we can have array with 5 elements or array with 1 element 
- Data type of array elements all are same, we can have array of integer, array of character and array of float and so on
- The simplest form of array one can imagine is one dimensional array
- You can imagine a block of memory as a variable and an array as a collection of variable

<img src="https://i.imgur.com/YqjN9uC.gif" alt="A developer's blog: Arrays in F# – The Mutable collection" style="zoom: 150%;" />

### Declaration and Definition 

Declaring means: Compiler will allocate a contiguous block of memory of **size = no. of element * sizeof(data_type)**

```c
data_type array_name [no. of element] ;
// for example
int arr [5] ;	char c [8] ;	float frac [3] ;
```

> The length of an array can be specified **only by Positive integer value constant expression**
>
> Specifying the length of an array using **macro** is considered to be an excellent practice **(#define)** , because when you need resize the array, so when you need to edit on the array length, then change the value of macro 

### Accessing Array Elements

To access an array element 

```c
array_name [index of element] ;
// for example 
arr[0] ; 		// accessing element number 1
arr[1] ;		// accessing element number 2
arr[2] ;		// accessing element number 3
```

> In arrays we start counting from **0** and go up to **length - 0**, the index for first element in arrays is always **0**, if you try to access element with index equal length, you'll get an error

### Initializing an Array

There's 4 methods we can initialize the array with it 

1. Method one 

   ```c
   int arr[5] = {1, 2, 3, 4, 5} ;
   ```

   Here we know the size of array but we can't add any element before update the array length 

2. Method two

   ```c
   int arr[] = {1, 2, 3, 4, 5} ;
   ```

   Here we don't know the size of array but we can add any element to the array 

3. Method three

   ```c
   int arr[5] ;
   arr[0] = 1 ;
   arr[1] = 2 ;
   arr[2] = 3 ;
   arr[3] = 4 ; 
   arr[4] = 5 ;
   ```

   Here we must know the size of array and initialize the elements one by one

4. Method four 

   ```c
   int arr[5] ;
   for (i = 0 ; i < 5 ; i++)
   {
       scanf ("%d" , &arr[i]) ;
   }
   ```

   Here we must know the size of array and initialize the elements one by one by taking the value from the user 

> What if number of element are lesser than the length specified ? 
>
> The remaining locations of the array are filled by value 0
>
> ```c
> int arr[9] = {1, 2, 3, 4, 5} ; // {1, 2, 3, 4, 5 , 0 , 0 , 0 , 0}
> ```
>
> What's this program is matched ?
>
> ```c
> int arr[10] ;
> for (i = 0 ; i < 10 ; i++)
> {
>     arr[i] = 0 ;
> }
> ```
>
> we can write: **int arr[10] = {0} ;**
>
> Why not **int arr[10] = { }**
>
> Because this's illegal, you must have to specify at least 1 element, it can't be completely empty and **it's also illegal to add more element that the length of an array**
>
> ```c
> int arr[5] = {1, 2, 3, 4, 5 , 6} ;
> ```

Sometime we want to initialize the array like this

```c
int arr[10] = {1 , 0 , 0 , 0 , 0 , 2 , 0 , 0 , 3 , 0}
```

So we use **Designated Initialization** , we write something like this 

```c
int arr[10] = {[0] = 1 , [5] = 2 , [8] = 3} ;
```

Each number in the square brackets is said to be a **designator**

Advantages of Designated Initialization:

1. No need to bother about the entries containing  zeros 

2. No need to bother about the order at all

   ```c
   int arr[10] = {[5] = 2 , [0] = 1 , [8] = 3} ;
   ```

3. We can mix between Designated Initialization and another method

   ```c
   int arr[10] = {1, 2, 3, [5] = 5 , 6, 7 , [9] = 10} ;
   ```

   But if there's a clash, then Designated Initializer will win

   ```c
   int arr[10] = {1, 2, 3, [2] = 5 , 6, 7 , [9] = 10} ; // {1 , 2 , 5 , ....}
   ```

> - If the length of an array is 'n' , then each designator must between 0 and n - 1
>
> - If I won't mention the length, the compiler will deduce the length of the array from the largest designator in the list 
>
>   ```c
>   int arr[] = {[5] = 2 , [0] = 1 , [8] = 3} ;
>   ```
>
>   Here the compiler deduce the maximum length of this array would be 9 

### Array with sizeof() Operator

How many elements in arrays bellow 

```c
int a[] = {898 , 86 , 985 , 9565 , 6384 , 865 , 86438 , 4464 , , 9565 , 6384 , 865 , 86438 , 4464 , 5 , 995 , 484 , 787 , 56 , 1 , 46 , 8468 , 43 , 456 } ;

int b[] = {1 , 5 , 5 , 898 , 86 , 985 , 9565 , 6384 , 865 , 86438 , 4464 , 5 , 995 , 484 , 787 , 56 , 1 , 46 , 8468 , 43 , 456 , 898 , 86 , 985 , 9565 , 6384 , 865 , 86438 , 4464 , 898 , 86 , 985 , 9565 , 6384 , 865 , 86438 , 4464 , 43 , 456 , 898 , 86 , 985 , 9565 , 6384 , 865 , 86438 , 4464 , 898 , 86 , 985 , 9565 , 6384 , 865 , 86438 , 4464 , 1 , 5 , 5 , 898 , 86 , 985 , 9565 , 6384 , 865 , 86438 , 4464 , 5 , 995 , 484 , 787 , 56 , 1 , 46 , 8468 , 43 , 456 , 898 , 86 , 985 , 9565 , 6384 , 865 , 86438 , 6384 , 865 , 86438 , 4464 , 43 , 456 , 898 , 86 , 985 , 9565 , 6384 , 865 , 86438 , 4464 , 898 , 86 , 985 , 9565 , 6384 , 865 , 86438 , 4464 , 1 , 5 , 5 , 898 , 86 , 985 , 9565 , 6384 , 865 , 86438 , 4464 , 5 , 995 , 484 , 787 , 56 , 1 , 46 , 8468 , 43 , 456 , 898 , 86 , 985 , 9565 , 6384 , 865 , 86438} ;
```

Of course this's waste of our time, so let's make a better solution with help of **sizeof( )** operator 

If you remember, we said that **size of array = no. of element * sizeof(data_type)**

So if we divide the **size of array** over **sizeof(data_type)** , then will get **no. of element**

**no. of element = sizeof(array) / sizeof(data_type)**

```c
#include<stdio.h>
 int main()
  {
      int b[] = {1 , 5 , 5 , 898 , 86 , 985 , 9565 , 6384 , 865 , 86438 , 4464 ,
       5 , 995 , 484 , 787 , 56 , 1 , 46 , 8468 , 43 , 456 , 898 , 86 , 985 , 9565 ,
       6384 , 865 , 86438 , 4464 , 898 , 86 , 985 , 9565 , 6384 , 865 , 86438 , 4464
       , 43 , 456 , 898 , 86 , 985 , 9565 , 6384 , 865 , 86438 , 4464 , 898 , 86 , 985 , 9565
        , 6384 , 865 , 86438 , 4464 , 1 , 5 , 5 , 898 , 86 , 985 , 9565 , 6384 , 865 , 86438 , 4464 
           ,5, 995 , 484 , 787 , 56 , 1 , 46 , 8468 , 43 , 456 , 898 , 86 , 985 , 9565 , 6384 , 865 , 
                 86438 , 6384, 865 , 86438 , 4464 , 43 , 456 , 898 , 86 , 985 , 9565 , 6384 
                     , 865 ,86438 , 4464 , 898 , 86 , 985, 9565 , 6384 , 865 , 86438 , 4464 , 1 , 5 
                     , 5 , 898 , 86 , 985 , 9565 , 6384 , 865 , 86438 , 4464 , 5 , 99, 484 , 787 , 56 
                     , 1 , 46 , 8468 , 43 , 456 , 898 , 86 , 985 , 9565 , 6384 , 865 , 86438} ;
    printf("%d" , sizeof(b) / sizeof(b[0])) ;
  }

```

The output of this program is ...![86](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\86.PNG)

### Multidimensional Arrays

Multidimensional Arrays can be defined as an **array of array** , we will learn about (2D array , 3D array)

```c
data_type array_name [no. of elements1][no. of elements2] ... [no. of elementsN] ;
// for example
int arr [5][5] ;	// 2D array
char c [8][8][2] ;	// 3D array
```

Compiler will allocate a contiguous block of memory by calculated by multiplying the size of all the dimensions

 **size of ND array = no. of element1 * no. of element2 .... * no. of elementN  * sizeof(data_type)**

> We can store up to 200 elements in 2D array and up to 800 elements in 3D array

1. **2D Array**

   We can say 2D array is a basically a matrix, it has a number of rows and number of columns

   ```c
   int arr [2][3] ;
   // 2 equal the number of rows, 3 equal the number of columns 
   ```

   - **Initialize 2D array**

     1. Method 1

        ```c
        int arr[2][3] = {1 , 2 , 3 , 4 , 5 , 6} ; // It's confusing 
        ```

        |               | Element 0 | Element 1 | Element 2 |
        | :-----------: | :-------: | :-------: | :-------: |
        | **Element 0** |     1     |     2     |     3     |
        | **Element 1** |     4     |     5     |     6     |

     2. Method 4

        ```c
        //				   row 1 		row 2
        int arr[2][3] = {{1 , 2 , 3} , {4 , 5 , 6}} ; // Better method 
        ```

        |               | Element 0 | Element 1 | Element 2 |
        | :-----------: | :-------: | :-------: | :-------: |
        | **Element 0** |     1     |     2     |     3     |
        | **Element 1** |     4     |     5     |     6     |

     3. Method 3

        ```c
        int arr[2][3] ;
        arr[0][0] = 1 ;
        arr[0][1] = 2 ;
        arr[0][2] = 3 ;				// Bad method
        arr[1][0] = 4 ; 
        arr[1][1] = 5 ;
        arr[1][2] = 6 ;
        ```

        |               | Element 0 | Element 1 | Element 2 |
        | :-----------: | :-------: | :-------: | :-------: |
        | **Element 0** |     1     |     2     |     3     |
        | **Element 1** |     4     |     5     |     6     |

     4. Method 4

        ```c
        int arr[2][3] ;
        for (i = 0 ; i < 2 ; i++)
        {
            for (j = 0 ; j < 3 ; j++)
            {
                scanf ("%d" , &arr[i][j]) ;
            }
        }
        ```

        Initialize the elements one by one by taking the value from the user 

   - **Access 2D Array Elements**

     We can access the array element by mention the position they are stored in 

     Let's learn how to print 2D array elements, we're using 2 nested loop

     ```c
     for (i = 0 ; i < 2 ; i++)
     {
         for (j = 0 ; j < 3 ; j++)
         {
             printf ("%d " , arr[i][j]) ;
         }
         printf ("\n") ;			// new line for new row 
     }
     /*
     	i = 0 , j = 0	a[0][0]
     	i = 0 , j = 1	a[0][1]
     	i = 0 , j = 2	a[0][2]
     	i = 1 , j = 0	a[1][0]
     	i = 1 , j = 1	a[1][1]
     	i = 1 , j = 2	a[1][2]
     */
     ```

2. **3D Array**

   We can say 3D array is a basically a multi matrix, it has a number of matrix, number of rows and number of columns

   ```c
   int arr [2][2][3] ;
   // 2 equal the number of matrix, , 3 equal the number of rows, 3 equal the number of columns 
   ```


|          | M0C0 | M0C1 | M0C2 |          | M1C0 | M1C1 | M1C2 |
| :------: | :--: | :--: | :--: | :------: | :--: | :--: | :--: |
| **M0R0** | E000 | E001 | E002 | **M1R0** | E100 | E101 | E102 |
| **M0R1** | E010 | E011 | E012 | **M1R1** | E110 | E111 | E112 |

   - **Initialize 2D array**

     1. Method 1

        ```c
        int arr[2][2][3] = {1 , 2 , 3 , 4 , 5 , 6 , 7 , 8 , 9 , 10 , 11 , 12} ; // It's confusing 
        ```

        |          | M0C0 | M0C1 | M0C2 |          | M1C0 | M1C1 | M1C2 |
        | :------: | :--: | :--: | :--: | :------: | :--: | :--: | :--: |
        | **M0R0** |  1   |  2   |  3   | **M1R0** |  7   |  8   |  9   |
        | **M0R1** |  4   |  5   |  6   | **M1R1** |  10  |  11  |  12  |

     2. Method 4

        ```c
        //						  matrix 1	 				  matrix 2
        //					 row 1   	   row 2		row 1			row 2
        int arr[2][2][3] = {{1 , 2 , 3} , {4 , 5 , 6}}, {{7 , 8 , 9} , {10 , 11 , 12}} ; // Better method 
        ```

        |          | M0C0 | M0C1 | M0C2 |          | M1C0 | M1C1 | M1C2 |
        | :------: | :--: | :--: | :--: | :------: | :--: | :--: | :--: |
        | **M0R0** |  1   |  2   |  3   | **M1R0** |  7   |  8   |  9   |
        | **M0R1** |  4   |  5   |  6   | **M1R1** |  10  |  11  |  12  |

     3. Method 3

        ```c
        int arr[2][2][3] ;
        arr[0][0][0] = 1 ;
        arr[0][0][1] = 2 ;
        arr[0][0][2] = 3 ;				
        arr[0][1][0] = 4 ; 
        arr[0][1][1] = 5 ;
        arr[0][1][2] = 6 ;							// Bad method
        arr[1][0][0] = 7 ;
        arr[1][0][1] = 8 ;
        arr[1][0][2] = 9 ;				
        arr[1][1][0] = 10 ; 
        arr[1][1][1] = 11 ;
        arr[1][1][2] = 12 ;
        ```

        |          | M0C0 | M0C1 | M0C2 |          | M1C0 | M1C1 | M1C2 |
        | :------: | :--: | :--: | :--: | :------: | :--: | :--: | :--: |
        | **M0R0** |  1   |  2   |  3   | **M1R0** |  7   |  8   |  9   |
        | **M0R1** |  4   |  5   |  6   | **M1R1** |  10  |  11  |  12  |

     4. Method 4

        ```c
        int arr[2][3] ;
        for (i = 0 ; i < 2 ; i++)
        {
            for (q = 0 ; q < 2 ; q++)
            {
                for (j = 0 ; j < 3 ; j++)
                {
                    scanf ("%d" , &arr[i][q][j]) ;
                }
            }
        }
        ```

        Initialize the elements one by one by taking the value from the user 

   - **Access 2D Array Elements**

     We can access the array element by mention the position they are stored in 

     Let's learn how to print 3D array elements, we're using 3 nested loop

     ```c
     for (i = 0 ; i < 2 ; i++)
     {
         for (q = 0 ; q < 2 ; q++)
         {
             for (j = 0 ; j < 3 ; j++)
             {
                 printf ("%d " , arr[i][j]) ;
             }
             printf ("\n") ;			// new line for new row
         }
         printf ("\n") ;			    // new line for new matrix
     }
     /*
     	i = 0 , q = 0 , j = 0	a[0][0][0]
     	i = 0 , q = 0 , j = 1	a[0][0][1]
     	i = 0 , q = 0 , j = 2	a[0][0][2]
     	i = 0 , q = 1 , j = 0	a[0][1][0]
     	i = 0 , q = 1 , j = 1	a[0][1][1]
     	i = 0 , q = 1 , j = 2	a[0][1][2]
     	i = 1 , q = 0 , j = 0	a[1][0][0]
     	i = 1 , q = 0 , j = 1	a[1][0][1]
     	i = 1 , q = 0 , j = 2	a[1][0][2]
     	i = 1 , q = 1 , j = 0	a[1][1][0]
     	i = 1 , q = 1 , j = 1	a[1][1][1]
     	i = 1 , q = 1 , j = 2	a[1][1][2]
     */
     ```


###  Matrix Multiplication

The size of the new matrix depended on **number of row in first matrix, number of column in second matrix**

We take the first row in first matrix and the first column in second matrix, then multiply index 1 * index 1 .... index n * index n, then sum them and added this summation in first index in new matrix, and so on

Example: Multiply this two matrix together 


|          | M0C0 | M0C1 | M0C2 |          | M1C0 | M1C1 | M1C2 |
| :------: | :--: | :--: | :--: | :------: | :--: | :--: | :--: |
| **M0R0** |  1   |  2   |  3   | **M1R0** |  1   |  2   |  3   |
| **M0R1** |  4   |  5   |  6   | **M1R1** |  4   |  5   |  6   |
| **M0R2** |  7   |  8   |  9   | **M0R2** |  7   |  8   |  9   |

Output is

|        |             C1              |             C2              |             C3              |
| :----: | :-------------------------: | :-------------------------: | :-------------------------: |
| **R0** | 1 * 1 + 4 * 4 + 7 * 7 = 66  | 1 * 2 + 2 * 5 + 3 * 8 = 36  | 1 * 3 + 2 * 6 + 3 * 9 = 42  |
| **R1** | 4 * 1 + 5 * 4 + 6 * 7 = 66  | 4 * 2 + 5 * 5 + 6 * 8 = 81  | 4 * 3 + 5 * 6 + 6 * 9 = 96  |
| **R2** | 7 * 1 + 8 * 4 + 9 * 7 = 102 | 7 * 2 + 8 * 5 + 9 * 8 = 125 | 7 * 3 + 8 * 6 + 9 * 9 = 150 |

> In order to multiply two matrixes, number of columns of first matrix must be equal number of rows in second matrix ({M1 = 3 * 3 , M2 = 3 * 3} here number of columns of M1 equal number of rows in M2) , ({M1 = 3 * 2 , M2 = 3 * 3} here number of columns of M1 not equal number of rows in M2 , so we can multiply this matrix)

###  Constant Arrays

Either one-dimensional  or multi-dimensional arrays can be made constant by starting the declaration with **const**

```c
#include<stdio.h>
 int main()
 {
    const int a[5] = {1 , 2 , 3 , 4 , 5} ;
    a[1] = 6 ;
    printf("%d" , a[1]) ;
 }
```

Error message...![90](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\90.PNG)

Advantage:

1. It assures that the program will not modify the array which may contain some valuable information 
2. It helps the compiler to catch errors by informing that is no intention to modify this array

###  Variable Length Arrays

Here we make the length of array **Variable** , like to ask the user to enter the length of array 

```c
int n ;
printf ("Enter the length of array: ") ; 
scanf ("%d" , &n) ;
int a [n] ; 
.
.
.
```

Advantage:

1. We can decide the length of the array at the time of execution 
2. No need to choose the fix length while writing the code 
3. Arbitrary expiration are available

> - Variable length arrays can't have **static** storage duration, and if you make it static, you will get an error
> - Variable length array doesn't have the initializer, and if you initialize it, you will get an error
> - **Variable length array doesn't work in all compiler, so it's compiler dependent**

### Passing Array to Function 

- **1D array**

  1. Prototype Scope 

     We passing the array return type and name for array

     ```c
     int Fun (int arr[]) ;
     ```

  2. Definition Scope

     We write the same in prototype, then our code

     ```c
     int Fun (int arr[])
     {
         // action
     }
     ```

  3. Colling Scope 

     We just write the name of the array

     ```c
     Fun (arr) ;
     ```

  >In Prototype and Definition, we can passing the size of array or not
  >
  >We will talk about passing array name in calling in pointers

- **2D array**

  1. Prototype Scope 

     We passing the array return type, name for array and **the size of array**

     ```c
     int Fun (int arr[2][2]) ;
     ```

  2. Definition Scope

     We write the same in prototype and **the size of array**, then our code

     ```c
     int Fun (int arr[2][2])
     {
         // action
     }
     ```

  3. Colling Scope 

     We just write the name of the array

     ```c
     Fun (arr) ;
     ```

  >In Prototype and Definition, we must passing the size of array
  >
  >We will talk about passing array name in calling in pointers

******

## Pointers

Pointer is a special variable that capable of storing some address, it points to a memory location where the first byte is stored, to access address of a variable to a pointer

We use the unary operator **&** (ampersand) that returns the address of that variable (it's called referencing)

We use the unary operator ***** (Asterisk) for two things (1. to declare a pointer variable, 2. to access the value stored in the address), so we use ***** to declare the pointer before it's name, and return the value of the variable located at address specified (it's called dereferencing)

> We can use **&** to cancel *****, or use ***** to cancel **&**, these operators cancel effect of each other when used one after another 

Size of pointer is fixed for a compiler, all pointer types take some number of bytes for a compiler

The reason for using pointers in a Cprogram is:

1. Pointers allow different functions to share and modify their local variables
2. To pass large structures so that complete copy of the structure can be avoided
3. Pointers enable complex “linked" data structures like linked lists and binary trees

###  Declaration 

```c
data_typr * pointer_name ;
int * ptr ;		// point to integer value
char *ptr ; 	// points to charcter value
float* ptr ;	// points to float value
```

Here data type refers to the type of the value that the pointer will point to, because it always contain the address of other object 

> There's no difference between the three declaration above, all are same 
>
> **int  *  ptr ; == int  *ptr ; == int *  ptr ;**

### Initialization 

Declaring a pointer is not enough, it's important to initialize pointer before use it

We have only one way to initialize a pointer is to assign address of some variable 

```c
int x = 5 ;		// let's imagin x address equal 1000
int *ptr ;		// let's imagin *ptr address equal 2000
ptr = &x ;		// we assign address of x (1000) to ptr, Now ptr has value equal 1000 (x address)
// The above declaration and initialization is equivalent to ..
int x = 5 , *ptr = &x ;
```

> **&** means address of operator

### Value of Operator 

**value of operator or indirection operator or dereference operator:** is an operator that is used to access the value stored at the location pointed by the pointer, it' say go to the address of object and take what is stored in the object 

```c
#include <stdio.h>
int main ()
{
    int x = 5 , *ptr = &x ;
    printf ("X = %d" , *ptr) ;
}
```

The output of this program is...![95](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\95.PNG)

We can also change the value of the object pointed by the pointer 

```c
#include <stdio.h>
int main ()
{
    int x = 10 , *ptr = &x ;
    *ptr = 4 ;
    printf ("X = %d" , x) ;
}
```

The output of this program is...![96](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\96.PNG)

- Never apply the indirection operator to the uninitialized pointer, if you da that, you will get undefined behavior

- Assigning value to an uninitialized pointer is dangerous, because we try to access address and assigned to object and this pointer don't point to any location, so we will get a **segmentation fault** error

  > **segmentation fault** error usually caused by program trying to read or write an illegal memory location 

We use **%p** to print "pointer"

```c
#include <stdio.h>
int main ()
{
    int x = 10 , *ptr = &x ;
    printf ("%d\n" , x) ;			// value of x
    printf ("%p\n" , &x) ;			// address of x
    printf ("%d\n" , *ptr) ;		// value of x
    printf ("%p\n" , ptr) ;			// address of x
    printf ("%p\n" , &ptr) ;		// address of ptr
}
```

The output of this program is...![115](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\115.PNG)

### Pointer Assignment

```c
int x = 10 ;	 	// let's imagin x address equal 1000
int *p , *q ;		// let's imagin *p address equal 2000 , *q address equal 3000
p = &x ;	// we assign address of x (1000) to p, Now p has value equal 1000 (x address)
q = p;	    // we assign p value equal 1000 (x address) to q, Now q has value equal 1000 (x address)
// Now we can print the value of x by three variable x , *p , *q
printf ("X = %d == *p = %d == *q = %d", x , *p , *q) ; // output: x = 10 == *p = 10 == *q = 10
// q = p not same as *q = *p
// in *q = *p we try to access the value in *p and assigned to *q 
int x = 10 , y = 20 ;	 	// let's imagin x address equal 1000 , y address equal 2000
int *p , *q ;			   // let's imagin *p address equal 3000 , *q address equal 4000
p = &x ;	// we assign address of x (1000) to p, Now p has value equal 1000 (x address)
q = &y;	    // we assign address of y (2000) to q, Now q has value equal 2000 (y address)
*q = *p ;   
/*
	we assign the contiant in *p point to address 1000 (x address) 
	to *q point to address 2000 (y address) 
	Now the value in y equal the value of x 
*/
printf ("X = %d == y = %d == *p = %d == *q = %d", x , y , *p , *q) ;
// output: x = 10 == y = 10 == *p = 10 , *q = 20 
```

### Returning Pointers

Let's see that with example 

```c
#include <stdio.h>
int *findMid(int arr[] , int n) ;
int main ()
{
    int arr[] = {1 , 2 , 3 , 4 , 5} ;
    int n = sizeof(arr) / sizeof(arr[0]) ;
    int *mid = findMid (arr , n) ;
    printf ("%d" , *mid) ;
}
int *findMid (int arr[] , int n)
{
    return &arr[n / 2] ;
}
```

The output of this program is...![98](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\98.PNG)

Here we make the return type of the function as pointer variable, therefore to be able to return an address of what we need to, consider, never ever try to return the address of an automatic local variable

```c
#include <stdio.h>
int *fun (void)
{
    int i = 10 ;
    return &i ;
}
int main ()
{
    printf ("%d" , *fun()) ;
}
```

Error message...![99](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\99.PNG)

Here we try to return a local variable after the function destroyed and popped from stack, therefore we got this warning, because we try to access a destroyed location 

### Pointer Arithmetic

Pointer arithmetic it's mean nothing unless performed on an array, so let's take some important notes in array first

> As we know, the array is a contiguous block of memory, so the begging address of array is a location address of the first element in array **arr[0]** , but in C the name of the array is the base address of the array, it saved in read only memory, therefore we can access the location address of first element of array using the name of the array **arr** , note that, we can use array name as pointers, but assigning a new address to them is not possible because it saved in **read only memory**
>
> The index address location we need to access in array equal .. (&arr[0] + index * size of element type) or (arr +  index * size of element type)
>
> Array parameters treated as pointers because of **efficiency**, we want to deal with the array not take a copy from it 
>
> The compiler convert the array operation in pointers before accessing the array element, let's explain some tricks bellow 
>
> ```c
> #include <stdio.h> 
> int main ()
> {
>     int arr[3] = {0 , 1 , 2} ;
>     printf ("%d\n" , arr[0]) ;			// prints 0
>     printf ("%d\n" , *arr) ;		    // prints 0
>     printf ("%d\n" , *(arr + 0)) ;		// prints 0
>     printf ("%d\n" , 0[arr]) ;			// prints 0
>     printf ("%d\n" , *(0 +arr)) ;		// prints 0
>     printf ("%d\n" , arr[1]) ;			// prints 1
>     printf ("%d\n" , *arr + 1) ;	     // prints 1
>     printf ("%d\n" , *(arr + 1)) ;	   	 // prints 1
>     printf ("%d\n" , 1[arr]) ;			// prints 1
>     printf ("%d\n" , *(1 +arr)) ;		// prints 1
>     printf ("%d\n" , arr[2]) ;			// prints 2
>     printf ("%d\n" , *arr + 2) ;		// prints 2
>     printf ("%d\n" , *(arr + 2)) ;		// prints 2
>     printf ("%d\n" , 2[arr]) ;			// prints 2
>     printf ("%d\n" , *(2 +arr)) ;		// prints 2
> }
> ```

We can access the address of first element of array, let's see how 

```c
int arr[10] ; 
int *ptr = arr ; 
// or
int *qtr = &arr[0] ;
```

Now Let's take the Arithmetic in pointer  

1. **Adding**

   If we need to access any forward indexes addresses location for array we just can make that 

   ```c
   int arr[10] ; 
   int *ptr = arr ; 
    // i equal any index of array 
   ptr += i ;	/* or */ 	ptr = arr + i ;
   // If p pointing to arr[ i ] , j is new index we need to access
   ptr += j ;	/* or */	ptr = &a[i + j] ;
   ```

2. **Subtraction**

   If we need to access any backward indexes addresses location for array we just can make that 

   ```c
   int arr[10] ; 
   int *ptr = arr ; 
    // i equal any index of array 
   ptr -= i ;	/* or */ 	ptr = arr - i ;
   // If p pointing to arr[ i ] , j is new index we need to access
   ptr -= j ;	/* or */	ptr = &a[i - j] ;
   ```

   > You need to make sure you don't access illegal address location 

   We can calculate the distance between pointers 

   ```c
   int *p = &arr[2] , *q = &arr[5] , dis;
   dis = q - p ; // here distance equal 3
   dis = p - q ; // here distance equal -3
   /*
   	let's say p contain address 1008 , q contain address 1020
   	q - p = 1020 - 1008 = 12
   	then take 12 and divide it by size of element type 
   	so q - p = 12 / no. of bytes
   */
   ```

   > Undefined Behavior 
   >
   > - Performing arithmetic an pointer which are not pointing to array element leads to undefined behavior 
   >
   >   ```c
   >   int main ()
   >   {
   >       int i = 10 , *p = &i ;
   >       printf("%d", *(p + 3)) ; // you try to access illegal address location 
   >   }
   >   ```
   >
   > - If two pointers are pointing to different arrays then performing subtraction between them leads to undefined behavior

3. **Increment & Decrement**

   - Post Increment

     ```c
     #include <stdio.h>
     int main ()
     {
         int arr[] = {1 , 2 , 3 , 4 , 5} ;
         int *p = arr ;
         printf ("%d " , *(p++)) ;
         printf ("%d " , *p) ;
     }
     ```

     This program output is...![102](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\102.PNG)

   - Pre Increment

     ```c
     #include <stdio.h>
     int main ()
     {
         int arr[] = {1 , 2 , 3 , 4 , 5} ;
         int *p = arr ;
         printf ("%d " , *(++p)) ;
         printf ("%d " , *p) ;
     }
     ```

     This program output is...![103](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\103.PNG)

   - Post Decrement

     ```c
     #include <stdio.h>
     int main ()
     {
         int arr[] = {1 , 2 , 3 , 4 , 5} ;
         int *p = &arr[2] ;
         printf ("%d " , *(p--)) ;
         printf ("%d " , *p) ;
     }
     ```

     This program output is...![104](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\104.PNG)

   - Pre Decrement

     ```c
     #include <stdio.h>
     int main ()
     {
         int arr[] = {1 , 2 , 3 , 4 , 5} ;
         int *p = &arr[2] ;
         printf ("%d " , *(--p)) ;
         printf ("%d " , *p) ;
     }
     ```

     This program output is...![105](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\105.PNG)

   > We can't do this operations in array name if we used as a pointer (++ , --)

   

4. **Comparing**

   - We can use **Relational Operator & Equality Operator** to compare pointers 
   - Only possible when the two pointers are in the same array
   - Output depends upon the relative positions of both the pointers 

   ```c
   #include <stdio.h>
   int main ()
   {
       int arr[] = {1 , 2 , 3 , 4 , 5} ;
       int *p = &arr[1] , *q = &arr[4] ;
       printf("%d\n" , q <= p) ;
       printf("%d\n" , q >= p) ;
       q = &arr[1] ;
       printf("%d\n" , q == p) ;
   }
   ```

   This program output is...![107](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\107.PNG)

### Pointer to Function 

When we create a simple pointer variable we just add ***** before the variable name 

```c
int * ptr ;
```

So if we need to create a pointer to function, we can just add ***** before the function name, right ?

```c
int * fun (int ) ;
```

No it's wrong, because as we know before, the brackets in C language has the highest level of precedence, so the function will be evaluate first, then it will return the address of returned value, and we don't need this 

So we can make the pointer evaluate first by adding the Asterisk and the function name inside a brackets 

```c
int (*fun)(int ) ;
```

Now we can use pointer to function, let's see how 

```c
#include <stdio.h> 
void fun (int ) ;
int main ()
{
    void (*fun_p)(int) = &fun ;		// fun_p is a pointer to a function 
    (*fun_p)(10) ;				   // use the function by pointer 
}
void fun (int a)
{
    printf ("Value of a is: %d" , a) ;
}
```

The output of this program is...![116](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\116.PNG)

- We don't allocate de-allocate memory using function pointers (we will know about that letter)

- Function pointers points to a code not data, also function pointer stores the start of executable code 

- Functions name can also be used to get functions address, like arrays, we don't need to write asterisk ***** and ampersand **&**

  ```c
  #include <stdio.h> 
  void fun (int ) ;
  int main ()
  {
      void (*fun_p)(int) = fun ;		 // we removed & 
      fun_p(10) ;				   		// we removed * and ()
  }
  void fun (int a)
  {
      printf ("Value of a is: %d" , a) ;
  }
  ```

  The output of this program is...![116](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\116.PNG)

- We can have array of function pointers 

- Function pointer can be used instead of switch case

  ```c
  #include <stdio.h>
  void add (int , int ) ;
  void sub (int , int ) ;
  void mlt (int , int ) ;
  int main ()
  {
      void (*fun_p [])(int , int) = {add , sub , mlt} ;
      int fun , a , b ;
      printf ("Enter 2 values: ") ;
      scanf ("%d%d" , &a , &b) ;
      printf ("Enter ID for your operation \n1 for summation\n2 for subtraction\n3 for multiplication: ") ;
      scanf ("%d" , &fun) ;
      fun_p[fun - 1](a , b) ;
  }
  void add (int a, int b)
  {
      printf ("The summation is: %d", a + b) ;
  }
  void sub (int a, int b)
  {
      printf ("The subtraction is: %d", a - b) ;
  }
  void mlt (int a, int b)
  {
      printf ("The multiplication is: %d", a * b) ;
  }
  ```

  The output is...![117](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\117.PNG)![118](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\118.PNG)![119](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\119.PNG)

- Function pointer can be passed as an argument, also can be returned from a function

  ```c
  #include <stdio.h>
  void return_fun (void (*fun)()) ;
  void fun1 (void) ;
  void fun2 (void) ;
  int main ()
  {
      return_fun(fun1) ;
      return_fun(fun2) ;
  }
  void return_fun(void (*fun)())
  {
      fun () ;
  }
  void fun1 (void)
  {
      printf ("Hey i'm fun1\n") ;
  }
  void fun2 (void)
  {
      printf ("Hey i'm fun2\n") ;
  }
  ```

  The output of this program is...![120](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\120.PNG)

  This point is very useful in C language, we can use function pointers to avoid code redundancy, we can write out own functions that can be used for any data type and can do different tasks without code redundancy, we will talk about it letter or you can search about (qsort function)

- In c++, many OOP are implemented by function pointer in C

### Array of Pointers 

First let's take this example 

```c
#include <stdio.h>
int main () 
{
   int  var[3] = {10, 100, 200};
   int i;
   for (i = 0; i < 3 ; i++) 
   {
      printf("Value of var[%d] = %d\n", i, var[i] );
   }
}
```

The output of this program is...![142](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\142.PNG)

We can do this program using array of pointers

```c
int * ptr [] ;
```

Every element in this array it will be hold an address, so lets edit the previous example 

```c
#include <stdio.h>
int main ()
{
   int  var[3] = {10, 100, 200};
   int i , * ptr[3];
   for (i = 0; i < 3 ; i++)
   {
      ptr[i] = (var + i) ;
   }
   for (i = 0; i < 3 ; i++)
   {
      printf("Value of var[%d] = %d\n", i, *ptr[i] );
   }
}
```

The output of this program is...![142](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\142.PNG)

### Passing Array to Function

In array, we said **"in calling scope, we just write the name of the array"** , now we know the array name is equivalent to base address for array, so we're not passing the whole array, we're just passing the address of the array, and we can treated the array name as a pointer, and the argument **arr[ ]** is a pointer we can also write it as ***b** 

### Printing 2D Array

Let's first know the difference between **ROW major & COLUMN major** order

1. ROW major order: Elements are stored row by row 
2. COLUMN major order: Elements are stored column by column

<img src="https://www.guideforschool.com/wp-content/uploads/2013/11/row-major-column-major-memory-address-calculation.jpg" alt="Memory Address Calculation in an Array | Guide For School" style="zoom:67%;" />

>  C stores 2D arrays in ROW major order

Now we can use the concept of ROW major order, then print the 2D array with one for loop using pointers

```c
/*
    int *p = arr ;
    for (p = &a[position of first element] ; p <= &a[position of last element] ; p++)
    {
        printf ("%d" , *p) ;
    }
*/
#include <stdio.h>
int main ()
{
    int arr[3][3] = {1 , 2 , 3 , 4 , 5 , 6 , 7 , 8 , 9}  ;
    int *p ;
    for (p = &arr[0][0] ; p <= &arr[2][2] ; p++)
    {
        printf ("%d " , *p) ;
    }
}
```

This program output is...![110](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\110.PNG)

### Address Arithmetic of Multidimensional Arrays

In 1D array, when we create an array of 4 elements we write **int a[4] ;**, and  the name of the array is the pointer to the first element of the array, so **a** is a name of array and it's point to the address of first element, therefore if the **&a[0]** is 1000 ,so **a** points to 1000 (base address), and if dereference it ***a **, I will get the contain of the first element **a[0]**

Form the concept of **ROW major & COLUMN major** order, let's see what's happened in 2D array

In 2D array, when we create an array of [2] [2] elements we write **int a[2] [2] ;** , we'll get three 1D array each contains 2 elements and the name of the array is the pointer to the first 1D array (first row), so **a** is a name of array and it's point to the address of first 1D array (first row), let's imagine the picture bellow

![pinter to pointer 2d array](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\pinter to pointer 2d array.png)

So the red box represent the first 1D array(first row), blue box represent the second 1D array (second row), like we see, the address of the first 1D array is equivalent to the first element of this array (a[0] [0]), both are same but the contexts are be different, also the the address of the second 1D array is equivalent to the first element of this array (a[1] [0])

```pseudocode
pointing the outer frame (1Ds arrays)
	a -> 1000		    								(pointer to 1st 1D array)
	a + 1 -> 1008										(pointer to 2nd 1D array)
pointing the address of elements in array
	*a == *(a + 0) == a[0] == &a[0][0]		 			 (pointer to 1st element in 1st 1D array)
	*a + 1 == *(a + 0) + 1 == a[0] + 1 == &a[0][1]		  (pointer to 2nd element in 1st 1D array)
	*(a + 1) == a[1] == &a[1][0]						(pointer to 1st element in 2nd 1D array)
	*(a + 1) +  1 == a[1] + 1 == &a[1][1]				 (pointer to 2nd element in 2nd 1D array)
accessing the elements of array
	**a == *(*a) == *(*(a + 0)) == *(a[0]) == *(&a[0][0])	 (access to 1st element in 1st 1D array)
	**a + 1 == *(*a + 1) == *(a[0] + 1) == *(&a[0][1])		 (access to 2nd element in 1st 1D array)
	**(a + 1) == *(*(a + 1)) == *(a[1]) == *(&a[1][0])		 (access to 1st element in 2nd 1D array)
	**(a + 1) + 1==*(*(a + 1) + 1)==*(a[1] + 1)==*(&a[1][1]) (access to 2nd element in 2nd 1D array)
```

Form the concept of 2D array, let's see what's happened in 3D array

In 2D array, when we create an array of [2] [2] [2] elements we write **int a [2] [2] [2] ;** , we'll get two 2D array each contains two 1D array and each of these array have 2 elements and the name of the array is the pointer to the first 2D array, so **a** is a name of array and it's point to the address of first 2D array, let's imagine the picture bellow

![pinter to pointer to pointer 3d array edit](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\pinter to pointer to pointer 3d array edit.png)

So the red box represent the first 2D array, blue box represent the second 2D array, inside of the red box, white box represent the first 1D array in first 2D array, black box represent the second 1D array in first 2D array, inside of the blue box, green box represent the first 1D array in second 2D array, yellow box represent the second 1D array in second 2D array, like we see, the address of the first 2D array is equivalent to the first 1D array and the first element of this array (a[0] [0] [0]), both are same but all the contexts are be different, also the the address of the second 2D array is equivalent to the first 1D array and the first element of this array (a[1] [0])

```pseudocode
pointing the outer frame (2Ds arrays)
	(a) -> 1000		    								(pointer to 1st 2D array)
	(a + 1) -> 1016										(pointer to 2nd 2D array)
pointing the outer frame (1Ds arrays)
	*(a) -> 1000	    								(pointer to 1st 1D array in 1st 2D array)
	*(a) + 1 -> 1008	    							(pointer to 2nd 1D array in 1st 2D array)
	*(a + 1) -> 1016									(pointer to 1st 1D array in 2nd 2D array)
	*(a + 1) + 1 -> 1024								(pointer to 2nd 1D array in 2nd 2D array)
pointing the address of elements in array 
	*(*(a)) == &a[0][0][0]	 			    (pointer to 1st element in 1st 1D array in 1st 2D array)
	*(*(a) + 1) == &a[0][0][1]				(pointer to 2nd element in 1st 1D array in 1st 2D array)
	*(*(a + 1)) == &a[1][0][0]				(pointer to 1st element in 1st 1D array in 2nd 2D array)
	*(*(a + 1) + 1) == &a[1][0][1]			(pointer to 2nd element in 1st 1D array in 2nd 2D array)
accessing the elements of array
	(access to 1st element in 1st 1D array in 1st 2D array)
				 *(*(*(a))) == *(&a[0][0][0])
	(access to 2nd element in 1st 1D array in 1st 2D array)
				*(*(*(a)) + 1) == *(&a[0][0][1])
	(access to 1st element in 2nd 1D array in 1st 2D array)
				 *(*(*(a) + 1)) == *(&a[0][0][0])
	(access to 2nd element in 1st 1D array in 1st 2D array)
				*(*(*(a) + 1) + 1) == *(&a[0][0][1])
	(access to 1st element in 1st 1D array in 2nd 2D array)
				*(*(*(a + 1))) == *(&a[1][0][0])
	(access to 2nd element in 1st 1D array in 2nd 2D array)
				 *(*(*(a + 1)) + 1) == *(&a[1][0][1])
	(access to 1st element in 2nd 1D array in 2nd 2D array)
				*(*(*(a + 1) + 1)) == *(&a[1][0][0])
	(access to 2nd element in 2nd 1D array in 2nd 2D array)
				 *(*(*(a + 1) + 1) + 1) == *(&a[1][0][1])
```

```c
#include <stdio.h>
int main ()
{
    int a[2][2][2] = {1 , 2 , 3 , 4 , 5 , 6 , 7 , 8}  ;
    printf ("%d " , *(*(*(a)))) ;
    printf ("%d " , *(*(*(a)) + 1)) ;
    printf ("%d " , *(*(*(a) + 1))) ;
    printf ("%d " , *(*(*(a) + 1) + 1)) ;
    printf ("%d " , *(*(*(a + 1)))) ;
    printf ("%d " , *(*(*(a + 1)) + 1)) ;
    printf ("%d " , *(*(*(a + 1) + 1))) ;
    printf ("%d " , *(*(*(a + 1) + 1) + 1)) ;
}
```

This program output is...![111](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\111.PNG)

### Pointer Pointing to an Entire Array 

Let's consider we have the bellow program 

```c
#include<stdio.h>
int main()
{
    int a[5] = {1 , 2 , 3 , 4 , 5} ;
    int *p = a ;					// pointer to first element in array
    printf ("%d" , *p) ;
    return 0 ;
}
```

This program output is...![112](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\112.PNG)

So now if we replace ***p = a** with **(*p)[5]**, what's this means ? 

```c
#include<stdio.h>
int main()
{
    int a[5] = {1 , 2 , 3 , 4 , 5} ;
    int (*p) [5] = &a ;					// what's this means ???!
    printf ("%d" , **p) ;				// why two * ? 
    return 0 ;
}
```

Let's first read this line **(*p)[5]**, p is a pointer to 5 integer elements, it's mean **p** is a pointer pointing to the whole 1D array not 1 element, it's pointing to 5 element 

![pinter pinting to whole array](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\pinter pinting to whole array.png)

So now **p** in a pointer to the whole array not to first element, if you need to access the first element, you must use dereferencing operator to ***p**

```pseudocode
int a[5] = {1 , 2 , 3 , 4 , 5} ;
int (*p) = &a ;
*p -> pointer to 1D array
**p -> pointer to 1st element in 1D array
```

We use this method to help us to enter and exit the outer frame of the array, so we can use dereferencing operator to enter ***** and referencing operator to exit **&**, because we know **&** Eliminates the effect of *****

### Difference Between Pointers & Arrays

Pointers are used for storing address of dynamically allocated arrays and for arrays which are passed as arguments to functions

1. **& operator**

   - Arrays: if we use & operator before array name it returns the address of the first element in array (&arr[0])
   - Pointers: if we use & operator before pointer name it returns the address of pointer

2. **sizeof( ) operator**

   - Arrays: it returns the amount of memory used by all elements in array 
   - Pointers: it returns the amount of memory used by the pointer variable it self 

3. **String litters**

   - Arrays: **char arr[ ] = "abc"**, that's the first 4 elements in array ('a', 'b' , 'c' , '\0') 
   - Pointers: **char *p = "abc"**, that's the address of the "abc" string

4. Pointer variable can be assigned to a value, but array variable can't be

   ```c
   int arr[10] ; 
   int * p ;
   p = arr ; // can be 
   arr = q ; // can't be
   ```

5. Arithmetic on pointer variable is allowed, but array are not 

   ```c
   int arr[10] ; 
   int * p = arr ;
   p++ ;   // can be 
   arr++ ; // can't be
   ```

6. Array parameters are always passed as pointers, even when we use square brackets

### Void Pointer 

The void pointer is a generic pointer, is a special type of the special variable **pointer**, that point to some address location, we can declare the void pointer as any pointer, but we must use the keyword **void** as a pointer type, void pointer doesn't have a special type, if you assigned to char type it will be a character pointer, and if you assigned to int type it will be an integer pointer 

```c
int x = 5 ; 
void *p = &x ;
```

- We use void pointer in C to impalement generic functions, like compare function which is used in qsort() function 
- Void pointer is a return of **malloc() & callloc()** functions (we will take about letter)
- We can't make dereferencing operator in void pointer until we make a typecasting 
- We can't make pointer arithmetic in void pointer until we make a typecasting 

### Dangling Pointer 

When you use a pointer to point to a memory location, then this location has been deleted or freed, is called dangling pointer, there're three ways to name the pointer **dangling pointer**

1. Variable goes out of scope 

   ```c
   int main ()
   {
       int *p ;
       .....
       .....
       {
           int x = 5 ; 
           p = &x ;
       }
       // Here p is a dangling pointer 
   }
   ```

2. After function call

   ```c
   int * fun (void)
   {
       int x = 5 ; 
       return &x ;
   }
   int main ()
   {
       int *p = fun () ;
       printf ("%d" , *p) ;		// you will get a garbage address
   }
   /*
   	x is a local variable and after te function scope it will be over and destroyed
   */
   ```

3. De-allocation of memory 

   We will know about it in **Dynamic Memory Allocation**, but know we need to know if we reserved a location, then free it, so the pointer is point on this location will be a dangling pointer 

### NULL Pointer

NULL Pointer is a pointer which is pointing to nothing, if we don’t have address to be assigned to a pointer, then we can simply use NULL

```c
int * p ;
p = NULL ;  // p pointing to nothing 
```

We use NULL pointer for: 

1. To initialize a pointer variable when that pointer variable isn’t assigned any valid memory address yet
2. To check for a null pointer before accessing any pointer variable. By doing so, we can perform error handling in pointer related code, dereference pointer variable only if it’s not NULL
3. To pass a null pointer to a function argument when we don’t want to pass any valid memory address

NULL pointer is different from an wild and dangling pointer, in a specific program context, all wild or dangling or NULL pointers are invalid but NULL is a specific invalid pointer which is mentioned in C standard and has specific purposes, what we mean is that wild and dangling pointers are invalid but they can point to some memory address that may be accessible through the memory access is unintended

- If we create a NULL pointer, then this pointer is an uninitialized pointer, so it will be stores an undefined value, but one that is defined it will be a valid address for any object 

- NULL pointer is a value, while void pointer is a type 

- It's better to initialized pointer variables as NULL, and perform NULL check before accessing any pointer

- Size of NULL pointer is like as size of any pointer, if the pointer size is 4 bytes, then NULL pointer also equal 4 bytes

- Value of NULL pointer equal 0, but not like 0 as integer, let's see what's that means

  ```c
  printf ("%d" , NULL) ;		// prints 0
  printf ("%c" , NULL) ;		// prints sqace 
  printf ("%f" , NULL) ;		// prints 0.00000
  printf ("%s" , NULL) ;		// prints (null)
  ```

- If we're trying to dereference NULL pointer, we will get a undefined behaver, because it's a machine dependent  

### Wild Pointer 

Wild pointer is a pointer not been initialized to any values, even NULL, is known as wild pointer, the pointer maybe initialized to a non-NULL garbage value that may not be a valid pointer 

```c
int * p ; // wild pointer until initialization 
```

### Const Pointer

There're three uses of const with pointer 

1. Only const pointer 

   This is a constant pointer to non-constant data type, you cannot change the pointer, but can change the value pointed by pointer 

   ```c
   #include <stdio.h>
   int main ()
   {
       char a = 'A' , b = 'B' ;
       char * const p = &a ;
       printf ("Value pointed to pointer: %c\n" , *p) ;
       printf ("Address p pointed to: %p\n" , p) ;
       // p = &b 	this's illegal statement, because p variable assignment to read-only memory
       *p = b ;
       printf ("Value pointed to pointer: %c\n" , *p) ;
       printf ("Address p pointed to: %p\n" , p) ;
   }
   ```

   This program output is...![121](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\121.PNG)

2. Only const data type

   This is a constant data type to non-constant pointer, you can't change the value pointed by pointer , but can change the pointer 

   ```c
   #include <stdio.h>
   int main ()
   {
       char a = 'A' , b = 'B' ;
       const char * p = &a ;
       printf ("Value pointed to pointer: %c\n" , *p) ;
       printf ("Address p pointed to: %p\n" , p) ;
       // *p = b 	this's illegal statement, because p location assignment to read-only memory
       p = &b ;
       printf ("Value pointed to pointer: %c\n" , *p) ;
       printf ("Address p pointed to: %p\n" , p) ;
   }
   ```

   This program output is...![122](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\122.PNG)

3. const data type, const pointer 

   This is a constant pointer to constant character, you can neither change the value pointed by pointer, or the pointer

   ```c
   #include <stdio.h>
   int main ()
   {
       char a = 'A' , b = 'B' ;
       const char * const p = &a ;
       printf ("Value pointed to pointer: %c\n" , *p) ;
       printf ("Address p pointed to: %p\n" , p) ;
       // *p = b 	this's illegal statement, because p location assignment to read-only memory
       // p = &b 	this's illegal statement, because p variable assignment to read-only memory
   }
   ```

   This program output is...![123](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\123.PNG)

******

## Question Set 5

### Question 1

Write a program to print the array element in reverse order

```c
#include<stdio.h>
 int main()
  {
      int arr[10] , i ;
      for (i = 0 ; i < 10 ; i++)
      {
		  printf ("Enter Number %d: " , i + 1) ;
          scanf("%d" , &arr[i]) ;
      }
	  printf ("The values in reversed order\n") ;
	  for (i = 9 ; i >= 0 ; i--)
      {
          printf ("%d\n" , arr[i]) ;
      }
  }
```

The output of this program is ...![83](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\83.PNG)

### Question 2

Write a program to check whether any of the digits in a number appears more than one 

```c
#include<stdio.h>
 int main()
  {
      int num , i , arr[10] = {0} ;
      printf ("Enter Number: ") ;
          scanf("%d" , &num) ;
      while (num != 0)
      {
		  arr[num % 10]++ ;
		  num /= 10 ;
      }
	  for (i = 0 ; i < 10 ; i++)
      {
          if (arr[i] > 1)
          {
              printf ("Yes") ;
              return 0 ;
          }
      }
      printf ("No") ;
      return 0 ;
  }
/*
Here we use the concept of frequancy array (Search about it)
we count all digit in an array, then check if any counter greater than 1
*/
```

The output of this program is ...![84](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\84.PNG)![85](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\85.PNG)

### Question 3

Write a program that read a 5 x 5 array of integers and then prints the row sum and the columns sum, like that...

```pseudocode
Enter row 1: 8 3 9 0 10
Enter row 2: 3 5 17 1 1
Enter row 3: 2 8 6 23 1
Enter row 4: 15 7 3 2 9
Enter row 5: 6 14 2 6 0

Row total: 30 27 40 36 28
Column total: 34 37 37 32 21
```

```c
#include<stdio.h>
int main()
{
    int a [5][5] , sum , i , j ;
    for (i = 0 ; i < 5 ; i++)
    {
        printf ("Enter row %d: " , i + 1) ;
        for (j = 0 ; j < 5 ; j++)
        {
            scanf ("%d" , &a[i][j]) ;
        }
    }
    printf ("Row total: ") ;
    for (i = 0 ; i < 5 ; i++)
    {
        sum = 0 ;
        for (j = 0 ; j < 5 ; j++)
        {
            sum += a[i][j] ;
        }
        printf ("%d " , sum) ;
    }

    printf ("\nColumn total: ") ;
    for (i = 0 ; i < 5 ; i++)
    {
        sum = 0 ;
        for (j = 0 ; j < 5 ; j++)
        {
            sum += a[j][i] ;
        }
        printf ("%d " , sum) ;
    }

}
```

The output of this program is ...![87](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\87.PNG)

### Question 4

Write a program to multiply two matrixes

```c
#include<stdio.h>
 int main()
 {
     int M1R , M1C , M2R , M2C , sum = 0 , i , j , q ;
     printf("Enter the rows and columns of matrix a: ") ;
     scanf("%d%d" , &M1R , &M1C) ;
     int a [M1R][M1C] ;
     printf ("Enter Matrix a\n") ;
     for (i = 0 ; i < M1R ; i++)
     {
        for (j = 0 ; j < M1C; j++)
        {
            scanf ("%d" , &a[i][j]) ;
        }
     }
     printf("Enter the rows and columns of matrix b: ") ;
     scanf("%d%d" , &M2R , &M2C) ;
     int b [M2R][M2C] ;
     printf ("Enter Matrix b\n") ;
     for (i = 0 ; i < M2R ; i++)
     {
        for (j = 0 ; j < M2C; j++)
        {
            scanf ("%d" , &b[i][j]) ;
        }
     }
     int c [M1R][M2C] ;
     if (M1C == M2R)
     {
         for (i = 0 ; i < M1R ; i++)
         {
            for (j = 0 ; j < M2C; j++)
            {
                for (q = 0 ; q < M2R; q++)
                {
                    sum+= a[i][q] * b[q][j] ;
                }
                c [i][j] = sum ;
                sum = 0 ;
            }
         }
         for (i = 0 ; i < M1R ; i++)
         {
            for (j = 0 ; j < M2C; j++)
            {
                printf ("%d " , c[i][j]) ;
            }
             printf ("\n") ;
         }
     }
      else
      {
          printf("We can multiply this matrix\nbecause number of columns of M1 not equal number of 					rows in M2") ;
      }
 }
```

The output of this program is ...![88](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\88.PNG)

![89](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\89.PNG)

### Question 5

Find the largest and smallest element in array using pointer 

```c
#include <stdio.h>
void MAX_MIN (int arr[] , int len , int *max , int *min) ;
int main ()
{
    int arr[] = {1 , 2 , 5 , 8 , 9 , 46 , 31 , -5} ;
    int max , min , len = sizeof(arr) / sizeof(arr[0]) ;
    MAX_MIN (arr , len , &max , &min) ;
    printf ("max element = %d , min element = %d" , max , min) ;
}
void MAX_MIN (int arr[] , int len , int *max , int *min)
{
    int i ;
    *max = *min = arr[0] ;
    for (i = 0 ; i < len ; i++)
    {
        if (arr[i] < *min)
        {
            *min = arr[i] ;
        }
        if (arr[i] > *max)
        {
            *max = arr[i] ;
        }
    }
}
```

This program output is...![97](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\97.PNG)

### Question 6

Consider the following two statement, first statement is the declaration and second is simple assignment statement, why isn't second statement p is preceded * symbol ?

```c
int *p = &i ;
p = &i ;
```

In C, * symbol ha different meanings depended on the context in which it's used, at the time of the declaration, * symbol isn't acting as an indirection operator, it tells the compiler that p is a pointer to an integer, but if we write ***p = &i** then it's wrong, because here * symbol indicates the indirection operator and we can't assign the address to some integer variable, because pointer variables can only hold addresses and normal variable can only hold values, therefore in second statement we don't need * symbol in front of p, because it simply means, we are assigning the address to a pointer 

### Question 7

What's the output of this program ?

```c
void fun (const int *p)
{
    *p = 0 ;
}
int main ()
{
    const int i = 10 ;
    fun (&i) ;
    return 0 ;
}
/*
	we trying to assing a constant variable, so we will get error 
	beacuse we try to access a read only location
*/
```

Error message...![100](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\100.PNG)

### Question 8

How to print the address of a variable 

```c
#include <stdio.h>
int main ()
{
    int i = 10 , *ptr = &i ;
    printf ("%d" , ptr) ;
    return 0 ;
}
```

This program output is...![101](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\101.PNG) the output is different from machine to machine 

### Question 9

If **i** is a variable and **p** is a pointer to **i**, which of the following expressions are aliases of **i** ?

**a) *p**

b) *&p

c) &p

d) *i

**e) *&i**

```c
/*
i adress = 1000, p adress = 2000
	*p = *(1000) = 10 = i
	*&p = *(2000) = 1000 != i
	&p = 2000 != i
	*i = *(10) i not a pointer and we this statment doesn't make sense
	*&i = *(1000) = 10 = i
*/
```

### Question 10

What's the output of this program ?

```c
#include <stdio.h>
int main ()
{
    int arr[] = {5 , 16 , 7 , 89 , 45 , 32 , 23 . 10} ;
    int *p = &arr[1] , *q = &arr[5] ;
    printf("%d " , *(p + 3)) ;
    printf("%d " , *(q - 3)) ;
    printf("%d " , (q - p)) ;
    printf("%d " , (p < q)) ;
    printf("%d" , (*p < *q)) ;
}
/*
	*(p + 3) = *(&arr[4]) = 45
	*(q - 3) = *(&arr[2]) = 7
	(q - p) = 5 - 1 = 4
	(p < q) = 3 < 5 = true = 1
	(*p < *q) = 16 < 32 = true = 1
*/
```

**a) 47  7  4  1  1**

b) 47  4  7  1  1 

c) 47  7  4  1  0

d) 47  7  4  0  1

### Question 11

Write a program to sum array element using pointers 

```c
#include <stdio.h>
int main ()
{
    int arr[9] = {5 , 16 , 7 , 89 , 45 , 32 , 23 , 10} ;
    int *p , sum = 0 ;
    for (p = arr ; p <= arr + 8 ; p++)
    {
        sum += *p ;
    }
    printf("The summation is: %d" , sum) ;
}
```

This program output is...![108](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\108.PNG)

### Question 12

Write a program to printing array element in reverse order using pointers 

```c
#include <stdio.h>
#define N (5)
int main ()
{
    int arr[N] , *p;
    printf("Enter %d Elements in the Array\n" , N) ;
    for (p = arr ; p <= arr + N - 1 ; p++)
    {
        scanf ("%d" , p) ;// Note we don't write &, because p is address for array element (&arr[i])
    }
    printf("Your Enter Elements in Reverse Order is: ") ;
    for (p = arr + N - 1 ; p >= arr ; p--)
    {
        printf("%d " , *p) ;
    }
}
```

This program output is...![109](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\109.PNG)

### Question 13

Consider the following declaration of 2D array **char a [0] [0]**, assuming that the main memory is byte addressable and that array is sorted starting from the memory address 0, what's the address of **a [40] [50]** ? 

a) 4040

**b) 4050**

c) 5040

d) 5050

We can generate a formula to find the address of any element in 2D array  

```pseudocode
array_type a[X][Y] ;
as we know, sizeof(a) = X * Y * sizeof(array_type)
so if we have location a[i][j] 
the address location will be 
Base adress + sizeof(array_type) * ((i * Y) + j)
so in the previous example a[40][50]
Base adress = 0 , sizeof(array_type) = 1 byte , i = 40 , Y = 100 , j = 50
so the address = 0 + 1 * ((40 * 100) + 50) = 4050
```

### Question 14

What's the output of the following program in C ?, assuming that the address of a is 2000, and an integer requires 4 bytes of memory 

```c
#include <stdio.h>
int main ()
{
    unsigned int a[4][3] = {{1 , 2 , 3} , {4 , 5 , 6} , {7 , 8 , 9} , {10 , 11 , 12}}  ;
    printf ("%u %u %u " , x + 3 , *(x + 3) , *(x + 2) + 3) ;
}
/*
	x -> 2000
	x + 3 -> 2000 + 3 * 3 * 4 -> 2036			 (pointer to 4th 1D array)
	*(x + 3) -> *(2036) -> &a[3][0] -> 3036		 (pointer to 1st element in 4th 1D array)
	*(x + 2) + 3 -> *(2000 + 2 * 3 * 4) + 3 -> *(2024) + 3 * 4 -> 2036 
*/
```

**a) 2036 2036 2036**

b) 2012 4 2204

c) 2036 10 10

d) 2012 4 6

### Question 15

What's the output of the following C program ?

```c
#include<stdio.h>
int main()
{
    int a[ ][3] = {1 , 2 , 3 , 4 , 5 , 6} ;	// we can only write the number of columns
    int (*p) [3] = &a ;					
    printf ("%d %d" , (*p)[1] , (*p)[2]) ;
    ++p ;
    printf ("%d %d" , (*p)[1] , (*p)[2]) ;
    return 0 ;
}
/*
	p -> pointer to 1st 1D array 
	*p -> pointer to 1st element in 1st 1D array 
	(*p)[0] -> *(*(p)) -> 1
	(*p)[1] -> *(*(p) + 1) -> 2
	(*p)[2] -> *(*(p) + 2) -> 3
	then ++p -> *(p + 1) -> pointer to 2nd 1D array 
	(*p)[0] -> *(*(p + 1)) -> 4
	(*p)[1] -> *(*(p + 1) + 1) -> 5
	(*p)[2] -> *(*(p + 1) + 2) -> 6
*/
```

**a) 2 3 5 6**

b) 2 3 4 5

c) 4 5 0 0

d) None of the above 

### Question 16

What's the output of the following C program ?

```c
#include <stdio.h>
void f (int *p , int *q)
{
    p = q ;
    *p = 2 ;
}
int i = 0 , j = 1 ;
int main ()
{
    f (&i , &j) ;
    printf ("%d %d\n" , i , j) ;
    return 0 ;
}
/*
	i = 0 , j = 1
	p -> &i , q -> &j
	p = q = &j
	*p = j = 2 ;
output: 0 2
*/
```

a) 2 2

b) 2 1

c) 0 1

**d) 0 2**

### Question 17

What's the output of the following C program ?

```c
#include <stdio.h>
int f (int *a , int n)
{
    if (n <= 0)
    {
        return 0 ;
    }
    else if (*a % 2 == 0)
    {
        return *a + f(a + 1 , n - 1) ;
    }
    else
    {
        return *a - f(a + 1 , n - 1) ;
    }
}
int main ()
{
    int a[ ] = {12 , 7 , 13 , 4 , 11 , 6} ;
    printf ("%d" ,f (a , 6)) ;
    getchar() ;
    return 0 ;
}
/*
f (a[0] , 6) 												 return 15
	n != 0 , a[0] % 2 == 0		return 12 + f (a[1] , 5)		return 12 + 3
f (a[1] , 5) 
	n != 0 , a[1] % 2 != 0		return 7 - f (a[2] , 4)			return 7 - 4
f (a[2] , 4) 
	n != 0 , a[2] % 2 != 0		return 13 - f (a[3] , 3)		return 13 - 9
f (a[3] , 5) 
	n != 0 , a[3] % 2 == 0		return 4 + f (a[4] , 2)			return 4 + 5
f (a[4] , 2) 
	n != 0 , a[4] % 2 != 0		return 11 - f (a[5] , 1)		return 11 - 6
f (a[5] , 1) 
	n != 0 , a[5] % 2 == 0		return 6 + f (a[6] , 0)			return 6 + 0
f (a[6] , 0) 
	n == 0 					   return 0
*/
```

a) -9

b) 5

**c) 15**

d) 19 

### Question 18

What's the output of the following C program ?

```c
#include <stdio.h>
int f (int x , int *py , int **ppz)
{
    int y , z ;
    **ppz += 1 ;
    z = **ppz ;
    *py += 2 ;
    y = *py ;
    x += 3 ;
    return x + y + z ;
}
int main ()
{
    int c , *b , **a ;
    c = 4 , b = &c , a = &b ;
    printf ("%d" , f(c , b , a)) ;
    return 0 ;
}
/*
Let's assuming the addresses
	c = 4 at address 1000
	b = &c = 1000 at address 2000
	a = &b = 2000 at address 3000
	now in function 
	x = 4 at address 4000
	py = b = 1000 at address 5000
	ppz = a = 2000 at address 6000
	y located at address 7000
	z located at address 8000
Now let's make some operation 
	**ppz += 1 -> *(&b) += 1 -> c += 1 -> 5 at address 1000
	z = **ppz -> *(&b) -> c located at address 8000
	*py += 2 -> (&c) -> c += 2 -> 7 at address 1000
	y = *py -> (&c) -> c located at address 7000
	x += 3 -> 7 at address 4000
return x + y + z -> 7 + 7 + 5 -> 19
*/
```

a) 18

**b) 19**

c) 21

d) 22

### Question 19

What's the output of the following C program ?

```c
#include <stdio.h>
int main ()
{
    int i , j ;
    char a[2][3] = {{'a' , 'b' , 'c'} , {'d' , 'e' , 'f'}} ;
    char b[3][2] ;
    char *p = *b ;
    for (i = 0 ; i < 2 ; i++)
    {
        for (j = 0 ; j < 3 ; j++)
        {
            *(p + 2*j + i) = a[i][j];
        }
    }
    for (i = 0 ; i < 3; i++)
    {
        for (j = 0 ; j < 2 ; j++)
        {
            printf ("%c " , b[i][j]) ;
        }
        printf ("\n") ;
    }
    return 0 ;
}
/*
	
*/
```

This program output is...![113](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\113.PNG)

### Question 20



*****

## String

### String Literals 

Is a sequence of characters enclosed within double quotes **" "**

- **%s** is a placeholder for a strings  

- Double quotes **" "** are important, we can't use single quotes 

- we use splicing **( \ )** when we need to write a large sentence in many lines, but you'll have a spaces between the lines, you can use  double quotes **" "** for every line 

  ```c
  // Error
  printf("%s" , "Fashion is kinda a joke. I don't get too bogged down in the clothes.
         For me, it's one big art project, just a canvas to show that fashion
         should have a brand which has someone behind it who cares about different contexts.
         Social things. Virgil Abloh") ;
  
  // No error
  printf("%s" , "Fashion is kinda a joke. I don't get too bogged down in the clothes.\
  For me, it's one big art project, just a canvas to show that fashion\
  should have a brand which has someone behind it who cares about different contexts.\
  Social things. Virgil Abloh") ;
  
  // No error
  printf("%s" , "Fashion is kinda a joke. I don't get too bogged down in the clothes."
  "For me, it's one big art project, just a canvas to show that fashion"
  "should have a brand which has someone behind it who cares about different contexts."
  "Social things. Virgil Abloh") ;
  ```

### Storing String Leterals

String literals are sorted as array of characters and it' always ended by **\0** (Null Character). it's indicates the end of the string and added by the compiler 

> **\0** character not **0** character, both have different ASCII codes, **\0** has the code 0 while **0** has the code 48 

In C, compiler treats a string liters as a **pointer to the first character**, so if we passing a string to a function, we actually passing the pointer for the first element in the string and it will be end when it reaches the **\0**

So we can declare and initialize a string laterals like that 

```c
char * s = "I am Desouky" ; 
```

Here we passing the address of the first element **I** to the pointer **s**, also we can use all operation on it like any pointer 

![store string](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\store string.png)

- String liters can't be modified, it causes undefined behavior, because string letters are known as string constant, they saved in read only memory, so we can't alter them, but character pointer itself has been allocated read-write memory, so the same pointer can point so some other string litters 
- String laterals not like character constant 
- When we use scanf() function, there's no need to use **&**, therefore we passing address of pointer or array 
- scanf() function doesn't store the white space characters in the string variable, when white space seen by scanf(), it stops and store all element before white space 

###  Declaring and Initializing String Variables

A string variables is a 1D array of characters that is capable of holding a string at a time 

> Always make the array one character longer than the string, if the length of the string is 5 characters long, then we must make extra room for **\0**, if you forget it, it will be unpredictable results when the program is executed 

```c
char s[8] = "Desouky" ;
char arr[8] = {'D' , 'e' , 's' , 'o' , 'u' , 'k' , 'y' , '\0'} ;
// both are equal 
```

- String liters can't be modified, but we can modify a char array 

  ```c
  // Error
  char * s = "Desouky" ; 
  *s = 'A' ;
  
  // No error
  char s[8] = "Desouky" ; 
  s[0] = 'A' ;
  ```

- In short length initializer the compiler will puts **\0** in the empty rooms 

- In long length initializer the compiler will produce a warning message and we got a unpredictable results

- In equal length initializer (no place for **\0**) the compiler will produce a warning message and we got a undefined behavior 

- In omitting length initializer the compiler will set a number of character plus one for **\0**

- If we need to display number of character on the screen we can use **%.ns**, while **n** is the number of character, and if we need to print size of field within which the string will be display, we use **%m.ns**, while **m*** is the number of fields 

  ```c
  char * s = "Abdelrahman Eldesouky" ;
  printf("%.5s" , s) ;	// prints (Abdel)
  printf("%5.5s" , s) ;	// prints (     Abdel)
  ```

### puts ( ) Function 

puts() function declared in **<stdio.h>** library (like printf(), scanf() functions), it used to write strings on the output screen, also it's automatically writes a newline character **\n** after writing the string to the output screen 

```c
#include <stdio.h>
int main ()
{
    char * s = "Abdelrahman Eldesouky" ;
    puts (s) ; 
    puts (s) ; 
}
```

The output of this program is...![133](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\133.PNG)

### gets ( ) Function 

gets() function declared in **<stdio.h>** library (like printf(), scanf() and puts() functions), it used to read an entire line of input, not like scanf(), gets() function can store white spaces as a character

- Both gets(), scanf() functions have no way to detect when the character array is full 

- Both gets(), scanf() functions never check the maximum limit of input character, so they may cause undefined behavior and probably lead the buffer overflow error which eventually causes the program to crash 

- scanf() has the way to set the limit for the number of characters to be stored in the character array by using **%ns**, where **n** is the number of character allowed to store in the character array, but gets() still unsafe, therefore it's not advisable to use gets() function 

  ```c
  char s[10] ; 
  scanf ("%5s" , s) ;
  printf ("%s" , s) ;
  // Input:	Eldesouky
  // output:	Eldes
  ```

### Designing The Input Function using getchar() Function 

As we see, scanf(), gets() functions are risky to use, so we'll design our input function 

We need our input functions has the following attributes:

1.  Read the string even after seeing white space character 
2. Stop reading the string after seeing the newline character
3. Must discard extra character 
4. Returns the number of characters it stored in the character array 

> **getchar( )** functions is used to read one character at time from the user input, it returns an integer equivalent to the ASCII code of the character 

```c
#include <stdio.h>
int input (char str[] , int n)
{
    int IN , i = 0 ;		// local variable (i for count) , (IN for check the input is \n or not)
    while ((IN = getchar()) != '\n')
    {
        if (i < n)			// condition for discard extra character 
        {
            str[i] = IN ; // storing the elements in array 
            i++ ;		 // update the counter 
        }
    }
    str[i] = '\0' ;			// put the null character at the end of the array 
    return i ;			   // return the number of number stored in the array 
}
```

Lets use it...

```c
#include <stdio.h>
int input (char str[] , int n)
{
    int IN , i = 0 ;		// local variable (i for count) , (IN for check the input is \n or not)
    while ((IN = getchar()) != '\n')
    {
        if (i < n)			// condition for discard extra character 
        {
            str[i] = IN ; // storing the elements in array 
            i++ ;		 // update the counter 
        }
    }
    str[i] = '\0' ;			// put the null character at the end of the array 
    return i ;			   // return the number of number stored in the array 
}
int main ()
{
    char s [100] ;
    int n = input (s , 5) ;
    printf ("%d %s" , n , s) ; 
}
```

The output of this program is...![134](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\134.PNG)

### putchar () Function

putchar() function accept an integer argument and returns an integer representing the character written on the screen, putchar() function it put the character on the screen  

```c
// prototype
int putchar (int ) ;
```

Example 

```c
#include <stdio.h>
int main ()
{
    int OUT ;
    for (OUT = 'A'; OUT <= 'Z' ; OUT++)
    {
        putchar(OUT) ;
    }
}
```

The output of this program is...![135](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\135.PNG)

> There's no difference between using **int** or **char** in this function, always it turns into binary in our machines 

### C String Library

**<string.h>** library contains all the required functions for preforming string operation like (copy strings, concatenate strings, select substrings and so on), so if we need to use any of these functions, we must include it in out program 

```c
#include <string.h>
```

Now let as learn more about those functions  

- **strcpy ()** Function (String Copy Function )

  strcpy() function is used to copy a string pointed by source including **\0** to the destination 

  ```c
  // prototype
  char * strcpy (char * destination , const char * source) ;
  // we make the source constant because we don't modifie it
  ```

  Example

  ```c
  #include <stdio.h>
  #include <string.h>
  int main ()
  {
      char a[10] = "Hello" , b[10] ;
      printf ("%s\n" , strcpy (b , a)) ;
      printf ("%s\n" , b) ;
  }
  ```

  The output of this program is...![136](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\136.PNG)

  > - strcpy() returns the pointer to the first character of the copied string 
  > - In the call to **strcpy(b , a)**, there's no way that strcpy() function will check if the string pointed by a will fit in b or not 
  > - If the length of the string pointed by a is greater than the length of the character array b, then it will be an undefined behaver 

- **strncpy ()** Function 

  Like strcpy() function, but here we discard extra character from coping, but strncpy() will leave the destination without terminating **\0**, if the size of the source is equal to or greater than the size of destination it produce undefined behavior, so we must added by ourselves 

  ```c
  // prototype
  char * strncpy (char * destination , const char * source , sizeof(destination)) ;
  ```

  Example

  ```c
  #include <stdio.h>
  #include <string.h>
  int main ()
  {
      char a[6] = "Hello" , b[4] ;
      strncpy (b , a , sizeof(b)) ;
      b[sizeof(b) - 1] = '\0' ;
      printf ("%s\n" , b) ;
  }
  ```

  The output of this program is...![140](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\140.PNG)

- **strlen ()** Function (String Length Function)

  strlen() function is used to detemind the length of the given string 

  ```c
  // prototype
  size_t strlen (const char * source) ;
  ```

  > - **size_t** is an unsigned integer type of at least 16 bits
  > - strlen() doesn't count the NULL character **\0**
  > - It calculates the length of the string not the length of the array

  Example

  ```c
  #include <stdio.h>
  #include <string.h>
  int main ()
  {
      char a[6] = "Hello" ;
      printf ("%d" , strlen (a)) ;	// prints 5
  }
  ```

  ```c
  #include <stdio.h>
  #include <string.h>
  int main ()
  {
      char a[] = "Hello" ;
      printf ("%d" , strlen (a)) ;	// prints 5
  }
  ```

  ```c
  #include <stdio.h>
  #include <string.h>
  int main ()
  {
      char a[100] = "Hello" ;
      printf ("%d" , strlen (a)) ;	// prints 5
  }
  ```

- **strcat ()** Function (String Concatenate Function)

  strcat() function appends the content of string b at the end of the string a, then returns the pointer of the resulting string a 

  ```c
  // prototype
  char * strcat (char * a , const char * b) ;
  ```

  Example 

  ```c
  #include <stdio.h>
  #include <string.h>
  int main ()
  {
      char a[100] , b[100] ;
      strcpy (a , "Welcome to") ;
      strcpy (b , " My Notes") ;
      strcat (a , b) ;
      printf ("%s" , a) ;
  }
  ```

  The output of this program is...![138](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\138.PNG)

  > An undefined behavior can be observed if size of string a isn't long enough to accommodate the additional characters of string b, because we're trying to add more characters than the memory allocated 

- **strncat ()** Function 

  Like strcat() function, but here we discard extra character from appending

  ```c
  // prototype
  char * strcat (char * a , const char * b , sizeof(a) - strlen(a) - 1) ;
  ```

  Example 

  ```c
  #include <stdio.h>
  #include <string.h>
  int main ()
  {
      char a[5] , b[100] ;
      strcpy (a , "He") ;
      strcpy (b , "llo!") ;
      strncat (a , b , sizeof(a) - strlen(a) - 1) ;
      printf ("%s" , a) ;
  }
  ```

  The output of this program is...![141](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\141.PNG)

- **strcmp ()** Function (String Comparison Function)

  ```c
  // prototype
  int strcmp (const char * a , const char * b) ;
  ```

  Returns value:

  1. Less than 0, if a < b 
     - When the first **i** character in a and b are same and (**i + 1**)st character of a is less than that of b
     - When All characters of a match b, but a is shorter than b 
  2. Greater than 0, if a > b
  3. Equal 0. if a == b 

### Array of Strings 

If we need to represent an array of strings, we can use 2D array

```c
char arrstr [][n] ; 
// n represent number of columns (string size)
```

Example 

```c
char fruits [][12] = {"3 Oranges" , "4 Appels" , "2 Pineapple"} ;
```

|  0   |  1   |  2   |  3   |  4   |  5   |  6   |  7   |  8   |  9   |  10  |  11  |
| :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: |
|  3   |      |  O   |  r   |  a   |  n   |  g   |  e   |  s   |  \0  |  \0  |  \0  |
|  4   |      |  A   |  p   |  p   |  e   |  l   |  s   |  \0  |  \0  |  \0  |  \0  |
|  2   |      |  P   |  i   |  n   |  e   |  a   |  p   |  p   |  l   |  e   |  \0  |

This representation waste a lot of memory by adding more \0, so we can use **Array of Pointers**

```c
char *  arrstr [] ; 
```

Example  

```c
char * fruits [] = {"3 Oranges" , "4 Appels" , "2 Pineapple"} ;
```

|       |  0   |  1   |  2   |  3   |  4   |  5   |  6   |  7   |  8   |  9   |
| :---: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: |
| **0** |  3   |      |  O   |  r   |  a   |  n   |  g   |  e   |  s   |  \0  |

|       |  0   |  1   |  2   |  3   |  4   |  5   |  6   |  7   |  8   |
| :---: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: |
| **1** |  4   |      |  A   |  p   |  p   |  e   |  l   |  s   |  \0  |

|       |  0   |  1   |  2   |  3   |  4   |  5   |  6   |  7   |  8   |  9   |  10  |  11  |
| :---: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: |
| **2** |  3   |      |  P   |  i   |  n   |  e   |  a   |  p   |  p   |  l   |  e   |  \0  |



Look at the begging of session 6 in IMT lecture

******

## Userdefind  Data Type 

We used to save number of data type together, why we do that ?

Suppose I have an employee, he has a name, ID, position, salary, bonus and deductions, so I need to save all this information Somewhere, we know each of these data has own data type, we can create Separate variables for each of them

Now I have a problem, if I need to change any of these variable for an employee or reuse it on another employees, we can think about array, arrays can hold amount of data, but they all must be of same type, note that, we have a different data type, therefore arrays not a good solution

So we must to make our data type, that can hold all different data type we need for one object, now let's explain how ? 

### struct 

A structure is a user defined data type that can be used to group elements of different data type into a single type

- **Declaration**

  ```c
  struct 
  {
      char .... ;
      int ..... ;
      float ... ;
      double .. ;
      int ..... ;
      char .... ;
  } object1 , object2 , objectn ;
  ```

  Here we declare a structure data type, and we create number of variables from this structure, all this variable has access to all data type inside the structure, object1 not equal to object2, each of them has own struct 

  If we need to access data type inside of any object we use ( **.** ) operator 

  ```c
  #include <stdio.h> 
  struct 
  {
      char * name ;
  }employee1 , employee2 ;
  int main ()
  {
      employee1.name = "Abdelrahman Eldesouky" ;
      employee2.name = "Ahmed Elsayed" ;
      printf ("employee1 name is: %s\n" , employee1.name) ;
      printf ("employee2 name is: %s\n" , employee2.name) ;
  }
  ```

  The output of this program is...![124](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\124.PNG)

- **Structure Types**

  1. **Global Scope**

     We declare the structure in global scope to be visible in all functions 

  2. **Local Scope**

     We We declare the structure in Local scope to be visible in it function only 

  > Usually we declare the structure in global scope to be available at all functions and no need to redeclare it

  

  ```c
  struct 
  {
      char * name ;
      int age ;
      int salary ;
  } employee1 , employee1 ;
  int manager (void)
  {
      struct 
      {
          char * name ;
          int age ;
          int salary ;
      } manager ;
      ....
      ....
  }
  ```

  3. **Structure Tag**

     We used to name the structure to define new object from it at any function, it's used to identify a particular kind of structure 

     ```c
     struct Structure_Tag
     {
         ....
         ....
     } ;
     ```

     ```c
     struct employee
     {
         char * name ;
         int age ;
         int salary ;
     };
     int manager (void)
     {
         struct employee manager ; 
         ....
         ....
     }
     int main () 
     {
         struct employee employee1 ; 
         struct employee employee2 ; 
         ....
         ....
     }
     ```

     Also we can create a variable from the structure, even if we use a structure tag, but the actual use of structure tag like we say above 

     ```c
     struct employee
     {
         char * name ;
         int age ;
         int salary ;
     } employee1 ;
     ```

  4. **typedef**

     We can use **typedef** to declare a structure data type , as we know, we use it to create a new name for any data type in C, it gives the user the freedom to create their own types

     ```c
     typedef old_data_type new_data_type ;
     ```

     ```c
     typedef struct Structure_Tag_is_optional
     {
         // your data type
     } new_name_for_struct_data_type ;
     ```
```
     
     ```c
     typedef struct
     {
         char * name ;
         int age ;
         int salary ;
     } employee ;
     int manager (void)
     {
         employee manager ; 
         ....
         ....
     }
     int main () 
     {
         employee employee1 ; 
         employee employee2 ; 
         ....
         ....
     }
```

     Here we can create a new variables from structure using the new name for struct data type, no need to use **Structure_Tag** or **struct** keyword to create a new object from a structure 

- **Initializing & Accessing the Structure Members**

  ```c
  // Not Allowed 
  struct num
  {
      int p = 10 ;
      int q = 20 ;
  } ;
  // Allowed 
  struct num
  {
      int p = 10 ;
      int q = 20 ;
  } ;
  int main ()
  {
      struct num num1 = {10 , 20} ;
  }
  ```

  ```c
  struct employee
  {
      char * name ;
      int age ;
      int salary ;
  };
  int manager (void)
  {
      struct employee manager = {"Amr" , 45 , 15000} ; 
      ....
      ....
  }
  int main () 
  {
      struct employee employee1 = {"Ahmed" , 25 , 5000} ; 
      struct employee employee2 = {"Waleed" , 32 , 10000} ;
      ....
      ....
  }
  ```

  We say before, if we need to access data type inside of any object we use ( **.** ) operator 

  ```c
  struct employee
  {
      char * name ;
      int age ;
      int salary ;
  };
  int manager (void)
  {
      struct employee manager ;
      manager.name = "Amr" ;
      manager.age = 45 ;
      manager.salary = 15000 ;
      ....
      ....
  }
  int main () 
  {
      struct employee employee1 ; 
      empolyee1.name = "Ahmed" ;
      empolyee1.age = 25 ;
      empolyee1.salary = 5000 ;
      ....
      ....
  }
  ```

  > **Designated Initialization**
  >
  > Allows structure members to be initialized in any order
  >
  > ```c
  > struct employee
  > {
  >     char * name ;
  >     int age ;
  >     int salary ;
  > };
  > int main ()
  > {
  >     struct employee manager = {.age = 50 , .name = "Amr" , .salary = 15000} ;
  >     printf ("%s %d %d" , manager.name , manager.age , manager.salary) ; // prints Amr 50 15000
  > }
  > ```

- **Array of Structure**

  Instead of declaring multiple variables, we can declare an array of structure in which each element of the array will represent a structure variable 

  ```c
  struct object arr[size] ;
  ```

  Example

  ```c
  #include <stdio.h>
  typedef struct
  {
      int ID ;
  	int Math ;
  	int Language ;
  	int Physics ;
  	int Chemistry ;
  }Students_Grades ;
  
  int main()
  {
      int i , id ;
      Students_Grades arr[10] ;
      for (i = 0 ; i < 10 ; i++)
      {
          arr[i].ID = i + 1 ;
          arr[i].Math = 100 - i * 5 ;
          arr[i].Language = 100 - i * 4 ;
          arr[i].Physics = 100 - i *3 ;
          arr[i].Chemistry = 100 - i * 2 ;
      }
      printf ("Enter Your ID: ") ;
      scanf ("%d" , &id) ;
      if (id > 10 || id == 0)
      {
          printf ("Your ID is not exist") ;
      }
      else
      {
          printf("Math grade = %d\n" , arr[id-1].Math) ;
          printf("Math grade = %d\n" , arr[id-1].Language) ;
          printf("Math grade = %d\n" , arr[id-1].Physics) ;
          printf("Math grade = %d\n" , arr[id-1].Chemistry) ;
      }
  }
  ```

  The output of this program is...![125](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\125.PNG)![126](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\126.PNG)

- **Pointer to Structure Variable**

  ```c
  struct employee
  {
      char * name ;
      int age ;
      int salary ;
  };
  int main ()
  {
      struct employee manager = {.age = 50 , .name = "Amr" , .salary = 15000} ;
      struct employee * ptr = &manager ; // ptr is a pointer to some variables of type struct 
  }
  ```

  If we need to access the variable inside the structure we can use (**.**) operator or arrow (**->**) operator 

  ```c
  #include <stdio.h>
  struct employee
  {
      char * name ;
      int age ;
      int salary ;
  };
  int main ()
  {
      struct employee manager = {.age = 50 , .name = "Amr" , .salary = 15000} ;
      struct employee * ptr = &manager ; // ptr is a pointer to some variables of type struct
  
      printf ("%s %d %d" , (*ptr).name , (*ptr).age , (*ptr).salary) ;    // prints Amr 50 15000
      printf ("%s %d %d" , ptr->name , ptr->age , ptr->salary) ;          // prints Amr 50 15000
  }
  ```

- **Size of Structure**

  Here there's some misunderstanding, let's see example1

  ```c
  struct 
  {
      char a ;		// 1 byte
      char b ;		// 1 byte
      int c ;			// 4 bytes
  }
  // size = 8 bytes
  ```

  For a while, we can say the size of structure is 6 bytes (1 + 1 + 4), but this wrong it will be 8 bytes, because of structure padding, but if we use structure packing, the size of structure will be 6 bytes, so let's talk about them 

  1. **Structure Padding**

     processor doesn't read 1 byte at a time from memory, it reads 1 word at a time, if we have 32-bits processor, then it means it can access 4 bytes at a time, which means word size is 4 bytes , if we have 64-bits processor, then it means it can access 8 bytes at a time, which means word size is 8 bytes 

     Let's see example2

     ```c
     struct
     {
         char a ;		// 1 byte
         char b ;		// 1 byte
         char c ;		// 1 byte
         char d ;		// 1 byte
         int e ;			// 4 bytes
     } ;
     // size = 8 bytes
     ```

     Confusing right ? 

     So let's explain it, in example1, the memory partition was like that 

     ![pandding](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\pandding.png)

     The compiler reserved 1 byte for char a , 1 byte for cha b and 4 bytes for int c, but this representation are wastage of CPU cycles, because int c need two CPU cycle to access it and we can access it by one CPU cycle, so the concept of padding come because of that, we can save number of cycles by using this concept

     ![pandding2](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\pandding2.png)

     Empty room will be created because the concept of padding, and variable c will be access in one cycle, so in example1, size = 1 byte for char a + 1 byte for car b + 2 bytes for Empty room + 4 bytes for int c 

     In example2, he memory partition was like that 

     ![pandding3](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\pandding3.png)

     Note the difference between this example and the previous one 

     > If we use padding representation, we should arrange the items in descending or ascending order to save the wastage of memory

     Now think about this example3

     ```c
     struct 
     {
         char a ;		// 1 byte
         int c ;			// 4 bytes
         char b ;		// 1 byte
     }
     // size = 12 bytes..why?
     ```

  2. **Structure Packing**

     Because of structure padding, size of the structure becomes more than the size of the actual structure, due to this some memory will get wasted, because the creation of empty rooms to save CPU cycle

     We can avoid the wastage of memory by using **#pragma** directive, it's a special purpose directive used to turn on or off certain features 

     ```c
     #pragma pack (1)
     struct 
     {
         char a ;		// 1 byte
         int c ;			// 4 bytes
         char b ;		// 1 byte
     }
     // size = 6 bytes
     ```

     Here we makes the memory partition like that 

     ![packing1](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\packing1.png)

     It makes the memory representation as bytes not words, this representation wasted the CPU cycle, but saved the wastage of memory

  > If you want to save the memory, use structure packing, if you want to save CPU cycle, use structure padding, you won't win everything
  
- **Bit Fields**

  

### union 

Unions it has the same properties , operations and parameters as structures, but unlike structures, union members share same memory location

```c
union Union_Tag
{
    char .... ;
    int ..... ;
    float ... ;
    double .. ;
} obj1 , obj2 ;
```

So let's see what's the difference between unions and structures 

```c
struct s 
{
    int a ;
    char b ;
}
// a address is 1000
// b address is 2000

union u
{
    int a ;
    char b ;
}
// a address is 1000
// b address is 1000
```

![C Union | Itsbeyondsimple](https://www.itsbeyondsimple.com/wp-content/uploads/2017/10/word-image-37.png)

As we see in union, members will share the same location, so if we make changes in one member, then it'll reflected to other member as well 

```c
#include <stdio.h>
union abc
{
    int a ;
    char b ;
} var ;
int main ()
{
    var.a = 65 ;
    printf("a = %d\n" , var.a) ;
    printf("b = %c\n" , var.b) ;
}
/*
	a , b shared the same location
	assigned a to 65 and saved in memory
	now b also have the value equal 65 in it memory 
	65 is an integer, 65 as ASCII is 'A'
*/
```

The output of this program is...![132](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\132.PNG)

Size of the union is taken according to the size of the largest member of the union 

```c
union
{
    char .... ;
    int ..... ;
    double .. ;
} ;
```

![union size](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\union size.png)

> This sizes depends on your machine or compiler you use

- Applications 

  1. A store sells two kind of items (books , shirts)

     Books have: Title, Author, Pages no., **price**

     Shirts have: Color, Size, Design, **price**

     We can create structure have all these information like that 

     ```c
     struct store
     {
         double price ;		// 8 bytes 
         char * title ;		// 8 bytes
         char * author ;		// 8 bytes
         int * pages ;	    // 4 bytes
         int color ;		    // 4 bytes
         int size ;		    // 4 bytes
         char * design ;		// 8 bytes
     } ;
     // 44 bytes
     ```

     Here if we need to create object for a new book we have un useful data type for shirts, also if we create object for a new shirt we have un useful data type for books, this a wastage of memory 

     If we use unions we'll save a lot of memory

     ```c
     struct store
     {
         double price ;			// 8 bytes
         union
         {
             struct			   // 20 bytes 
             {
                 char * title ;
                 char * author ;			
                 int * pages ;
             } book ;
             struct			// 16 bytes
             {
                 int color ;
                 int size ;
                 char * design ;
             } shirt ;
         } item ;	// 20 bytes
     } ;
     // 28 bytes
     ```

  2. Array with different type 

     We can create an array with different types using array of unions 

     ```c
     typedef union
     {
         int a ;
         double b ;
         char c ;
     } diff_data ;
     int main ()
     {
         data arr[10] ; 
         arr[0].a = 10 ; 
         arr[1].b = 5.644 ;
         arr[2].c = 'A' ;
         arr[3].b = 3.14 ;
         arr[4].a = 100 ;
         // and so on 
     }
     ```

     If we representing this formula using structures it will be waste of memory

### enum

An enumerated type is used to assign names to integral constant, because names are easier to handle in program 

```c
enum Enum_Tag
{
    enum_name1 ,
    enum_name2 ,
} ;
```

If we don't assign values to enum names, then automatically compiler will assign values to them, starting from 0

```c
#include <stdio.h>
enum boolean
{
    False ,
    True ,
} ;
int main ()
{
    printf ("%d\n" , False ) ;
    printf ("%d" , True ) ;
}
```

The output of this program is...![127](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\127.PNG)

If we assign values to enum name and left some enum names without assigning, then automatically compiler will assign values to the rest of them, starting from last assignation, in different word we can say, **we can assign values in any order, all unassigned names will get value as value of previous name + 1**

```c
#include <stdio.h>
enum nmu
{
    a = 5 ,
    b ,
    c ,
    d = 2 ,
    e = 7 ,
    f ,
    g = 0 ,
    h ,
    i ,
    j = 10 ,
} ;
int main ()
{
    printf ("%d %d %d %d %d %d %d %d %d %d" , a , b , c ,d , e , f , g , h , i , j) ;
}
```

The output of this program is...![128](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\128.PNG)

We know we can use **#define** to assign an integral constant, so why do we need enum? 

1. Enums can be declared in the local scope 

   ```c
   #include <stdio.h>
   int main ()
   {
       enum boolean
       {
           False ,
           True ,
       } ;
       printf ("%d\n" , False ) ;
       printf ("%d" , True ) ;
   }
   ```

   Here we can't use enum outside main() function, but #define declare in global scope to be visible in all functions

2. Enum names are automatically initialized by the compiler 

   ```c
   #include <stdio.h>
   int main ()
   {
       enum boolean
       {
           False ,
           True ,
       } ;
       int var = False ;
       printf ("%d" , var) ;	// prints 0
   }
   ```

- Two or more name can have same values 

  ```c
  #include <stdio.h>
  int main ()
  {
      enum point
      {
          x = 0 ,
          y = 0 ,
          z = 0 ,
      } ;
      printf ("(%d , %d , %d)" , x , y , z) ;		// prints (0 , 0 , 0)
  }
  ```

- Only integral constant are allowed 

  ```c
  #include <stdio.h>
  int main ()
  {
      enum point
      {
          x = 0 ,
           y = 0.5 ,
          z = 0 ,
      } ;
      printf ("(%d , %f , %d)" , x , y , z) ;
  }
  ```

  Error message...![129](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\129.PNG)

- All enum constant must be unique in their scope

  ```c
  #include <stdio.h>
  int main ()
  {
      enum point1
      {
          x = 0 ,
          y = 0 ,
          z = 0 ,
      } ;
      enum point2
      {
          x = 2 ,
          p = 2 ,
          q = 2 ,
      } ;
      printf ("%d %d %d %d %d" , x , y , z , p , q) ;
  }
  ```

  Error message...![130](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\130.PNG)

> Redeclaration of name in the same scope not allowed 

******

## C Preprocessor Directives

### #include 



### #define

We used to defined a constant values or use it like macro

```c
//#define NAME value
#include <stdio.h>
#define PI 3.14159
int main ()
{
    printf ("%.5f\n", PI) ;
    return 0 ;
}
```

The output of this program is ...![24](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\24.PNG)

>  Job of preprocessor (not compiler) to replace NAME with value
>
>  **NAME is called as *macro* too**

- Don't add semicolon at the end of #define syntax

- Don't re-use #define name to declare a variable (compilation error)

- Whatever inside double quotes **" "** won't get replaced 

  ```c
  #include <stdio.h>
  #define PI 3.14159
  int main ()
  {
      printf ("PI = %.5f\n", PI) ;
      return 0 ;
  }
  ```

  The output of this program is ...![25](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\25.PNG)

- We can use macros as functions 

  ```c
  #include <stdio.h>
  #define add(x, y) x + y
  int main ()
  {
      printf ("x + y = %d\n", add(4, 3)) ;
      return 0 ;
  }
  ```

  The output of this program is ...![26](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\26.PNG)

- We can write multiple line using \ 

  ```c
  #include <stdio.h>
  #define greater(x, y)   if (x > y) \
                                              printf ("%d is greater than %d", x , y) ; \
                                          else \
                                              printf ("%d is less than %d", x , y) ;
  int main ()
  {
      greater(5, 6) ;
      return 0 ;
  }
  ```

  The output of this program is ...![27](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\27.PNG)

- Frist expansion then evaluation 

  ```c
  #include <stdio.h>
  #define add(x, y) x + y
  int main ()
  {
      printf ("result of expression: a * b + c is: %d\n", 5 * add(4, 3)) ;
      // we expect the result = 5 * 7 = 30 
      // but the result = 5 * 4 + 3 = 23
      return 0 ;
  }
  ```

  The output of this program is ...![28](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\28.PNG)

- Some predefined macros like **____DATE____ && ____TIME____** can print current date and time 

### #undef

We used to undefined the macro we already define it

```c
#include <stdio.h>
#define X	10
#undef X
#define X	20
int main ()
{
    printf ("X = %d\n", X) ;
    return 0 ;
}
```

The output of this program is ...![144](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\144.PNG)

### #error

The #error directive causes preprocessing to stop at the location where the directive is encountered, information following the #error directive is output as a message prior to stopping preprocessing

```c
#error	ERROR_MESSAGE
```

Message to output prior to stopping preprocessing

### #warning

the #warning directive is similar to an #error directive, but does not result in the cancellation of preprocessing, information following the #warning directive is output as a message prior to preprocessing continuing

```c
#warning	WARNING_MESSAGE
```

The message to output prior to continuing preprocessing

### Stringize operator (#)

We use stringize operator in C to convert a token to string, it transforms the macro parameter to string, it causes the macro parameter to enclose in double quoted string, the C preprocessor expands PRINT(Eldesouky) to "Eldesouky"

```c
#include <stdio.h>
#define PRINT(msg)	#msg
int main ()
{
    printf (PRINT(ELDESOUKY)) ;
    return 0 ;
}
```

The output of this program is ...![145](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\145.PNG)

### Token-pasting operator (##)

Allows tokens used as actual arguments to be concatenated to form other tokens, it's often useful to merge two tokens into one while expanding macros, this's called token pasting or token concatenation
The ‘##’ pre-processing operator performs token pasting, when a macro is expanded, the two tokens on either side of each ‘##’ operator are combined into a single token, which then replaces the ‘##’ and the two original tokens in the macro expansion

```c
#include <stdio.h>
#define WITH(a , b)	a##b
int main ()
{
    int ab = 50 ; 
    printf ("%d" , WITH(a , b)) ;
    return 0 ;
}
```

The output of this program is ...![146](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\146.PNG)

### defined() Operator

The preprocessor defined operator is used in constant expressions to determine if an identifier is defined using #define, if the specified identifier is defined, the value is true (non-zero), if the symbol is not defined, the value is false (zero)

```c
#include <stdio.h>

#if !defined (MESSAGE)
   #define MESSAGE "You wish!"
#endif

int main(void) {
   printf("Here is the message: %s\n", MESSAGE);  
   return 0;
}
```

The output of this program is ...

### #pragma

This directive is a special purpose directive and is used to turn on or off some features, this type of directives are compiler-specific, so it's a compiler dependent, let's take some #pragma usage in c:

1. **#pragma startup and #pragma exit**

   These directives helps us to specify the functions that are needed to run before program startup (before the control passes to main()) and just before program exit (just before the control returns from main())

   ```c
   #include<stdio.h> 
   void func1(void); 
   void func2(void); 
   #pragma startup func1 
   #pragma exit func2 		
   int main() 
   { 
   	printf("Inside main()\n"); 	
   	return 0; 
   }
   void func1(void) 
   { 
   	printf("Inside func1()\n"); 
   } 
   void func2(void) 
   { 
   	printf("Inside func2()\n");	 
   } 
   ```

   ```pseudocode
   output: 
   Inside func1()
   Inside main()
   Inside func2()
   ```

   > this code wont run in GCC compiler, output on it is just **Inside main()**, because GCC not support them, we can do this by another code in GCC 
   >
   > ```c
   > #include<stdio.h> 
   > void func1(void); 
   > void func2(void); 
   > void __attribute__((constructor)) func1(); 
   > void __attribute__((destructor)) func2(); 	
   > int main() 
   > { 
   > 	printf("Inside main()\n"); 	
   > 	return 0; 
   > } 
   > void func1(void) 
   > { 
   > 	printf("Inside func1()\n"); 
   > } 	
   > void func2(void) 
   > { 
   > 	printf("Inside func2()\n"); 
   > } 
   > ```
   >
   > ```pseudocode
   > output: 
   > Inside func1()
   > Inside main()
   > Inside func2()
   > ```

2. **#pragma warn Directive**

   This directive is used to hide the warning messages which are displayed during compilation, this may be useful for us when we have a large program and we want to solve all the errors before looking on warnings then by using it we can focus on errors by hiding all warnings, we can again let the warnings be visible by making slight changes in syntax

   ```c
   #pragma warn +xxx (To show the warning)
   #pragma warn -xxx (To hide the warning)
   #pragma warn .xxx (To toggle between hide and show)
   ```

   > We can hide the warnings as shown below:
   >
   > - **#pragma warn -rvl:** This directive hides those warning which are raised when a function which is supposed to return a value does not return a value
   > - **#pragma warn -par:** This directive hides those warning which are raised when a function does not uses the parameters passed to it
   > - **#pragma warn -rch:** This directive hides those warning which are raised when a code is unreachable. For example: any code written after the return statement in a function is unreachable

3. **#pragma GCC poison**

   This directive is supported by the GCC compiler and is used to remove an identifier completely from the program, we use it if we want to block an identifier

   ```c
   #include<stdio.h> 
   #pragma GCC poison printf 
   int main() 
   { 
   	int a=10; 
   	if(a==10) 
   	{ 
   		printf("GEEKSFORGEEKS"); 
   	} 
   	else
   		printf("bye"); 
   	return 0; 
   } 
   ```

   Error message...![147](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\147.PNG)

4. **#pragma GCC dependency**

   The #pragma GCC dependency allows you to check the relative dates of the current file and another file, if the other file is more recent than the current file, a warning is issued, this is useful if the current file is derived from the other file, and should be regenerated

   ```c
   #pragma GCC dependency "parse.y"
   #pragma GCC dependency "/usr/include/time.h" rerun fixincludes
   ```

5. **#pragma GCC system_header**
   This pragma takes no arguments, it causes the rest of the code in the current file to be treated as if it came from a system header

6. **#pragma once**
   The #pragma once directive has a very simple concept, the header file containing this directive is included only once even if the programmer includes it multiple times during a compilation, this directive works similar to the #include guard idiom, use of #pragma once saves the program from multiple inclusion optimisation

   ```c
   #pragma once
   ```

### Conditional Directive 

| Directive |                   Usage                   |
| :-------: | :---------------------------------------: |
|   ifdef   |   Returns true if this macro is defined   |
|  ifndef   | Returns true if this macro is not defined |
|    if     | Tests if a compile time condition is true |
|   else    |          The alternative for #if          |
|   elif    |      \#else and #if in one statement      |
|   endif   |       Ends preprocessor conditional       |

Examples 

```c
#ifndef MESSAGE
   #define MESSAGE "You wish!"
#endif
// It tells the C preprocessor to define MESSAGE only if MESSAGE isn't already defined
```

```c
#ifdef DEBUG
   /* Your debugging statements here */
#endif
// It tells the C preprocessor to process the statements enclosed if DEBUG is defined
/*
	This is useful if you pass the -DDEBUG flag to the gcc compiler at the time of compilation
    This will define DEBUG, so you can turn debugging on and off on the fly during compilation
*/
```

******

## Questions Set 6

### Question 1

What's the output of the following C program ?

```c
#include <stdio.h>
struct point
{
    int x , y , z ;
} ;
int main ()
{
    struct point p1 = {.y = 0 , .z = 1 , .x = 2} ;
    printf ("%d %d %d" , p1.x , p1.y , p1.z) ;
}
```

**a) 2 0 1**

b) 2 1 0

c) 0 1 2

d) Compiler error

### Question 2

What's the output of the following C program ?

```c
#include <stdio.h>
struct Ournode
{
    char x , y , z ;
} ;
int main ()
{
    struct Ournode p = {'1' , '0' , 'a' + 2} ;
    struct Ournode *q = &p ;
    printf ("%c %c" , *((char *) q+1) , *((char *) q+2) ) ;
}
```

a) 0	a+2

**b) 0	c**

c) '0'	'c'

d) '0'	'a+2'

> If we need to access the element like above, we must use typecasting, because q points to the whole structure 

### Question 3

The following C declaration for s is: 

```c
struct node 
{
    int i ;
    float j ;
} ;
struct node *s[10] ;
```

**a) An array, each element of which is a pointer to a structure of type node**

b) A structure of 2 fields, each field being a pointer to an array of 10 elements

c) A structure of 3 fields: an integer, a float, and an array of 10 elements 

d) An array, each element of which is a structure of type node 

> We know that, Precedence of brackets has a higher level from pointers, so this an array not a structure, also this not a normal array because of asterisk (*****) operator

### Question 4

Calculating the area of rectangle using structures

The following structure are designed to store information about objects on a graphics screen

```c
struct point 
{
    int x , y ;
}
struct recangle 
{
    struct point upper_left ;
    struct point lower_left ;
}
```

Write a function that accepts rectangle structure **r** as an argument and computes the area of **r**

```c
#include <stdio.h>
#include <stdlib.h>
struct point
{
    int x , y ;
} ;
struct rectangle
{
    struct point upper_left ;
    struct point lower_right ;
} ;
int area (struct rectangle r)
{
    int length = r.lower_right.x - r.upper_left.x ;
    int width = r.upper_left.y - r.lower_right.y ;
    return  length * width ;
} ;
int main ()
{
    struct rectangle r ;
    printf ("Enter the upper left point: ") ;
    scanf ("%d %d" , &r.upper_left.x , &r.upper_left.y) ;
    printf ("Enter the lower right point: ") ;
    scanf ("%d %d" , &r.lower_right.x , &r.lower_right.y) ;
    printf("Area of rectangle is: %d" , abs(area(r))) ;
}
```

The output of this program is ...![131](E:\Neso Academy\C & Data Str. Neso Academy\Notes\Pic\131.PNG)

### Question 5

Consider the following c declaration 

```c
struct 
{
    short s[5] ;
    union
    {
        float y ;
        long z ;
    } u ;
} t ;
```

Assuming that objects of the type short, float and long have sizes 2 bytes , 4 bytes and 8 bytes respectively, the memory requirement for variable t is ? 

Ignoring alignment considerations (padding representation)

a) 22 bytes 

b) 14 bytes 

**c) 18 bytes**

d) 10 bytes

### Question 6

Identify which of the following calls don't work properly and give the reason for the same 

- [ ] printf ("%c" , '\n') ;

- [x] printf ("%c" , "\n") ;

  Because the format specifier for the character not string  

- [ ] putchar ('\n') ;

- [x] putchar ("\n") ;

  Because the function expect a character not string  

- [x] puts ('\n') ;

  Because the function expect a string not character

- [ ] puts ("\n") ;

- [x] printf ("%s" , '\n') ;

  Because the format specifier for the string not character 

- [ ] printf ("%s" , '\n') ;

### Question 7  

What's the output of the following C program ?

```c
char p[20] ; 
char * s = "string" ; 
int length = strlen(s) ; 
int i ; 
for (i = 0 ; i < length ; i++) 
{
    p[i] = s[lenght - i] ;
}
printf ("%s" , p) ; 
/*
	length = 6 
	s[length - 0] = s[6] = \0 (NULL character)
*/
```

a) gnirts

b) string 

**c) No output**

d) gnirt

### Question 8

What's the output of the following C program ?

```c
#include<stdio.h>
#include <string.h>
int main()
{
    char c[] = "ABDELRAHMAN" ;
    char * p = c ;
    printf ("%s" , p + p[3] - p[1]) ;
}
/*
	p = 1000 (some address for first element in the array)
	p[3] = 'E'
	p[1] = 'B'
	p + p[3] - p[1] = 1000 + 'O' - 'E' = 1000 + 69 - 66 = 1003
Output:
	ELRAHMAN
*/
```

### Question 9

What's the output of the following C program ?

```c
void func (char * a)	// input "ABCD EFGH"
{
    if (* a && * a != ' ')
    {
        func (a + 1) ;
        putchar (* a) ;
    }
}
```

a) ABCD EFGH

b) ABCD

**c) DCBA**

d) HGFE DCBA

### Question 10

What's the output of the following C program ?

```c
#include<stdio.h>
#include <string.h>
int main()
{
    char c[] = "ABDELRAHMAN" ;
    char * p = c ;
    printf ("%d" , (int)strlen(c + 2[p] - 6[p] - 1)) ;
}
/*
	2[p] = *(2 + p) , 6[p] = *(6 + p)
Now
	c + *(2 + p) - *(6 + p) - 1
Assuming c[0] = 1000
	1000 + *(1002) - *(1006) - 1 = 1000 + 'D' - 'A' - 1 = 1000 + 68 - 65 - 1 = 1002
Output
	9 (count from 'D')
*/
```

******

## Refrence 

1. Neso Academy 
2. Geeks4Geeks
3. tutorialspoint
4. C how to program 3rd edition 
5. codeforwin
6. techonthenet
