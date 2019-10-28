# random.js

A very basic javascript implementation of the most basic tools from [Random.hx](https://github.com/haxegon/haxegon/blob/master/haxegon/Random.hx) by [Terry Cavanagh](https://github.com/TerryCavanagh)

## Usage

```javascript
let rnd = new Random();

let newBool = rnd.bool();
let newRandom = rnd.random(); /* random float between 0 and 1 */
let newInteger = rnd.int(20, 80); /* random integer between 20 and 80 */
let newFloat = rnd.float(20.0, 80.0); /* random float between 20.0 and 80.0 */
let newChance = rnd.chance(80.0); /* 80% chance to return true */
let newString = rnd.string(40, '0123456789abcdef'); /* random 40 character string, using [0-9a-f] */
let newPick = rnd.pick(['one', 'two', 'three']); /* returns a random value from an array */
let newShuffledArray = rnd.shuffle(['a', 'b', 'c', 'd', 'e', 'f']); /* returns a shuffled array */
let newWeightedPick = rnd.weighted(['a', 'b', 'c', 'd', 'e', 'f'], [1,1,1,2,2,6]); /* returns a weighted array pick */
```

## Notes

For lack of proper xorshift, such as [xorshift.js](https://github.com/AndreasMadsen/xorshift/blob/master/xorshift.js), this uses the [Web Cryptography API](https://developer.mozilla.org/en-US/docs/Web/API/Crypto) to generate random values. If not available, it falls back to `Math.random()`. I know.

If you need a more rounded random package, [Chance.js](https://github.com/chancejs/chancejs) looks to be the solution. I liked Terry Cavanagh's go at the problem, because it was readable and small in size and scope; the daily bread. I stripped the seed mechanism from it because I don't need it and don't understand it well enough to reproduce it accurately.

## Warning

It is unlikely I'll update this very often. Take it as is. If you like it, I accept donations and tips aka. support :)
