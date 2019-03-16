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
