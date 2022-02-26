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
           ` * {
                box-sizing: border box;
                margin: 0;
                padding: 0;
            }`

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


