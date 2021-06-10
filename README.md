# js-tricks


Top 20 JavaScript tips and tricks to increase your Speed and Efficiency
#webdev #tutorial #javascript #react
techygeeky profile image Kapil Raghuwanshi🖥
8/06 ・Updated on 10/06 ・6 min read
Convenient and useful techniques to reduce the lines of code and pace up your Dev Work!

In our daily tasks, we get to write functions such as sorting, searching, finding unique values, passing parameters, swapping values etc, so here I present my list of shorthand techniques to write all of them as a Pro!✌🏻

Increase Your Performance

    JavaScript is truly an awesome language💛 to learn and work with. And there can be more than one approach to reach to the same solution for given problem. In this article, we will discuss only the quickest ones.🚀

These approaches will definitely help you in:

    Reducing the number of LOC(lines of code),
    Coding Competitions,
    Hackathons or
    Other time bound tasks.⏱

Most of these JavaScript Hacks uses techniques from ECMAScript6(ES2015) onwards, though the latest version is ECMAScript11(ES2020).

Note: All below tricks have been tested on the Console of Google Chrome.
## 1. Declare and Initialize Arrays

We can initialize array of particular size with default values like "", null or 0. You might have used these for the 1-D array but how about initializing 2-D array/matrix?
```
const array = Array(5).fill(''); 
// Output 
(5) ["", "", "", "", ""]

const matrix = Array(5).fill(0).map(()=>Array(5).fill(0)); 
// Output
(5) [Array(5), Array(5), Array(5), Array(5), Array(5)]
0: (5) [0, 0, 0, 0, 0]
1: (5) [0, 0, 0, 0, 0]
2: (5) [0, 0, 0, 0, 0]
3: (5) [0, 0, 0, 0, 0]
4: (5) [0, 0, 0, 0, 0]
length: 5
```
## 2. Find out the sum, minimum and maximum value

We should make use of reduce method to quickly find basic maths operations.
```
const array  = [5,4,7,8,9,2];

    Sum

array.reduce((a,b) => a+b);
// Output: 35

    Max

array.reduce((a,b) => a>b?a:b);
// Output: 9

    Min

array.reduce((a,b) => a<b?a:b);
// Output: 2
```
## 3. Sorting Array of String, Numbers or Objects

We have inbuilt methods sort() and reverse() for sorting strings but How about numbers or array of objects?
Let's check out sorting hacks for Numbers and Objects in Increasing and Decreasing order as well.

    Sort String Array
```
const stringArr = ["Joe", "Kapil", "Steve", "Musk"]
stringArr.sort();
// Output
(4) ["Joe", "Kapil", "Musk", "Steve"]

stringArr.reverse();
// Output
(4) ["Steve", "Musk", "Kapil", "Joe"]

    Sort Number Array

const array  = [40, 100, 1, 5, 25, 10];
array.sort((a,b) => a-b);
// Output
(6) [1, 5, 10, 25, 40, 100]

array.sort((a,b) => b-a);
// Output
(6) [100, 40, 25, 10, 5, 1]

    Sort Array of Objects

const objectArr = [ 
    { first_name: 'Lazslo', last_name: 'Jamf'     },
    { first_name: 'Pig',    last_name: 'Bodine'   },
    { first_name: 'Pirate', last_name: 'Prentice' }
];
objectArr.sort((a, b) => a.last_name.localeCompare(b.last_name));
// Output
(3) [{…}, {…}, {…}]
0: {first_name: "Pig", last_name: "Bodine"}
1: {first_name: "Lazslo", last_name: "Jamf"}
2: {first_name: "Pirate", last_name: "Prentice"}
length: 3
```
## 4. Ever need to filter falsy values out of an array?

Falsy values like 0, undefined, null, false, "", '' can be omitted easily through below trick
```
const array = [3, 0, 6, 7, '', false];
array.filter(Boolean);
// Output
(3) [3, 6, 7]
```
## 5. Use Logical Operators for various conditions

If you want to reduce nested if..else or switch cases, you can simply play with basic of logical operators AND/OR.
```
function doSomething(arg1){ 
    arg1 = arg1 || 10; 
// set arg1 to 10 as a default if it’s not already set
return arg1;
}

let foo = 10;  
foo === 10 && doSomething(); 
// is the same thing as if (foo == 10) then doSomething();
// Output: 10

foo === 5 || doSomething();
// is the same thing as if (foo != 5) then doSomething();
// Output: 10
```
## 6. Remove Duplicates values

You might have used indexOf() with for loop which return first found index or newer one includes() which returns boolean true/false from the array to find out/remove duplicates. Here's we have 2 quicker approaches.
```
const array  = [5,4,7,8,9,2,7,5];
array.filter((item,idx,arr) => arr.indexOf(item) === idx);
// or
const nonUnique = [...new Set(array)];
// Output: [5, 4, 7, 8, 9, 2]
```
## 7. Create a Counter Object or Map

