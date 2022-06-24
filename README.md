# random.js

A very basic javascript implementation of most of the tools from [Random.hx](https://github.com/haxegon/haxegon/blob/master/haxegon/Random.hx) by [Terry Cavanagh](https://github.com/TerryCavanagh)

## Usage

```javascript
import { random } from './random.js'

let rnd = new random();

let newBool = rnd.bool();
let newRandom = rnd.random(); /* random float between 0 and 1 */
let newInteger = rnd.int(20, 80); /* random integer between 20 and 80 */
let newFloat = rnd.float(20.0, 80.0); /* random float between 20.0 and 80.0 */
let newChance = rnd.chance(80.0); /* 80% chance to return true */
let newString = rnd.string(40, '0123456789abcdef'); /* random 40 character string, using [0-9a-f] */
let newPick = rnd.pick(['one', 'two', 'three']); /* returns a random value from an array */
let newShuffledArray = rnd.shuffle(['a', 'b', 'c', 'd', 'e', 'f']); /* returns a shuffled array */
let newWeightedPick = rnd.weighted(['a', 'b', 'c', 'd', 'e', 'f'], [1,1,1,2,2,6]); /* returns a weighted array pick */
let newChallenge = rnd.challenge(20, 150, 75); /* % chance to return true, based on value between lower and upper bounds */
```

## Notes

Values are derived using `mulberry32` (https://stackoverflow.com/a/47593316/3625228), with a small built-in hash method to allow for alphanum seed values. All this is not perfect, but this version allows for manually setting seed, as well as getting and setting.

```javascript
let rnd = new random('custom-seed-string');
const bak = rnd.getState();
rnd.setState('other-seed');
```

This will produce predictable outcomes, as used in many games.

If you need a more rounded random package, [Chance.js](https://github.com/chancejs/chancejs) looks to be the solution. I liked Terry Cavanagh's go at the problem, because it was readable and small in size and scope; the daily bread. ~~I stripped the seed mechanism from it because I don't need it and don't understand it well enough to reproduce it accurately.~~

## Warning

It is unlikely I'll update this very often. Take it as is. If you like it, I accept donations and tips aka. support :)
