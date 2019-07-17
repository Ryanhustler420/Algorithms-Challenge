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

##### Bishop And Pawn

```js

const bishop = 'a1';
const pawn = 'c3';

const board = {
    "a": 1,
    "b": 2,
    "c": 3,
    "d": 4,
    "e": 5,
    "f": 6,
    "g": 7,
    "h": 8,
};

const bishopX = board[bishop[0]];
const bishopY = parseInt(bishop[1]);
const pawnX = board[pawn[0]];
const pawnY = parseInt(pawn[1]);

if(bishopX + bishopY === pawnX + pawnY || bishopX + pawnY === pawnX + bishopY){
    console.log(true);
}

```

##### BoxBlur Algo

```js

function boxBlur(image){
    const res = [];

    for (let y = 0; y < image.length - 2; y++) {
        console.log(image[y])
        const line = [];

        for (let x = 0; x < image[y].length - 2; x++) {

            let sum = 0;
            let count = 0;

            for (let a = y; a < y + 3 ; a++) {
                for (let b = x; b < x + 3; b++) {
                    image[a][b]; /*? */
                    sum += image[a][b];
                    count++;
                    
                }
            }
            line.push(Math.floor(sum/count));
            Math.floor(sum/count); /*? */
        }
        res.push(line);
        
    }
    return res;
}

boxBlur([[1,1,1],[1,7,1],[1,1,1]]); /*? */

```

##### candies

```js

function candies(nChild, nCandy) {
    const candy = Math.floor(nCandy / 3);

    return candy * nChild;
}

console.log(candies(3, 10));


```

##### Case Insensitive Palindrome

```js

const string = 'Aabaa';

const reversed = [...string.toLowerCase()].reverse().join(''); /*? */

if(string.toLowerCase() == reversed) {
    console.log('yup');
}else {
    console.log('nop');
}

```

##### Century From Year


```js

function centuryFromYear(year) {
    const century = (year / 100);
    if(year % 100 === 0) {
        return century;
    }
    return (Math.floor(century) + 1) /*? */
}

console.log(centuryFromYear(1905));
console.log(centuryFromYear(1700));
console.log(centuryFromYear(2019));

````

##### Character Parity

```js
function characterParity(symbol) {
    if(!isNaN(symbol)){
        return (parseInt(symbol) % 2 === 0) ? 'even' : 'odd'; 
    }
    return 'not a digit';
}

console.log(characterParity('2'));



```

##### Chess Board Cell Color

```js

function chessBoardCellColor(cell1, cell2) {
    const board = {
        "A": 1,
        "B": 2,
        "C": 3,
        "D": 4,
        "E": 5,
        "F": 6,
        "G": 7,
        "H": 8
    };

    const total1 = (board[cell1[0]] + parseInt(cell1[1])) % 2;
    const total2 = (board[cell2[0]] + parseInt(cell2[1])) % 2;

    return total1 === total2;
}

(chessBoardCellColor('A1', 'C3')); /*? */
(chessBoardCellColor('A1', 'H3')); /*? */


```

##### Chunky Monkey

```js

function chunkyMonkey(array, size) {
    let newArray = [];
    for (let index = 0; index < array.length - size; index+=size) {
        newArray.push(array.slice(index, size)); /*? */
    }
    newArray.push(array.slice(size)); /*? */
    return newArray;
}

chunkyMonkey(["a","b","c","d"], 2); /*? */
chunkyMonkey([0,1,2,3,4,5], 4); /*? */

```

##### Circle of Numbers

```js
function circleOfNumbers(n, firstnumber) {
    const array = [];
    times = n;
    while(times--){
        array.push(firstnumber++);
    }
    return array[Math.floor(n/2)];
}

circleOfNumbers(10, 2); /*? */
```

##### Company Bot Strategy

```js

function companyBotStrategy(trainingData) {
    let time = 0;
    let correctness = 0;

    trainingData.forEach((data) => {
        if(data[1] === 1) {
            time += data[0];
            correctness += data[1];
        }
    });

    return time / correctness || 0;
}

console.log(companyBotStrategy([[3,1],[6,1],[4,1],[5,1]]));
console.log(companyBotStrategy([[4,1],[4,-1],[0,0],[6,1]]));
console.log(companyBotStrategy([[4,-1],[0,0],[5,-1]]));


```
