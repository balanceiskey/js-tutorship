# Functions (and some other things) Workshop

Alright, young grasshopper, you've picked up a lot of new tricks over the past few weeks and we want to put them to them to the test. Below you'll find a series of questions. Use Chrome's snippet manager and JS console to come up with solutions. You can also use previous notes, your amigos in the room and our favorite, Google, for consultation if you need additional help.

Here we go!

## A Really, Uber-Quick Review of Things We Know

- Primitives (numbers, strings, booleans)
- Boolean operators
- Variables
- Basic Functions

## Out on the edges of a space frontier...

As we run through these, use Chrome's snippet tool to paste in code as we go.

1. Let's build a starfighter. To start, your trusted vehicle needs a name. Make the log statement here register as `true`, by providing a valid shipName. (And of course, see what happens when we don't provide a valid shipName)

    ```js
    var shipName = '';

    // make this true, by setting the name above
    console.log('Is ship name valid?', (shipName.length > 3 && shipName.length < 18));
    ```

2. Alright, we've got a name. Let's give it a few more qualities. Add the following lines to your code:

    ```js
    var shipSpeed = 125;

    console.log('current ship speed', shipSpeed);
    ```

3. We need to know if the values we provided for `shipSpeed`are any good. Let's start by writing a function called `shipSpeedIsValid`. It should take as parameters a speed and return `true` if the speed provided is *greater than* `2.2` and *less than or equal to* `15`.

    ```js
    // write your function here:

    console.log('Is ship speed valid?', shipSpeedIsValid(shipSpeed));
    ```

Clearly, something's wrong with the speed we initially provided. Make our function return `true` by setting an appropriate value.

4. We want to know if our fancy new starfighter is capable of cloaking, so let's write a function called `canCloak` that checks if our `shipSpeed` is between 3 and 6 (inclusive on both counts), and set the value to a variable.

    ```js
    // write your function here:

    var shipCanCloak = canCloak(shipSpeed);
    console.log('Can ship cloak?', shipCanCloak);
    ```

5. Similar to above, we want to know if our starfighter can shield. Write a function, `canShield` that takes as a parameter the ship's speed, and then verifies that the provided speed is greater than 6 and that the ship cannot cloak.

    ```js
    // write your function here

    var shipCanShield = canShield(shipSpeed);

    console.log('Can ship shield?', shipCanShield);
    ```

6. Every space encounter is a gamble. Write a function, `hasLuck`, that takes as a parameter a ship name, and checks whether the first letter is 'a', or the last letter is 'z', or that the length of the name is equal to 7. Note, we haven't officially done equality just yet, so I'll give you the first part for free.

    ```js
    function hasLuck (name) {
        return (name[0].toLowerCase() === 'a' //... fill in the rest);
    }

    var shipHasLuck = hasLuck(shipName);

    console.log('Does your ship have luck?', hasLuck);
    ```

7. We know a lot about the starfighter now, but how does it stack up in a fight? Write a function, `printStarfighterStats`, that takes a total of 4 parameters: `shipOneName`, `shipOneSpeed`, `shipTwoName`, `shipTwoSpeed`. Use the name and speed of each ship to generate whether the ship can shield, whether the ship can cloak and whether the ship has luck (use the functions you wrote above), and print them out. Comment out the above `console.logs` to make things a little easier to navigate.

    ```js
    function printStarfighterStats (shipOneName, shipOneSpeed, shipTwoName, shipTwoSpeed) {
        // write it out
    }
    ```








