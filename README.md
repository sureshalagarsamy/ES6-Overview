# ES6 - Overview

ECMAScript (ES) is a scripting language specification standardized by ECMAScript International.

### JavaScript
JavaScript started life with the name Mocha, and was briefly named LiveScript before being officially renamed to JavaScript. It is a scripting language that is executed by the browser.

ECMAScript6 has the following new features.

 * Support for constants
 * Block Scope
 * Arrow Functions
 * Extended Parameter Handling
 * Modules
 * Classes
 * Iterators
 * Generators
 * Collections
 * New built in methods for various classes
 * Promises

### JavaScript Variable Scope


 - ```Global Scope``` − A variable with global scope can be accessed from within any part of the JavaScript code.

 - ```Local Scope``` − A variable with a local scope can be accessed from within a function where it is declared.

##### ES6 defines a new variable scope - The Block scope.

# 1
### The Let and Block Scope

```javascript
function test() { 
   var num = 9;
   console.log("value of num in test() "+num);
   (function() { 
      console.log("Inner Block begins") 
      let num = 90 
      console.log("value of num : "+num)  
   })(); 
} 
test();

// Output
// value of num in test() 9
// Inner Block begins
// value of num : 90
```

The script declares a variable num within the local scope of a function and re-declares it within a block using the let keyword. 

#### Example: let v/s var

```javascript
var no = 10; 
var no = 20; 
console.log(no);

// Output 20
```

Let us re-write the same code using the ```let``` keyword.

```javascript
let no = 10; 
let no = 20; 
console.log(no);
```

The above code will throw an error: Identifier 'no' has already been declared. 

``` Uncaught SyntaxError: Identifier 'no' has already been declared ```

# 2

### The const

The following rules hold true for a variable declared using the const keyword 

 * Constants cannot be reassigned a value.
 * A constant cannot be re-declared.
 * A constant requires an initializer. This means constants must be initialized during its declaration.
 * The value assigned to a ```const``` variable is immutable (unable to change).

# 3

### Lambda Functions / Arrow functions

There are 3 parts to a Lambda function

* ```Parameters``` − A function may optionally have parameters.
* lambda notation ```(=>)``` It is also called as the goes to operator.
* Statements − Represents the function’s instruction set.

It is an anonymous function expression that points to a single line of code. Following is the syntax for the same.

```
([param1, parma2,…param n] )=>statement;
```

###  Lambda Expression

```javascript
var foo = (x)=>10+x 
console.log(foo(10));

// Output 20
```
The function returns the sum of 10 and the argument passed.

### Lambda Statement

It is an anonymous function declaration that points to a block of code. This syntax is used when the function body spans multiple lines. Following is the syntax of the same.

```
( [param1, parma2,…param n] )=> {       
   //code block 
}
```

Example

```javascript
var msg = ()=> { 
   console.log("function invoked") 
} 
msg();

// Output : function invoked 
```

#### Syntactic Variations

Optional parentheses for a single parameter.

```javascript
var msg = x=> { 
   console.log(x) 
} 
msg(10)
```

Optional braces for a single statement. Empty parentheses for no parameter.

```javascript
var disp = ()=>console.log("Hello World") 
disp();
```

# 4

### Returning Multiple Values

ES6 provides a array like syntax to assign multiple variables to values of array indexes ```destructuring feature```. It also lets you ignore some array indexes.

```javascript
function function_name()
{
    return [1, 6, 7, 4, 8, 0]; 
}
var q, w, e, r, t, y;
//Here we are using ES6's array destructuring feature to assign the returned values to variables.
//Here we are ignoring 2 and 4 array indexes
[q, w, , r, , y] = function_name();

alert(y);//y is 0
```
