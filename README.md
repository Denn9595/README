# core-code-from-scratch-readme

## Week 1

### Day 1
**Interpreted and compiled programming languages**
1. The advantage of these programming languages is that they are easier to debug and make changes to them, without having to remake the whole code written for a certain app.
2. Compiled languages tend to be faster and allow the programmer to decide how the hardware will interact with the user. They are faster, but usually need an extra program to run in a variety of devices. For example, a program/app could be built in a compiled language but will need to be developed for Mac, Windows or Linux.

**Is Java compiled or interpreted, or both?**

Java program is first compiled into bytecode which JRE can understand. ByteCode is then interpreted by the JVM making it as interpreted language. Note that Java implementations typically use a two-step compilation process. Java source code is compiled down to bytecode by the Java compiler. The bytecode is executed by a Java Virtual Machine (JVM). Modern JVMs use a technique called Just-in-Time (JIT) compilation to compile the bytecode to native instructions understood by hardware CPU on the fly at runtime.

**Pseudocode Currency Converter exercise**
```
START

USD Amount <-- GET

BTCprice <-- GET FROM(https://www.coindesk.com/price/bitcoin/)

Total <-- USD Amount / BTCprice

PRINT Total

END
```

### Day 2

**Your date of birth in the matrix?**

My DOB is 1995, which in binary is 1111100101.

**MIPS Excercises**

**1. Create a program that adds any two given numbers provided by the user**
```
  .data
	      number1: .asciiz "\nEnter Number 1 : "
	      number2: .asciiz "\nEnter Number 2: "
	      number3: .asciiz "\nResult: "
  .text
	      main:
              li $v0, 4
              la $a0, number1
              syscall

              li $v0, 5
              syscall

              move $t0, $v0

              li $v0, 4
              la $a0, number2
              syscall

              li $v0, 5
              syscall

              move $t1, $v0

              li $v0, 1
              move $a0, $t0
              syscall
              
              add $t2, $t1, $t0
              syscall
              
              li $v0, 4
              la $a0 number3
              syscall
              
              li $v0, 1
              move $a0, $t2
              syscall
```       

**2. Create a program that displays your name**
```
.data
	      Name: .asciiz "\nDennis Monroy"
  .text
	      main:
              li $v0, 4
              la $a0, Name
              syscall
```


### Day 3

**1. Print Special Numbers**
```
var str = '';

for (var i = 2; i < 101; i++) {
  str = str + i;
}

console.log(str);
```

**2. Bad Code 1**

```
var cond = false;

if (cond == true) {
    console.log('The cond variable is true');
} else {
    console.log('The cond variable is false');
}
```

**3. Bad Code 2**


```
var n = 100;

if (n == 100) {
    console.log('This is a special number!');
}
else if (n < 1000 && n % 10 == 0) {
    console.log('This is almost special');
} 
else {
    console.log('Just a regular number');
}
```
