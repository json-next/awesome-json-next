
JSON5 • HJSON • SON • CSON



# Awesome JSON - What's Next? 

A Collection of What's Next for Awesome JSON (JavaScript Object Notation) for rich structured (meta) data in (plain) text


#### _Contributions welcome. Anything missing? Send in a pull request. Thanks._


## What's Missing in JSON?

1. Comments, Comments, Comments
2. Unquoted Keys
3. Multi-Line Strings 
   - a) Folded -- Folds Newlines 
   - b) Unfolded
4. Trailing Commas in Arrays and Objects



More:

- Date/DateTime/Timestamp Type
- Optional Commas 
- "Raw" String (e.g. `''` instead of `""`) 
  - No need to escape `\` or `"` etc. To escape `'` use `'''` e.g. `''''Henry's Themes'''`



## What's Next?

[JSON5](#JSON5) •
[HJSON](#HJSON) •
[SON](#SON) •
[CSON](#CSON)


### JSON5 

_Modern JSON - JSON for the ES5 Era_

web: [json5.org](http://json5.org),
github: [json5](https://github.com/json5)

JSON for "Humans" (not Machines). Adds:

- Comments- Allow both inline (single-line) and block (multi-line) comments are allowed (like ES5)
- Keys can be unquoted if they're valid identifiers e.g. a-z0-9 (like ES5)
- Single and double quoted strings (like ES5)
- Allows multi-line string with backslash (like ES5)
- Allow trailing commas for arrays and objects.
- And some more.

```
// This file is written in JSON5 syntax, naturally, but npm needs a regular
// JSON file, so compile via `npm run build`. Be sure to keep both in sync!

{
    name: 'json5',
    version: '0.5.0',
    description: 'JSON for the ES5 era.',
    keywords: ['json', 'es5'],
    author: 'Aseem Kishore <aseem.kishore@gmail.com>',
    contributors: [
        // TODO: Should we remove this section in favor of GitHub's list?
        // https://github.com/json5/json5/contributors
        'Max Nanasy <max.nanasy@gmail.com>',
        'Andrew Eisenberg <andrew@eisenberg.as>',
        'Jordan Tucker <jordanbtucker@gmail.com>',
    ],
    main: 'lib/json5.js',
    bin: 'lib/cli.js',
    files: ["lib/"],
    dependencies: {},
    devDependencies: {
        gulp: "^3.9.1",
        'gulp-jshint': "^2.0.0",
        jshint: "^2.9.1",
        'jshint-stylish': "^2.1.0",
        mocha: "^2.4.5"
    },
    scripts: {
        build: 'node ./lib/cli.js -c package.json5',
        test: 'mocha --ui exports --reporter spec',
            // TODO: Would it be better to define these in a mocha.opts file?
    },
    homepage: 'http://json5.org/',
    license: 'MIT',
    repository: {
        type: 'git',
        url: 'https://github.com/json5/json5',
    },
}
```

### HJSON

_A "Human" User Interface for JSON_

web: [hjson.org](http://hjson.org),
github: [hjson](https://github.com/hjson)

- Commas Optional
- Add comments, hash-style (#), line-style (//) and block-style (/* */)
- Allow Keys without quotes
- Allow Strings without quotes
- Allow Multi-line strings Python-style e.g. ''' text '''

```
{
  // use #, // or /**/ comments,
  // omit quotes for keys
  key: 1
  // omit quotes for strings
  contains: everything on this line
  // omit commas at the end of a line
  cool: {
    foo: 1
    bar: 2
  }
  // allow trailing commas
  list: [
    1,
    2,
  ]
  // and use multiline strings
  realist:
    '''
    My half empty glass,
    I will fill your empty half.
    Now you are half full.
    '''
}
```

### SON

_Simple Object Notation_

github: [aleksandergurin/simple-object-notation](https://github.com/aleksandergurin/simple-object-notation)

Adds:

- comments starts with # sign and ends with newline (\n)
- comma after a key-value pair is optional
- comma after an array element is optional

```
{
  # Personal information
    
  "name": "Alexander Grothendieck"
  "fields": "mathematics"
  "main_topics": [
    "Etale cohomology"
    "Motives"
    "Topos theory"
    "Schemes"
  ]
}
```


### CSON

_CoffeeScript-Object-Notation. Same as JSON but for CoffeeScript objects_

github: [bevry/cson](https://github.com/bevry/cson)







## JSON Formats for Line-Oriented Tables / Records - JSON is the New CSV

_One Line, One Data Record_

[JSON Lines](#JSON-Lines) •
[NDJSON ](#NDJSON) 


### JSON Lines

web: [jsonlines.org](http://jsonlines.org)

One Line, One Record - Newline (nl or \n) Separated

```
["Name", "Session", "Score", "Completed"]
["Gilbert", "2013", 24, true]
["Alexa", "2013", 29, true]
["May", "2012B", 14, false]
["Deloise", "2012A", 19, true] 
```

Pros:

- Supports JSON Datatypes (Numbers, Bool, Null, etc.)


or nested data records e.g.

```
{"name": "Gilbert", "wins": [["straight", "7♣"], ["one pair", "10♥"]]}
{"name": "Alexa", "wins": [["two pair", "4♠"], ["two pair", "9♠"]]}
{"name": "May", "wins": []}
{"name": "Deloise", "wins": [["three of a kind", "5♣"]]}
```


### NDJSON 

_Newline Delmited JSON_

web: [ndjson.org](http://ndjson.org), 
github: [ndjson](https://github.com/ndjson)


1. Line Separator is '\n' 
2. Each Line is a valid JSON Value

```
{"some":"thing"}
{"foo":17,"bar":false,"quux":true}
{"may":{"include":"nested","objects":["and","arrays"]}}
```

(Source: [specs.okfnlabs.org/ndjson](http://specs.okfnlabs.org/ndjson))




## Meta

**License**

![](https://publicdomainworks.github.io/buttons/zero88x31.png)

The awesome list is dedicated to the public domain. Use it as you please with no restrictions whatsoever.

**Questions? Comments?**

Post them to the [wwwmake forum](http://groups.google.com/group/wwwmake). Thanks!
