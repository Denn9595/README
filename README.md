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

Week 2

Tuesday

1. Multiply exercise
  
  function multiply(a, b){
 return a * b
}

2.ASCII Total exercise


function uniTotal(str) {
  let count = 0;
  for (let i = 0; i < str.length; i++) {
    count += str.charCodeAt(i);
  }
  return count;
}

3.Char From ASCII Value exercise

function getChar(c){
return String.fromCharCode(c);
}

4.Binary Addition exercise

function addBinary(a,b) {
let sum = a + b;
  return sum.toString(2);
}

5.Student's Final Grade exercise

function finalGrade(exam, projects) {
  let total = 0;
  if (exam > 90 || projects > 10) {
  total = 100;
} else if (exam > 75 && projects >= 5) {
  total = 90;
} else if (exam > 50 && projects >= 2) {
  total = 75;
} else {
  total = 0;
}
  return total;
}


Wednesday 20/04
1. Holiday VIII - Duty Free exercise
function dutyFree(normPrice, discount, hol){
let descuentoTotal = normPrice*(discount/100);
  return Math.floor (hol/descuentoTotal);
}


2. Twice As Old exercise
function twiceAsOld(dadYearsOld, sonYearsOld) { n
  let dobAgeSon = 2*sonYearsOld;
  return Math.abs(dadYearsOld - dobAgeSon);
}


3. Valid Spacing Exercise
function validSpacing(s) {
  if (s.length === 0) return true;
  if (s[0] === ' ' || s[s.length - 1] === ' ') return false;
  let aSpaces0 = s.split(' ');
  for (let i = 0, length = aSpaces0.length; i < length; i++) {
    if (aSpaces0[i] === '') return false;
  }
  return true;
}


4. Fake Binary
function fakeBin(x){
let digits = '';
    for (let i = 0; i < x.length; i++) {
      if (parseInt(x[i]) < 5){
        digits = digits + '0';
      } else {
        digits = digits + '1';
      }
    }
  return digits;
}



Thursday  

1. Remove All Exclamation Marks From The End Of Sentence
function remove(inputString) {
let result = inputString;
while (result[result.length - 1] === "!"){
  result = result.slice(0,-1);
}
  return result;
}



2. Vowel Remover
function shortcut(mytext) {
  return mytext.replace(/[aeiou]/g, '');
}


3. Rock Paper Scissors!
const rps = (user1, user2) => {
  let result = "";
  if (user1 === user2) {
    result = "Draw!";
  }
  else if (user1 === "paper" && user2 === "rock") {
    result = "Player 1 won!";
  }
  else if (user1 === "scissors" && user2 === "paper") {
    result = "Player 1 won!";
  }
  else if (user1 === "rock" && user2 === "scissors") {
    result = "Player 1 won!";
  }
  else if (user1 === "paper" && user2 === "scissors") {
    result = "Player 2 won!";
  }
  else if (user1 === "scissors" && user2 === "rock") {
    result = "Player 2 won!";
  }
  else if (user1 === "rock" && user2 === "paper") {
    result = "Player 2 won!";
  }
  return result
}




4. Persistent Bugger
function persistence(num) {
  let counter = 0;
  let digits = num.toString().split(""); // 39 -> "39" -> ["3", "9"]
  while (digits.length > 1) {
    let results = 1;
    for (let i = 0; i < digits.length; i++){
      results = results * digits[i];
    }
    digits = results.toString().split("");
    counter = counter + 1;
  }
  return counter;
}




Week 3

Monday        


1. Who likes it?
function likes(names) {
  if (names.length == 0) return 'no one likes this';
  if (names.length == 1) return names[0] + ' likes this';
  if (names.length == 2) return names[0] + ' and ' + names[1] + ' like this';
  if (names.length == 3) return names[0] + ', ' + names[1] + ' and ' + names[2] + ' like this';
  return (names[0] +', ' + names[1] + ' and ' + (names.length - 2) + ' others like this');
}



2. Bit Counting
var countBits = function(n) {
   // make an array with the bit result
   const base = (n).toString(2).split('');
   // make a sum with the array and make the index a Number
   const result = base.reduce((sum, num) => sum + Number(num), 0);
   return result;
};



3. Your Order, Please
function order(words){
  return words.split(' ').sort(function(a, b){
      return a.match(/\d/) - b.match(/\d/);
   }).join(' ');
}



Tuesday 1. Simple Pig Latin
function pigIt(str){
  let newArr = [];
  let strArr = str.split(" ")
  strArr.forEach(x => {
    let wordArr = x.split("")
    wordArr.push(wordArr[0], 'ay'), wordArr.shift()
    if (x === "!" || x === "?" || x === "." || x === "," || x === ";"){
      newArr.push(x)
    } else {
      newArr.push(wordArr.join(""))
    }
  })
  return newArr.join(" ")
}



2. Counting Duplicate
function duplicateCount(text) {
  const splitString = text.toLowerCase().split("").sort();
  let results = [];
  for (let i = 0; i < splitString.length; i++) {
    if (splitString[i] === splitString[i + 1]) {
      results.push(splitString[i]);
    }
  }
  const setArray = new Set(results);
  return setArray.size;
}



3. Decode The Morse Code
decodeMorse = function(morseCode){
  morseCode = morseCode.trim();
  let refinedData = morseCode.split('   ');
  let result = [];
  for (let i = 0; i < refinedData.length; i++) {
    let temp = refinedData[i].split(' ');
    for (let j = 0; j < temp.length; j++) {
      if (MORSE_CODE[temp[j]]) {
        result.push(MORSE_CODE[temp[j]]);
      }
    }
    if (i !== refinedData.length - 1) {
    result.push(' ');
    }
  }
  return result.join('');
}



Wednesday
14:06
1. Valid Parentheses exercise
function validParentheses(parens) {
  let openNum = 0;
  for (let i = 0; i < parens.length; i++){
    if (parens[i] == "(") {
      openNum += 1;
    } else {
      openNum -= 1;
    }
    if (openNum < 0){
      return false
    }
  }
  if (openNum === 0){
    return true
  } else {
    return false
  }
}



2. Convert String To Camel Case
function toCamelCase(str){
  let strArray;
  if (str === ""){
    return "";
  }
  if (str.indexOf("-") !== -1){
    strArray = str.split("-")
  } else {
    strArray = str.split("_")
  }
  let ccString = strArray[0];
  for (let i = 0; i < strArray.length; i++){
    ccString += capitalize(strArray[i]);
  }
  return ccString
  }
  let capitalize = (str) => {
    return str[0].toUpperCase() + str.slice(1);
}



3. Unique In Order exercise
var uniqueInOrder=function(iterable){
  let newArr = []
  for (i = 0; i < iterable.length; i++){
    if (iterable[i] != iterable[i+1]){
      newArr.push(iterable[i])
    }
  }
  return newArr
}



Thursday
1. Fold An Array exercise
function foldArray(array, runs) {
  const r = [];
  const c = array.slice();
  while (c.length) r.push(c.pop() + (c.shift() || 0));
  return runs - 1 ? foldArray(r, runs - 1) : r;
}
2. Encrypt This! exercise*
var encryptThis = function(str) {
 if(str === '') {return '';
    }else {
        let s = str.split(' ');
        let x = s.map(element => {
            let a = element.split('');
            a[0] = element.charCodeAt(0);
            [a[1], a[a.length - 1]] = [a[a.length - 1], a[1]];
            return a.join('');});
      return x.join(' ');
    }
}
