# Javascript Notes

### This is just a scratchpad of notes for me to reference about areas I don't always remember in Javascript or that I need to focus more time on


- # Node

    - ### What is Node?
        - An asynchronous event driven javascript runtime designed to build scalable network applications
        and upon each connection the callback is fired, but if there is no work to be done, node will sleep
        - in other words, it's a runtime environment outside the browser (that is, on the server) that can run javascript when needed for the site

- # HTML

    - ## HTML Form - know how to make a working HTML Form from scratch
        -The `<label>` element has a `for` attribute that associates the `<label>` with a specific `<input>` element. 
        - The `for` attribute’s value should match that of the `<input>` element’s `id` value. 
        - `<label>` elements are useful as they allow your `<input>` elements to be identified by screen readers.

- # CSS

    - ## CSS Pseudo-class - its just things like `link a:hover` or `p:first-child`

    - ## `border-box` model - content, padding, border, margin

    - ## What is the `box sizing: border-box;`?
        - it's a way of standardizing how CSS interacts with HTML elements
        - It guarantees that the content box of an element shrinks to make space for the padding and borders. Therefore, if you set your element width to 200 pixels, `border-box` makes sure that the content, padding, and borders fit in this number.



                    // base styling
                    * {
                        box-sizing: border box;
                        margin: 0;
                        padding: 0;
                    }

    - ## CSS GRID
        - ### In general, use CSS GRID for the overall page layout and large page components and Flexbox for smaller UI components
            - ### Use CSS GRID to make the content respond to the layout
            - ### Use Flexbox to make the layout respond to the content

