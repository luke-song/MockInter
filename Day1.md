Day1 Journal for Ray & Luke 
Tips -> 

Practice the Ray’s template Question -> Communicate(Ask for clarification on requirement)
 ->	 Think in user’s perspective for edge cases (empty,capital..etc) -> Ask hypothetical questions 
example. 
 q) what if both input strings are empty, should i return as true or false?
  q) input string can have a special character? such as !, @, $. Or input string can have alphabetical letters only? 
  q) if the input strings have only alphabetical letters, can it have a lowerlower only or uppercases? 
  ex) str1 = 'abc', str2 = 'acB'.  

-> 	write a pseudo code and time complexity like this 
Example.
  P:
    1. check edge cases( input null or not)
   2. check input strs len. if they are different, then return false right away
   3. sort both input strs
    4. compare the sorted arrays. if they are not same, return false
    5. return true
  time: o(nlogn) n is for the looping, nlogn is for the sort. space: o(1) 

-> 	finally, write a function like this (It’s nice practice to follow python logic, simpler) *learn py
Example.
function arePermutations(str1, str2) {
  //check edge cases
  if ((str1.length) == 0 && (str2.length) == 0 ) return true;
  if (str1.length !== str2.length) return false;

  //ex) str1 = "cab" , str2 = "bac" => arr1 = "abc", arr2 = "abc"
  newStr1 = str1.toLowerCase();
  newStr2 = str1.toLowerCase();
  const arr1 = newStr1.split('').sort();  
  const arr2 = newStr2.split('').sort();

  // const arr1 = str1.toLowerCase().split('').sort();
  // const arr2 = str2.toLowerCase().split('').sort();
  // return arr1.join('') === arr2.join('');

  //compare the sorted arrays
  for(let i=0; i<arr1.length; i++){
    if(arr1[i] !== arr2[i]){
      return false
    }
  }

  return true;

  
}

const str1 = "abc"
const str2 = "Bac"

if (arePermutations(str1, str2)){
  console.log('they are permutaions')
} else {
  console.log('not permutations')
}










Organized Notes ->

Interview Question 1: String Permutations

Concept: The goal is to check if two strings are permutations of each other, meaning they have the same characters but in a different order.

Code:

function arePermutations(str1, str2) {
  // Check edge cases
  if (str1.length === 0 && str2.length === 0) return true; // Both strings are empty, consider them as permutations
  if (str1.length !== str2.length) return false; // Different lengths, not permutations

  // Convert strings to lowercase
  const newStr1 = str1.toLowerCase();
  const newStr2 = str2.toLowerCase();

  // Sort the characters in both strings
  const arr1 = newStr1.split('').sort();
  const arr2 = newStr2.split('').sort();

  // Compare the sorted arrays
  for (let i = 0; i < arr1.length; i++) {
    if (arr1[i] !== arr2[i]) {
      return false; // Characters at the same index are different, not permutations
    }
  }

  return true; // All characters are the same, permutations
}

const str1 = "abc";
const str2 = "Bac";

if (arePermutations(str1, str2)) {
  console.log('They are permutations');
} else {
  console.log('Not permutations');
}


Edge cases and considerations:

If both input strings are empty, they should be considered permutations.
The input strings can contain special characters or be composed of alphabetical letters only.
The code converts the strings to lowercase before comparing them to ignore case differences.
The code checks for the same length of the input strings. If the lengths are different, they are not permutations.
The time complexity of the function is O(n log n) due to sorting, where n is the length of the strings.
The space complexity is O(1) since the function only uses a constant amount of extra space.

Interview Question 2: Polymorphism

Concept: Polymorphism is the ability of an object to take on many forms. In object-oriented programming, it allows objects of different classes to be treated as objects of a common superclass.

class School {}

interface English {
  name: string;
}

abstract class Korean {
  student: string;
}


Explanation:

The code defines an empty class School.
It defines an interface English with a name property.
It defines an abstract class Korean with a student property.

Interview Question 3: Understanding let and var in JavaScript

Concept: The question is about the difference between let and var in JavaScript, particularly in terms of their scope.

Code:
function constLet() {
  console.log(x); // Output: undefined
  let x = 1;

  foo(); // Output: "Hello, world!"
  function foo() {
    console.log("Hello, world!");
  }
}

console.log(constLet());



Explanation:

The code demonstrates the usage of let and the hoisting behavior of var.
Within the constLet function, the code tries to log the value of x before declaring it using let. It logs undefined because let variables are hoisted but not initialized until the declaration.
The code defines a function foo after the console.log(x), and then calls it. The function is successfully called and logs "Hello, world!" because function declarations (like foo) are hoisted along with their function bodies.
Additional information:

