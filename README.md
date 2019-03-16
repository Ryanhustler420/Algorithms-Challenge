# Algorithms-Challenge
Programming Problems Solve Using JavasSript 

> Absolute sum minimization

Given a sorted array of integers a, find an integer x from a such that the value of

abs(a[0] - x) + abs(a[1] - x) + ... + abs(a[a.length - 1] - x)
is the smallest possible (here abs denotes the absolute value). If there are several possible answers, output the smallest one.

Example

For a = [2, 4, 7], the output should be absoluteValuesSumMinimization(a) = 4.

For a = [2, 4, 7, 6], the output should be absoluteValuesSumMinimization(a) = 4.

For a = [2, 4, 7, 6, 6], the output should be absoluteValuesSumMinimization(a) = 7.

For a = [2, 4, 7, 6, 6, 8], the output should be absoluteValuesSumMinimization(a) = 7.

Hints

Math.floor()
Input/Output

[time limit] 4000ms (js)
[input] array.integer a
A non-empty array of integers, sorted in ascending order.

Guaranteed constraints:

1 ≤ a.length ≤ 200,

-106 ≤ a[i] ≤ 106.

[output] integer

```typeScript
function absoluteValueSumMinimization(a: number[]): number {
  const isEven = a.length % 2 === 0;
  
  return isEven ? a[a.length /2 -1] : a[Math.floor(a.length / 2)];
}

console.log(absoluteValueSumMinimization([2,4,7]))       //4
console.log(absoluteValueSumMinimization([2,4,7,6]))     //4
console.log(absoluteValueSumMinimization([2,4,7,6,6]))   //7
console.log(absoluteValueSumMinimization([2,4,7,6,6,8])) //7

```

##### Add

1. Write a function that returns the sum of two numbers.
2. Write a function that returns the sum of all numbers regardless of # of params.

**Example**

For param1 = 1 and param2 = 2, the output should be
add(param1, param2) = 3.

**Hints**
-   Arithmetic Operators
-   Rest Operator
-   forEach()

**Input/Output**

- **[time limit] 4000ms (js)**
- **[input] integer param1**

Guaranteed constraints:

-100 ≤ param1 ≤ 1000.

**[input] integer param2**

Guaranteed constraints:
-100 ≤ param2 ≤ 1000.

**[output] integer**

The sum of the two inputs.

```typeScript
function add(number1: number, number2: number){
  return number1 + number2;
}

function add2(...param1: number[]):number {
  let total = 0;
  
  param1.forEach((num) => {
    total += num;  
  });
  
  return total;
}

console.log(add2(1,2,3,4,5));

```
##### Add Border

Given a rectangular matrix of characters, add a border of asterisks(*) to it.

**Example**

For

    picture = ["abc",
           "ded"]
the output should be

    addBorder(picture) = ["*****",
                      "*abc*",
                      "*ded*",
                      "*****"]

**Hints**
-   concat()
-   unshift()
-   push()

**Input/Output**
- **[time limit] 4000ms (js)**
- **[input] array.string picture**

A non-empty array of non-empty equal-length strings.

*Guaranteed constraints:*

1 ≤ picture.length ≤ 5,

1 ≤ picture[i].length ≤ 5.

- **[output] array.string**

The same matrix of characters, framed with a border of asterisks of width 1.

```typeScript
function addBorder(picture: string[]): any {
  const wall = "*".repeat(picture[0].length + 2);
  
  picture.unshift(wall);
  picture.push(wall);
  
  for(let i = 1; i < picture.length - 1; i++) {
    picture[i] = "*".concat(picture[i], "*");  
  }
  
  return picture;    
}

console.log(addBorder(["abc","ded"])); // ["*****","*abc*","*ded*","*****"]

```

##### Add Two Digits

You are given a two-digit integer n. Return the sum of its digits.

**Example**

For n = 29, the output should be
addTwoDigits(n) = 11.

**Hint**
-   split()
-   parseInt()
-   toString()
-   reduce()

**Input/Output**

- **[execution time limit] 4 seconds (js)**
- **[input] integer n**

    A positive two-digit integer.

*Guaranteed constraints:*

10 ≤ n ≤ 99.

- **[output] integer**

    The sum of the first and second digits of the input number.


```typeScript

function addTwoDigits(n: string): number {
 	/* return [...n.toString()].reduce((acc, cur) => {
   		return parseInt(acc) + parseInt(cur);
    });
    */
  	return parseInt(n[0]) + parseInt(n[1]);
}

console.log(addTwoDigits(29)); // 11


```

##### Adjacent Elements Products

Given an array of integers, find the pair of adjacent elements that has the largest product and return that product.

**Example**

For inputArray = [3, 6, -2, -5, 7, 3], the output should be
adjacentElementsProduct(inputArray) = 21.

7 and 3 produce the largest product.

**Hints**
-   None

**Input/Output**

- **[time limit] 4000ms (js)**
- **[input] array.integer inputArray**

An array of integers containing at least two elements.

*Guaranteed constraints:*

2 ≤ inputArray.length ≤ 10,
-1000 ≤ inputArray[i] ≤ 1000.

- **[output] integer**

The largest product of adjacent elements.

```typeScript

function adjacentElementsProduct(inputArray: number[]): number {
  let largestProduct = inputArray[0] * inputArray[1];
  
  for(let i=0; i < inputArray.length -1; i++){
    const product = inputArray[i] * inputArray[i + 1];
    
    largestProduct = largestProduct < product ? product : largestProduct;
  }
  
  return largestProduct;
}

console.log(adjacentElementsProduct([3,6,-2,-5,7,3])); //21

```

##### All Longest Strings

Given an array of strings, return another array containing all of its longest strings.

**Example**

For inputArray = ["aba", "aa", "ad", "vcd", "aba"], the output should be
allLongestStrings(inputArray) = ["aba", "vcd", "aba"].

**Hints**
-   None

**Input/Output**

- **[time limit] 4000ms (js)**
- **[input] array.string inputArray**

A non-empty array.

*Guaranteed constraints:*

1 ≤ inputArray.length ≤ 10,

1 ≤ inputArray[i].length ≤ 10.

- **[output] array.string**

Array of the longest strings, stored in the same order as in the inputArray.

```typeScript
  
  // plain vanilla JavaScript
  const inputArray = ["aba", "aa", "ad", "vcd", "aba"];

/*
  let newArray = [];
  newArray.push(inputArray[0]);

  for( let i = 1; i < inputArray.length; i++) {
    if(newArray.length > 0) {
        if(inputArray[i].length > newArray[newArray.length-1].length){
            newArray = [];
              newArray.push(inputArray[i]);
          }else if(inputArray[i].length === newArray[newArray.length-1].length){
            newArray.push(inputArray[i]);
          }
      }
  }

  console.log(newArray);
*/

  function allLongestStrings(inputArray: string[]): string[] {
      let longestLength = 0;
      const longestWords = [];

      inputArray.forEach((word: string) => {
        longestLength = longestLength < word.length ? word.length : longestLength;
      });

      inputArray.forEach((word: string) => {
        if(word.length === longestLength){
          longestWords.push(word);
        }
      });

      return longestWords;
  }

  console.log(allLongestStrings(inputArray))
```