- # JAVASCRIPT

    - ## Great general blog on all things javascript
        - https://2ality.com/index.html

    - ## Javascript Data Types
        - ### There are `6`
            -  string 
            -   number
            -   boolean
            -   null
            -   undefined 
            -   symbol

    - ## Javascript Objects


        - ### `Object.assign()` 
            - A quick way of making a clone of an Object in JavaScript is to use Object.assign.

        - https://www.digitalocean.com/community/tutorials/copying-objects-in-javascript


                const car = {
                color:'red'
                }

                const secondCar = Object.assign({}, car)
                car.wheels = 4;
                console.log(car);
                    // {color: 'red', wheels: 4}
                console.log(secondCar);
                    // {color: 'red'}

        - Updating car did not affect secondCar. Object.assign takes a target object as the first argument, and a source as the second one. In our example, we used an empty Object as our target and our car as the source.

        - ## Object instance methods
            - #### `hasOwnProperty()`
                - Indicates if the given property specified in the function argument exists on the `object` instance( and not on the `prototype`).
            - #### `isPrototypeOf()`
                - Checks whether the `object` specified in the argument is a `prototype` of another `object`.
            - #### `propertyIsEnumerable()`
                - Indicates if the given property specified in the argument can be enumerated using the for-in statement.
            - #### `toLocaleString()`
                - Returns a string representation of the `object` that is appropriate for the locale of execution context.
            - #### `toString()`
                - Returns a string representation of the `object`.
            - #### `valueOf()`
                - Returns a string, number or Boolean equivalent of te `object`. It often returns the same value as `toString()`

    - ## Javascript Arrays

        - ### `array.push()` 
            - adds items to the end of the array and returns the new length

        - ### `array.unshift()` 
            - adds an item to the beginning of an array and returns the new length

        - ### `array.pop()` 
            - removes the last item from array and returns the item

        - ### `array.shift()`
            - removes the first item from an array and returns the item




    - ## Escaping Characters 
        - uses a backslash \
            - include quotes in string
            - let quote = "\"Stay Awesome"\"; // "Stay Awesome"
        - let twosentences = "cat dog \n dog cat";  // new line

    - ## `null` vs. `undefined` 
        - `null` is the value of no value
        - `undefined` means a variable has only been initialized or declared but no value assigned

    - ## Arrow Functions () => {}

        - ### Arrow function and the `this` keyword
            -   Be careful when using arrow functions with the `this` keyword, as they behave differently from normal functions.
            -   **When using an arrow function, the `this` keyword is inherited from the ***parent scope.***
            -   Practice using `this` in object and function creation
        - ### The `arguments` object cannot be accessed on an arrow function
            -   Another difference between arrow functions and normal functions is the access to the arguments object. The arguments object is an array-like object that we can access from inside functions and contains the values of the arguments passed to that function.
            - However, `arguments` can be access in arrow functions using the spread `...` operator
            

                    const showWinner = (...args) => {
                    const winner = args[0];
                    console.log(`${winner} was the winner`)
                    }
                    showWinner("Usain Bolt", "Justin Gatlin", "Asafa Powell" )
                    // "Usain Bolt was the winner"

    - ## Default Function Arguments
        - prior to ES6 if you had a method that took three arguments and you were only passing it one of the arguments,
            it would error out and say cannot access `undefined`
        - So you had to pass `undefined` as an argument to the function for it to run

                function getLocation(continent,country,city){
                    if(typeof country === 'undefined'){
                        country = 'Italy'
                    }
                    if(typeof continent === 'undefined'){
                        continent = 'Europe'
                    }
                    console.log(continent,country,city)
                }

                getLocation(undefined, undefined,'Milan')
                // Europe Italy Milan

                getLocation(undefined,'Paris','France')
                // Europe Paris France


        - ES6 makes it very easy to set default function arguments. Let’s look at an example:

                function calculatePrice(total, tax = 0.1, tip = 0.05){
                    // When no value is given for tax or tip, the default 0.1 and 0.05 will be used
                    return total + (total * tax) + (total * tip);
                }
        - If you only provided two arguments, it would default the second argument to `tax` even if you meant it to be the `tip` argument
        - to get around that you can pass, in order `calculatePrice(20, undefined, 0.10)` to use the default `tax` value
        - or you can use desctructuring


                function calculatePrice({
                    total = 0,
                    tax = 0.1,
                    tip = 0.05} = {} ){
                    console.log(total + (total * tax) + (total * tip));
                }

                const bill = calculatePrice({ tip: 0.15, total:150 });
                // 187.5

        - We made the argument of our function an object. When calling the function, we don’t even have to worry about the order of the parameters because they are matched based on their key.
        -   In the example above, the default value for tip was 0.05, and we overwrote it with 0.15. But we didn’t give a value to tax which remained the default 0.1.

    - ## String Methods
        - ### `startsWith()`
        - ### `endsWith()`
        - ### `includes()`
        - ### `repeat()`


    - ## Exercise 1
        -   Check the following code snippet riddle:

        -   Determine the values logged to the console before you execute it.


                    'use strict';

                    var guessMe1 = 1;
                    let guessMe2 = 2;

                    {
                    
                        try {
                            console.log( guessMe1, guessMe2 ); // (A) 1, error - guessMe2 was never initialized
                        } catch(err) {
                            console.log("Error");
                        }
                        
                        let guessMe2 = 3;
                        console.log( guessMe1, guessMe2 ); // (B) 1, 3
                    }

                    console.log( guessMe1, guessMe2 ); // (C) 1, 2

                    const print_func = () => {

                        console.log( guessMe1 ); // (D) since function is never called, this never runs
                        var guessMe1 = 5;
                        let guessMe2 = 6;
                        console.log( guessMe1, guessMe2 ); // (E) since function is never called, this never runs
                    };


                    console.log( guessMe1, guessMe2 ); // (F) 1, 2


        - Let’s examine the six console logs one by one.

            -   (A): Here, guessMe1 holds the value original value of 1 as it has not been defined again in the block. The error is thrown because of guessMe2. Why? This is because we have defined it with the let keyword in line 14 of the block:

            -   let guessMe2 = 3;
            -   If we remove the try method and simply print line 9:

            -   console.log( guessMe1, guessMe2 );
            -   an error will still tell you that guessMe2 is uninitialized. Hence Error was the first output.

            -   (B): This console.log() will work because now

            -   guessMe1 == 1 and guessMe2 == 3.

            -   However, keep in mind that these values are only true for this particular block.

            -   (C): This will print the original values of both variables as we have moved outside the scope of the block above.

            -   guessMe1 == 1 and guessMe2 == 2.

            -   (D): The print_func function is never called in the program, hence its contents never run.

            -   (E): Just as for (D), the print_func function is never called in the program, hence its contents never run.

            -   (F): The console.log in this line is the same as that in (C). The values of both variables have not been altered anywhere in the global scope. Hence, the output is the same.


                    'use strict';

                    var guessMe1 = 1;
                    let guessMe2 = 2;

                    {
                        
                        try {
                            let guessMe2 = 3;
                            console.log( guessMe1, guessMe2 ); // (A) 1, 3
                        } catch(err){console.log("Error");}
                        
                        let guessMe2 = 3;
                        console.log( guessMe1, guessMe2 ); // (B) 1, 3
                    }

                    console.log( guessMe1, guessMe2 ); // (C) 1, 2

                    const print_func = () => {
                        var guessMe1 = 5;
                        console.log( guessMe1 ); // (D) 5
                        
                        let guessMe2 = 6;
                        console.log( guessMe1, guessMe2 ); // (E) 5, 6
                    };

                    print_func();


                    console.log( guessMe1, guessMe2 ); // (F) 1, 2