Most of the time, the requirement to solve problem by creating counter object or map which tracks variables as keys with their frequency/occurrences as values.
```
let string = 'kapilalipak';

const table={}; 
for(let char of string) {
  table[char]=table[char]+1 || 1;
}
// Output
{k: 2, a: 3, p: 2, i: 2, l: 2}

and

const countMap = new Map();
  for (let i = 0; i < string.length; i++) {
    if (countMap.has(string[i])) {
      countMap.set(string[i], countMap.get(string[i]) + 1);
    } else {
      countMap.set(string[i], 1);
    }
  }
// Output
Map(5) {"k" => 2, "a" => 3, "p" => 2, "i" => 2, "l" => 2}
```
## 8. Ternary Operator is cool

You can avoid nested conditional if..elseif..elseif with ternary operators.
```
function Fever(temp) {
    return temp > 97 ? 'Visit Doctor!'
      : temp < 97 ? 'Go Out and Play!!'
      : temp === 97 ? 'Take Some Rest!';
}

// Output
Fever(97): "Take Some Rest!" 
Fever(100): "Visit Doctor!"
```
## 9. Quicker for loops compare to legacy onces
```
    for and for..in gets you index by default, but you can use arr[index].
    for..in accepts non numeric as well so avoid it.
    forEach, for...of gets you element directly.
    forEach can get you index also but for...of can't.
    for and for...of considers holes in array but other 2 do not.
```
## 10. Merge 2 objects

Often we need to merge multiple objects in our daily tasks.
```
const user = { 
 name: 'Kapil Raghuwanshi', 
 gender: 'Male' 
 };
const college = { 
 primary: 'Mani Primary School', 
 secondary: 'Lass Secondary School' 
 };
const skills = { 
 programming: 'Extreme', 
 swimming: 'Average', 
 sleeping: 'Pro' 
 };

const summary = {...user, ...college, ...skills};

// Output 
gender: "Male"
name: "Kapil Raghuwanshi"
primary: "Mani Primary School"
programming: "Extreme"
secondary: "Lass Secondary School"
sleeping: "Pro"
swimming: "Average"
```
## 11. Arrow Functions

An arrow function expression is a compact alternative to a traditional function expression, but is limited and can't be used in all situations. Since they have lexical scope (parental scope) and does not have their own this and arguments hence they refer to the environment in which they are defined.
```
const person = {
name: 'Kapil',
sayName() {
    return this.name;
    }
}
person.sayName();
// Output
"Kapil"

But

const person = {
name: 'Kapil',
sayName : () => {
    return this.name;
    }
}
person.sayName();
// Output
""
```
## 12. Optional Chaining

The optional chaining ?. stops the evaluation if the value before ?. is undefined or null and returns undefined.
```
const user = {
  employee: {
    name: "Kapil"
  }
};
user.employee?.name;
// Output: "Kapil"
user.employ?.name;
// Output: undefined
user.employ.name
// Output: VM21616:1 Uncaught TypeError: Cannot read property 'name' of undefined
```
## 13. Shuffle an Array

Making use of inbuilt Math.random() method.
```
const list = [1, 2, 3, 4, 5, 6, 7, 8, 9];
list.sort(() => {
    return Math.random() - 0.5;
});
// Output
(9) [2, 5, 1, 6, 9, 8, 4, 3, 7]
// Call it again
(9) [4, 1, 7, 5, 3, 8, 2, 9, 6]
```
## 14. Nullish Coalescing Operator

The nullish coalescing operator (??) is a logical operator that returns its right-hand side operand when its left-hand side operand is null or undefined, and otherwise returns its left-hand side operand.
```
const foo = null ?? 'my school';
// Output: "my school"

const baz = 0 ?? 42;
// Output: 0
```
## 15. Rest & Spread operators

Those mysterious 3 dots ... can rest or spread!🤓
```
function myFun(a,  b, ...manyMoreArgs) {
   return arguments.length;
}
myFun("one", "two", "three", "four", "five", "six");

// Output: 6

and

const parts = ['shoulders', 'knees']; 
const lyrics = ['head', ...parts, 'and', 'toes']; 

lyrics;
// Output: 
(5) ["head", "shoulders", "knees", "and", "toes"]
```
## 16. Default Parameters
```
const search = (arr, low=0,high=arr.length-1) => {
    return high;
}
search([1,2,3,4,5]);

// Output: 4
```
## 17. Convert Decimal to Binary or Hexa

We can use some in-built methods like .toPrecision() or .toFixed() to achieve much of helping functionalities while solving problems.
```
const num = 10;

num.toString(2);
// Output: "1010"
num.toString(16);
// Output: "a"
num.toString(8);
// Output: "12"
```
## 18. Simple Swap 2 values using Destructuring
```
let a = 5;
let b = 8;
[a,b] = [b,a]

[a,b]
// Output
(2) [8, 5]
```
## 19. Single-liner Palindrome check

Well, this is not a shorthand trick overall but it will give you clear idea to play with strings.
```
function checkPalindrome(str) {
  return str == str.split('').reverse().join('');
}
checkPalindrome('naman');
// Output: true
```
## 20. Turn Object attributes into an Array of attributes
```
Using Object.entries(),Object.keys() and Object.values()

const obj = { a: 1, b: 2, c: 3 };

Object.entries(obj);
// Output
(3) [Array(2), Array(2), Array(2)]
0: (2) ["a", 1]
1: (2) ["b", 2]
2: (2) ["c", 3]
length: 3

Object.keys(obj);
(3) ["a", "b", "c"]

Object.values(obj);
(3) [1, 2, 3]
```
So that's it guys for now! 🤗
