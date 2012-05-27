Horrible.js
===========
For all your horrible Javascript needs.

Horrible.js is really more of an _obfuscator_ than a compiler, as the resulting code will __always__ come out larger. It uses some of Javascript's quirks to produce completely, utterly unreadable code.

Usage
-----
After you grab the repo off git; that is:

`git clone git@github.com:TShadwell/horrible.js.git`

into your folder of choice, open the index.html with a browser that has a javascript console.

There are two functions that can be used to compile code, both of which take 2 arguments, the code to compile (as a string) and the variable to use when compiling (also as a string):

`compileToString`, which, as it says compiles code into a string that when evaluated will yeild the original code as a string. Good for obfuscating strings.

`compile`, which will compile the code and package in a particularly horrible form of exec to execute the code.
## Example
> compile("console.log('test')","$")

"$=String.fromCharCode(46,103,40,39,41);_="constructor";_[_][_](([![]]+{})[+!+[]+[+[]]]+([]+[]+{})[+!+[]]+([]+[]+[][[]])[+!+[]]+(![]+[])[!+[]+!+[]+!+[]]+([]+[]+{})[+!+[]]+(![]+[])[!+[]+!+[]]+(!![]+[])[!+[]+!+[]+!+[]]+$[0]+(![]+[])[!+[]+!+[]]+([]+[]+{})[+!+[]]+$[1]+$[2]+$[3]+(!![]+[])[+[]]+(!![]+[])[!+[]+!+[]+!+[]]+(![]+[])[!+[]+!+[]+!+[]]+(!![]+[])[+[]]+$[3]+$[4])();"

> $=String.fromCharCode(46,103,40,39,41);_="constructor";_[_][_](([![]]+{})[+!+[]+[+[]]]+([]+[]+{})[+!+[]]+([]+[]+[][[]])[+!+[]]+(![]+[])[!+[]+!+[]+!+[]]+([]+[]+{})[+!+[]]+(![]+[])[!+[]+!+[]]+(!![]+[])[!+[]+!+[]+!+[]]+$[0]+(![]+[])[!+[]+!+[]]+([]+[]+{})[+!+[]]+$[1]+$[2]+$[3]+(!![]+[])[+[]]+(!![]+[])[!+[]+!+[]+!+[]]+(![]+[])[!+[]+!+[]+!+[]]+(!![]+[])[+[]]+$[3]+$[4])();

test
