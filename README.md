# numbers.js [![Build Status](https://travis-ci.org/numbers/numbers.js.png)](https://travis-ci.org/numbers/numbers.js)
Numbers - an advanced mathematics toolkit for JavaScript and Node.js, adapted for Inner Core


## Description

Numbers provides a comprehensive set of mathematical tools that currently are not offered in JavaScript.  These tools include:

* Basic calculations
* Calculus
* Matrix Operations
* Prime Numbers
* Statistics
* More...

A few things to note before using: JavaScript, like many languages, does not necessarily manage floating points as well as we'd all like it to. For example, if adding decimals, the addition tool won't return the exact value. This is an unfortunate error. Precautions have been made to account for this. After including numbers, you can set an error bound. Anything in this will be considered an "acceptable outcome."

The primary uses cases are client side operations which the DOM will recognize (e.g. 1.1px == 1px). It can be used for data analysis, calculations, etc. on the server as well.

## How to use

Numbers is pretty straightforward to use.

With node, simply require it:
```javascript
var numbers = require('numbers');
```

For example, if we wanted to estimate the integral of sin(x) from -2 to 4, we could:

Use Riemann integrals (with 200 subdivisions)

```javascript
numbers.calculus.Riemann(Math.sin, -2, 4, 200);
```

Or use adaptive simpson quadrature (with epsilon .0001)

```javascript
numbers.calculus.adaptiveSimpson(Math.sin, -2, 4, .0001);
```

User-defined functions can be used too:

```
var myFunc = function(x) {
  return 2*Math.pow(x,2) + 1;
}

numbers.calculus.Riemann(myFunc, -2, 4, 200);
numbers.calculus.adaptiveSimpson(myFunc, -2, 4, .0001);
```

Now say we wanted to run some matrix calculations:

We can add two matrices

```javascript
var array1 = [0, 1, 2];
var array2 = [3, 4, 5];

numbers.matrix.addition(array1, array2);
```

We can transpose a matrix

```javascript
numbers.matrix.transpose(array);
```

When working with vectors, treat them like single row matrices:

```javascript
var vector1 = [[1, 0, 0]];
```

Numbers also includes some basic prime number analysis.  We can check if a number is prime:

```javascript
// basic check
numbers.prime.simple(number);

// Miller-Rabin primality test
numbers.prime.millerRabin(number);
```

The statistics tools include mean, median, mode, standard deviation, random sample generator, correlation, confidence intervals, t-test, chi-square, and more.

```javascript
numbers.statistic.mean(array);
numbers.statistic.median(array);
numbers.statistic.mode(array);
numbers.statistic.standardDev(array);
numbers.statistic.randomSample(lower, upper, n);
numbers.statistic.correlation(array1, array2);
```
For further documentation, check out [numbers.github.io](http://numbers.github.io/)

## Test

To execute, run:

```
npm test
```

Note: Make sure to install the plugins by running `npm install`.

With gulp:

```
npm run g-test
```

## Lint

To perform a code quality check using jshint, run 

```
npm run lint
```

or, with gulp:

```
npm run g-lint
```

Running without gulp will error on warnings.

## Format Code

To format all the tests and lib files using jsbeautifier, run 

```
npm run format
```

or, with gulp:

```
npm run g-format
```

## Build

To update the public JavaScript, run

```
npm run build
```

This will compile the entire library into a single file accessible at src/numbers.js. It will also minify the file into public/numbers.min.js.

With gulp:

```
npm run g-build
```

Numbers.js is also available on Bower via

```
$ bower install numbers.js
```

## Core Team
* Steve Kaliski - [@stevekaliski](http://twitter.com/stevekaliski)
* David Byrd - [@thebyrd](http://twitter.com/thebyrd)
* Ethan Resnick - [@studip101](http://twitter.com/studip101)
* Dakota St. Laurent - [@SaintDako](https://github.com/SaintDako)
* Kartik Talwar - [@KartikTalwar](https://github.com/KartikTalwar)

## Contributors
In no particular order:
* [Ethan aka `altercation`](https://github.com/altercation)
* [Hrishikesh Paranjape aka `hrishikeshparanjape`](https://github.com/hrishikeshparanjape)
* [Greg Leppert aka `leppert`](https://github.com/leppert)
* [Lars-Magnus Skog aka `ralphtheninja`](https://github.com/ralphtheninja)
* [Tim Wood aka `codearachnid`](https://github.com/codearachnid)
* [Miles McCrocklin aka `milroc`](https://github.com/milroc)
* [Nate Kohari aka `nkohari`](https://github.com/nkohari)
* [Eric LaForce aka `elaforc`](https://github.com/elaforc)
* [btmills aka `btmills`](https://github.com/btmills)
* [swair shah aka `swairshah`](https://github.com/swairshah)
* [Jason Hutchinson aka `Zikes`](https://github.com/Zikes)
* [Philip I. Thomas aka `philipithomas`](https://github.com/philipithomas)
* [Brandon Benvie aka `Benvie`](https://github.com/Benvie)
* [Larry Battle aka `LarryBattle`](https://github.com/LarryBattle)