let and var are used to declare variables in JavaScript.
Variables declared with let are block-scoped, meaning they are only accessible within the block in which they are declared.
Variables declared with var are function-scoped, meaning they are accessible within the function in which they are declared, as well as any nested functions.
Hoisting is a JavaScript behavior where variable and function declarations are moved to the top of their containing scope during the compilation phase, allowing them to be used before they are declared. However, only function declarations are fully hoisted, while variables declared with let or const are hoisted but not initialized until the declaration.



Archive ->
  //"Write a function in JavaScript that takes in two strings as arguments and returns true if the strings are permutations of each other, and false otherwise. A permutation is defined as a rearrangement of the characters in a string. For example, 'abc' and 'cba' are permutations of each other, but 'abc' and 'def' are not."

/*
  q) what if both input strings are empty, should i return as true or false?
  q) input string can have a special character? such as !, @, $. Or input string can have alphabetical letters only? 
  q) if the input strings have only alphabetical letters, can it have a lowerlower only or uppercases? 
    ex) str1 = 'abc', str2 = 'acB'.  

  P:
    1. check edge cases( input null or not)
    2. check input strs len. if they are different, then return false right away
    3. sort both input strs
    4. compare the sorted arrays. if they are not same, return false
    5. return true

  time: o(nlogn) n is for the looping, nlogn is for the sort. space: o(1) 
*/

function arePermutations(str1, str2) {
  //check edge cases
  if ((str1.length) == 0 && (str2.length) == 0 ) return true;
  if (str1.length !== str2.length) return false;

  //ex) str1 = "cab" , str2 = "bac" => arr1 = "abc", arr2 = "abc"
  newStr1 = str1.toLowerCase();
  newStr2 = str1.toLowerCase();
  const arr1 = newStr1.split('').sort();  
  const arr2 = newStr2.split('').sort();

  // const arr1 = str1.toLowerCase().split('').sort();
  // const arr2 = str2.toLowerCase().split('').sort();
  // return arr1.join('') === arr2.join('');

  //compare the sorted arrays
  for(let i=0; i<arr1.length; i++){
    if(arr1[i] !== arr2[i]){
      return false
    }
  }

  return true;

  
}

const str1 = "abc"
const str2 = "Bac"

if (arePermutations(str1, str2)){
  console.log('they are permutaions')
} else {
  console.log('not permutations')
}

/*
I : inheratance
P : polymorphism
A: Abstaction
E: Encapsulation
*/


/*
polymorphism
*/

class School {
  
}

interface class English {
  name: string
  
}

 
abstract class Korean {
  student: string
}

// class Shape {
//   constructor() {
//     if (new.target === Shape) {
//       throw new Error('Cannot instantiate abstract class.');
//     }
//   }
//   getArea() {
//     throw new Error('Method not implemented.');
//   }
// }

// class Rectangle extends Shape {
//   constructor(width, height) {
//     super();
//     this.width = width;
//     this.height = height;
//   }
//   getArea() {
//     return this.width * this.height;
//   }
// }

// let shape = new Shape(); // Throws an error
// let rectangle = new Rectangle(5, 10);
// console.log(rectangle.getArea()); // Output: 50

// // Polymorphism example

// class School {
//     constructor(name) {
//       this.name = name;
//     }
//     getDescription() {
//       return `This is a ${this.name} school.`;
//     }
//     getSchool(){
          return name
      }
//        
//
//   }
  
//   class English extends School {
//     constructor() {
//       super("English");
        
//     }
//     getDescription() {
//       return `This is an ${this.name} school. We will be learning about literature and language.`;
//     }give 
            

            
//   }
  
//   class Korean extends School {
//     constructor() {
//       super("Korean");
//     }
//     getDescription() {
//       return `This is a ${this.name} school. We will be learning about Korean language and culture.`;
//     }
//   }
  
//   let englishSchool = new English();
//   let koreanSchool = new Korean();
  
//   console.log(englishSchool.getDescription());
//   console.log(koreanSchool.getDescription());


/*
async + await
*/

// The main difference between let and var is their scope. Variables declared with var are function-scoped, meaning they are accessible within the function in which they are declared, as well as any nested functions. Variables declared with let, on the other hand, are block-scoped, meaning they are only accessible within the block in which they are declared (e.g. within a loop or an if statement

 function constLet(){
    // let response = 1

    // response = 2

    // console.log(response)
   
    console.log(x); // Output: undefined
    let x = 1;

    foo(); // Output: "Hello, world!"
    function foo() {
      console.log("Hello, world!");
    }
 }

   // var x;
   // function foo() {
   //    console.log("Hello, world!");
   //  }å

   //  console.log(x); // Output: undefined
   //  x = 1;

   //  foo(); // Output: "Hello, world!"
   //  }

console.log(constLet())


//
//https://docs.google.com/document/d/1m2-a90V1LNsGu_sloHwrrjJLKFMR9mrnnKD3S9euTH0/edit?usp=sharing

          

