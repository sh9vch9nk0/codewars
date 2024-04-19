# Codewars JavaScript Solutions

## One Line Task: Making Pizza (7 kyu)

### Task

Fix the code to pass all the tests. Unfortunately, you can only modify **ONE** line of code :(

### Rules

Usually, the changes you make are limited to one line. Please don't complain that you can't write your own code, because this is a `bugfix` kata. Also, don't complain that the initial code is too messy. That's why you need to do the task ;-)

- You can do the following operations:

  - Replace the existing characters.
  - Add the character at the end of the line.

- You should not Add a new line or Delete a line.

- The overall difference of the modified code is less than 5 characters.

### Example

Some exmples of modify operations:

```
var hello = "word"   <--- initial code
                 xxx  <--- 3 characters modified
var hello = "world"  <--- modified code

var hello = "world"  <--- initial code
             x     x  <--- 2 characters modified
var hello = 'world'  <--- modified code

var hello = "world"  <--- initial code
     xxxxxxxxxxxxxxxx <--- don't try to insert chars at the middle
var  hello = "world" <--- modified code

var hell = "world"   <--- initial code
          xxxxxxxxxx  <--- 10 characters modified
var hello = "world"  <--- bad way
         x            <--- 1 characters modified
var hello= "world"   <--- better way
```

### Solution

```
function makePizza(pieces) {
  var result = "";
  while ( pieces-- ){
    var needSteps = 5;
    while ( needSteps-- ) result += make( needSteps+1);
  }
  return result;
}
function make(step){
  switch ( step ){
    case 5: return "P";
    case 4: return "i";
    case 3:
    case 2: return "z";
    case 1: return "a";
  }
}
```
