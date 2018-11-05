In the previous lesson, we learned how to rewrite code to use arrays and while loops. And a few lessons before that, we learned how to use an array to get four squares to move. But, we noticed that a lot of the code for moving the squares was the same. Here's an example what we did. This is code is incomplete and copying and pasting into the console won't work. 

```javascript
function Square(){
    //create properties for square
}

var square1 = new Square();
var square2 = new Square();
var square3 = new Square();
var square4 = new Square();

var squares = [square1, square2, square3, square4];

//this is the code we want to imrpove
squares[0].position.x += 1;
squares[1].position.x += 1;
squares[2].position.x += 1;
squares[3].position.x += 1;
```

We're already using an array, so that's a good. The only thing that changes in the last four lines of code are the numbers between the square brackets. All the variables are being updated by adding 1 to their x position. And we now have a way of being able to change those numbers using a while loop.


To make our while loop, remember the guide we created earlier.

1. What's the end or stop condition?
2. What's the equivalent while condition?
3. What's the condition in code?

1. Stop condition  
All squares have been updated.

2. While condition  
Current position is a valid position in the array.

3. Code for while loop condition
`index < squares.length`

And we'll add a fourth step.

4. Code to do something with item at `index`
`squares[index].position.x += 1`;

And we can also use a table to check our logic.

|`index`|`squares.length`|`index < squares.length`|`squares[index]`|
|------:|---------------:|-----------------------:|---------------:|
|0      |4               | `true`                 |`square1`       |
|1      |4               | `true`                 |`square2`       |
|2      |4               | `true`                 |`square3`       |
|3      |4               | `true`                 |`square4`       |
|4      |4               | `false`                |`undefined`     |

Putting it all together looks like this. Again, this isn't complete code. We've simplified it to focus on the important details.

```javascript
function Square(){
    //create properties for square
}

var square1 = new Square();
var square2 = new Square();
var square3 = new Square();
var square4 = new Square();

//our array
var squares = [square1, square2, square3, square4];

//variable to keep track of current position in the array
var index = 0;

//this should look familiar
while(index < squares.length){
    //update x-position of square at position `index` in the array
    squares[index].position.x += 1;
}
```

Can you think of other ways to improve this code? For example, is it possible to rewrite this so we don't need variables `square1` through `square4`?

-----

At this point, you may have noticed a pattern. With an array, a variable for the position, the array's length, and a while loop, we can loop over all the items in any array, and do whatever we'd like with each item. We'll this _iteration_ from now on. And if we see this pattern or something similar in other code, there's a good chance the code is _iterating_, or cycling through items in an array.

_an iteration pattern_  
using a while loop to _iterate, or cycle through each item in an array
```javascript
//variable for the array
//could be named anything
var array;

//variable to keep track of position in the array
//could be named anything
var index = 0;

//some code that fills the array. could be anything.

//while loop to iterate through the array
//stops when the position of the array is invalid 
while(index < array.length){
    //code that uses `array[index]` to something with item at position `index` in the array
    //could be anything

    //increase `index` to position it at next item in the array
    index = index + 1;
}
```

