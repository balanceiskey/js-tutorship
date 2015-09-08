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
    
    console.log('Is ship name valid?', (shipName.length > 3 && shipName.length > 18));
    ```

2. Alright, we've got a name. Let's give it a few more qualities. Add the following lines to your code:

    ```js
    var shipSpeed = 125;
    var hasCloak = true;
    var hasShield = false;
    
    console.log('current ship speed', shipSpeed);
    console.log('ship has cloak', hasCloak);
    console.log('ship has shield', hasShield);
    ```

3. We need to know if the values we provided for `shipSpeed`, `hasCloak` and `hasShield` are any good. Let's start by writing a function called `shipSpeedIsValid`. It should take as parameters a speed and return `true` if the speed provided is *greater than* `4.2` and *less than or equal to* `15`. It's okay if the ship speed is currently invalid.

    ```js
    // write your function here:
    
    console.log('Is ship speed valid?', shipSpeedIsValid(shipSpeed));
    ```

4. Similar to above, we want to know if `hasCloak` is valid, so let's write a function called `hasCloakIsValid` that checks if our `shipSpeed` is between 3 and 6 (inclusive on both counts). It's okay if the hasCloak value is currently invalid.

    ```js
    // write your function here:
    
    console.log('Is ship\'s cloak value valid?', hasCloakIsValid(shipSpeed));
    ```

5. Alright, we've got one last value we need to verify, `hasShield`. Write a function, `hasShieldIsValid` that checks that shipSpeed is greater than 6 and that hasCloak is `false`. It's okay if the hasShield value is currently invalid.

    ```js
    // write your function here
    
    console.log('Is ship\'s shield value valid?', hasShieldIsValid(shipSpeed));
    ```

6. Alright, we know a lot of things about our ship, but you've probably noticed a lot of the values don't seem exactly right. Reassign anything that's coming up as `false` so that they instead become `true`.

7. Okay, I'm going to give you a freebie function. It looks like this:

    ```js
    function hasLuck (name) {
        return (shipName[0].toLowerCase() === 'a' || shipName[shipName.length - 1].toLowerCase() === 'z');
    }

    var hasLuck = hasLuck(shipName);
    
    console.log('Does your ship have luck?', hasLuck);
    ```

No code for this one, but can you explain what's going on here?

8.







