# Control Flow Workshop

Hello space pilot! It seems your ship is in need of repairs and a few upgrades. Let's walk through tuning your craft now that you've acquired a few more skills. To review here are a few things we've recently gone over:

- Equality Checks
- Control Flow: If-Else-Else If
- For Loops

## Diagnostics

In order to properly diagnose what's gone wrong with your ship's systems we'll want to write a small utility function called `assertEquals` that takes two arguments and checks if they're equal. It should return `true` or `false`.

Once you've written it, check to make sure the following executes as expected (you'll see the expected return values commented to the right of each statement):

```js
assertEquals(1, 1); // true
assertEquals('one', 'one'); // true
assertEquals(true, true); // true
assertEquals(1 < 10, 4 < 5); // true
assertEquals(1, 0); // false
assertEquals('one', 'zero'); // false
assertEquals(-1 > 1, 1 === 1); // false
```

## Virus

Got your utility function ready-to-go? Good.

On your last foray into the nether regions of space things didn't go so well. A pair of humans managed to re-write some source code on your vessel when you attempted to scan them (Yes, they were Jeff Goldblum and Will Smith). Things haven't worked so well since. Your thrusters have been inexplicably firing at odd times, your comm systems have been contacting longtime exes and all of that cheese you stocked up on the last planetary run has gone bad because your refridgeration has gone dead.

It's just not good. Fortunately, we've found at least part of the problem. It seems the following function is where Jeff Goldblum's crafty hacker code first struck. Here's how it reads now:

```js
function toggleEngineSpeed (currentShipSpeed) {
    if (currentShipSpeed === 0) {
        return 0;
    } else {
        return 100;
    }
}
```

Fortunately, we've got your handy diagnostic function to help us out. Re-write the above function to make sure the following uses of `assertEquals` return `true`.

```js
assertEquals(toggleEngineSpeed(0), 100);
assertEquals(toggleEngineSpeed(100), 0);
assertEquals(toggleEngineSpeed(50), 0);
```

## Communications

Curse you Jeff Goldblum! Anyways, your engines should be in working order now. Onward to figuring out why you can't seem to contact anyone.

Here's are the next few broken functions:

```js
function contact (name) {
    if (name === 'Mom') {
        return '7215123';
    } else if (name === 'Port') {
        return true;
    } else {
        return 8675309;
    }
}
```

Make the following assert `true`:

```js
assertEquals(contact('Mom'), 7215123);
assertEquals(contact('Port'), 4125012);
assertEquals(contact('Unknown'), false);
```


## Message Decryption

Alright, before we get into the meat of this next one, a quick JavaScript reminder. When dealing with strings you can access some interesting properties. One of those is grabbing a single letter (or 'character') from a string using a position value called an `index`. That looks something like this:

```js
var aString = 'Here is a string';
var firstCharacter = aString[0]; // remember, strings are '0-indexed', meaning we start counting from 0

var lastCharacter = aString[aString.length - 1]; // and so the last value isn't the length, but the length minus 1.

var fourthCharacter = aString[3];

console.log('first character', firstCharacter);
console.log('last character', lastCharacter);
console.log('fourth character', fourthCharacter);
```

One other quick note about strings, you can also find the index of a character on string using the `indexOf` function. Its usage looks like this:

```js
var aString = 'Here is a string';

var indexPositionOfH = aString.indexOf('H');
var indexPositionOfS = aString.indexOf('s');

console.log('the position of H', indexPositionOfH);
console.log('the position of s', indexPositionOfS);
```

Okay, now that know a little bit more about strings, let's figure out why we can't seem to decrypt messages from our fellow starfighters. It seems the `decryptMessage` function we use isn't working as expected. It's supposed to work by running through each letter of the message, finding the matching index in the `scrambledAlphabet` and then using that index to find the real letter from the `alphabet`. But, it seems like some of the scrambles have been a little funky lately and in some cases just not working. Here's the broken function:


```js

function decryptMessage (encryptedMessage) {
    var alphabet = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ';
    var scrambledAlphabet = 'WKOJGYXQITNHBUVEPFDCZMLSAR';
    var decryptedMessage = '';

    for (var i = 0; i < encryptedMessage.length; i++) {
        var encryptedLetter = encryptedMessage[i];
        var scrambledIndex = scrambledAlphabet.indexOf(encryptedLetter);
        var realLetter = alphabet[scrambledIndex];


        decryptedMessage = decryptedMessage + realLetter;
    }

    return decryptedMessage;
}

```

Try and make these asserts pass by fixing the broken function above:

```js
assertEquals(decryptMessage('qghhv'), 'HELLO');
assertEquals(decryptMessage('QGHHV'), 'HELLO');
assertEquals(decryptMessage('oqwfcfgzdg'), 'CHARTREUSE');
```

## Virus Prevention (Extra Credit!)

We don't ever want Jeff Goldblum to hack us again, so let's write some antivirus mechansims.

Human viruses seem to exhibit an uncommonly high number of semicolons. How might you write a function called `hasTooManyCommas` that takes as its argument a string of source code. It should then run through each character of the code and count the number of commas. If the ratio of commas to the length of the source is greater than or equal to `0.05` let's return `true`;

The following asserts should pass:

```js
var codeExampleOne = "var cipher = 'ABCD'; var scramble = [];";
var codeExampleTwo = "just a silly string, probably not code";
var codeExampleThree = "No just; No; No; No;";

assertEquals(hasTooManyCommas(codeExampleOne), true);
assertEquals(hasTooManyCommas(codeExampleTwo), false);
assertEquals(hasTooManyCommas(codeExampleThree), true);
```


## Extra-extra credit

How could you make your virus prevention function smarter? Are there other things you could look for?
