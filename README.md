Horrible.js
===========
For all your horrible Javascript needs.

Horrible.js is really more of an _obfuscator_ than a compiler, as the resulting code will __always__ come out larger. It uses some of Javascript's quirks to produce completely, utterly unreadable code.

*If you were looking for a horrible js compiler that is, in itself horrible, check out [LukeZbihlyj's fork](https://github.com/LukeZbihlyj/horrible-horrible.js), which probably caters to your twisted desire.*

Usage
-----
If you're not going to hack on the code, you can use an online version [here](http://tshadwell.github.com/horrible.html).

Otherwise, you can grab the latest version:

`git clone git@github.com:TShadwell/horrible.js.git`

into your folder of choice, open index.html.

## Using the browser

At the bottom of the page there are two boxes, one for code and one for output that can be used to compile code, in addition to a slider, some radio bottons and a text input. Explainations of the functions are given below.

The three radio buttons correspond to different amounts of obfuscation- radio 1 is as in the example, radio 2 encodes just the string "constructor" and radio 3 encodes `_[_][_]`, completely avoiding the use of underscores.
## Using Javascript

There are two functions that can be used to compile code, both of which take 2 arguments, the code to compile (as a string) and the variable to use when compiling (also as a string):

`compileToString`, which, as it says compiles code into a string that when evaluated will yeild the original code as a string. Good for obfuscating strings.

`compile`, which will compile the code and package in a particularly horrible form of exec to execute the code.

In addition, the `code` object can be used to compile the code from the textarea via `code.compileToString()` and `code.compile()`.

There is a 'Horror factor', which determines how much to mess up the resulting code. The factor can be changed with `window.horror`.
* Factor 1: As normal.
* Factor 2: Indexes encoded with quirks.
* Factor 3: Indexes and char-codes encoded with quirks.

To execute the code, Horrible.js uses `_="constructor";_[_][_](CODE)`. This works because the constructor of string is `String` and the constructor of string is `Function`, so it effectively runs `(new Function (CODE))();`.

The code used to construct the Function from the string can be changed with `window.constructo`.
## Example

Factor 1:

compile("console.log('test')","$")

    "$=String.fromCharCode(46,103,40,39,41);_="constructor";_[_][_](([![]]+{})[+!+[]+[+[]]]+([]+[]+{})[+!+[]]+([]+[]+[][[]])[+!+[]]+(![]+[])[!+[]+!+[]+!+[]]+([]+[]+{})[+!+[]]+(![]+[])[!+[]+!+[]]+(!![]+[])[!+[]+!+[]+!+[]]+$[0]+(![]+[])[!+[]+!+[]]+([]+[]+{})[+!+[]]+$[1]+$[2]+$[3]+(!![]+[])[+[]]+(!![]+[])[!+[]+!+[]+!+[]]+(![]+[])[!+[]+!+[]+!+[]]+(!![]+[])[+[]]+$[3]+$[4])();"

Inputting:

    $=String.fromCharCode(46,103,40,39,41);_="constructor";_[_][_](([![]]+{})[+!+[]+[+[]]]+([]+[]+{})[+!+[]]+([]+[]+[][[]])[+!+[]]+(![]+[])[!+[]+!+[]+!+[]]+([]+[]+{})[+!+[]]+(![]+[])[!+[]+!+[]]+(!![]+[])[!+[]+!+[]+!+[]]+$[0]+(![]+[])[!+[]+!+[]]+([]+[]+{})[+!+[]]+$[1]+$[2]+$[3]+(!![]+[])[+[]]+(!![]+[])[!+[]+!+[]+!+[]]+(![]+[])[!+[]+!+[]+!+[]]+(!![]+[])[+[]]+$[3]+$[4])();

test

Factor 2:

    $=String.fromCharCode(46,103,40,39,41);_="constructor";_[_][_](([![]]+{})[+!+[]+[+[]]]+([]+[]+{})[+!+[]]+([]+[]+[][[]])[+!+[]]+(![]+[])[!+[]+!+[]+!+[]]+([]+[]+{})[+!+[]]+(![]+[])[!+[]+!+[]]+(!![]+[])[!+[]+!+[]+!+[]]+$[(+[])]+(![]+[])[!+[]+!+[]]+([]+[]+{})[+!+[]]+$[(+!+[])]+$[(+!+[]+!+[])]+$[(+!+[]+!+[]+!+[])]+(!![]+[])[+[]]+(!![]+[])[!+[]+!+[]+!+[]]+(![]+[])[!+[]+!+[]+!+[]]+(!![]+[])[+[]]+$[(+!+[]+!+[]+!+[])]+$[(+!+[]+!+[]+!+[]+!+[])])();

Factor 3:

    $=String.fromCharCode((+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]),(+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]),(+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]),(+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]),(+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]+!+[]));_="constructor";_[_][_](([![]]+{})[+!+[]+[+[]]]+([]+[]+{})[+!+[]]+([]+[]+[][[]])[+!+[]]+(![]+[])[!+[]+!+[]+!+[]]+([]+[]+{})[+!+[]]+(![]+[])[!+[]+!+[]]+(!![]+[])[!+[]+!+[]+!+[]]+$[(+[])]+(![]+[])[!+[]+!+[]]+([]+[]+{})[+!+[]]+$[(+!+[])]+$[(+!+[]+!+[])]+$[(+!+[]+!+[]+!+[])]+(!![]+[])[+[]]+(!![]+[])[!+[]+!+[]+!+[]]+(![]+[])[!+[]+!+[]+!+[]]+(!![]+[])[+[]]+$[(+!+[]+!+[]+!+[])]+$[(+!+[]+!+[]+!+[]+!+[])])();
