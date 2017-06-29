
JSON5 • HJSON • HanSON • SON • CSON • USON •
JSON Lines • NDJSON •
HOCON • HCL • UCL



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
- Optional Unquoted String Values
- "Raw" String (e.g. `''` instead of `""`) 
  - No need to escape `\` or `"` etc. To escape `'` use `'''` e.g. `''''Henry's Themes'''`
- More Data Types (`set`, `map`, `symbol`, etc.)
- And much more


## What's Next?

[JSON5](#json5) •
[HJSON](#hjson) •
[HanSON](#hanson) •
[SON](#son) •
[CSON](#cson) •
[USON](#uson)


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


### HanSON 

_JSON for Humans_

github: [timjansen/hanson](https://github.com/timjansen/hanson)

Adds:

- HanSON is JSON with comments, multi-line strings and unquoted property names.
- Comments use JavaScript syntax (`//`, `/**/`).
- Supports backticks as quotes (\`\`) for multi-line strings.
- You can use either double-quotes (`""`) or single-quotes (`''`) for single-line strings.
- Property names do not require quotes if they are valid JavaScript identifiers.
- Commas after the last list element or property will be ignored.
- Every JSON string is valid HanSON.
- HanSON can easily be converted to real JSON.


```js
{
  listName: "Sesame Street Monsters", // note that listName needs no quotes
  content: [
    {
      name: "Cookie Monster",
      /* Note the template quotes and unescaped regular quotes in the next string */
      background: `Cookie Monster used to be a
monster that ate everything, especially cookies.
These days he is forced to eat "healthy" food.`
    }, {
      // You can single-quote strings too:
      name: 'Herry Monster',
      background: `Herry Monster is a furry blue monster with a purple nose.
He's mostly retired today.`
    },    // don't worry, the trailing comma will be ignored
   ]
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

CSON:

``` coffeescript
# Comments!!!

# An Array with no commas!
greatDocumentaries: [
	'earthlings.com'
	'forksoverknives.com'
	'cowspiracy.com'
]

# An Object without braces!
importantFacts:
	# Multi-Line Strings! Without Quote Escaping!
	emissions: '''
		Livestock and their byproducts account for at least 32,000 million tons of carbon dioxide (CO2) per year, or 51% of all worldwide greenhouse gas emissions.
		Goodland, R Anhang, J. “Livestock and Climate Change: What if the key actors in climate change were pigs, chickens and cows?”
		WorldWatch, November/December 2009. Worldwatch Institute, Washington, DC, USA. Pp. 10–19.
		http://www.worldwatch.org/node/6294
		'''

	landuse: '''
		Livestock covers 45% of the earth’s total land.
		Thornton, Phillip, Mario Herrero, and Polly Ericksen. “Livestock and Climate Change.” Livestock Exchange, no. 3 (2011).
		https://cgspace.cgiar.org/bitstream/handle/10568/10601/IssueBrief3.pdf
		'''

	burger: '''
		One hamburger requires 660 gallons of water to produce – the equivalent of 2 months’ worth of showers.
		Catanese, Christina. “Virtual Water, Real Impacts.” Greenversations: Official Blog of the U.S. EPA. 2012.
		http://blog.epa.gov/healthywaters/2012/03/virtual-water-real-impacts-world-water-day-2012/
		“50 Ways to Save Your River.” Friends of the River.
		http://www.friendsoftheriver.org/site/PageServer?pagename=50ways
		'''

	milk: '''
		1,000 gallons of water are required to produce 1 gallon of milk.
		“Water trivia facts.” United States Environmental Protection Agency.
		http://water.epa.gov/learn/kids/drinkingwater/water_trivia_facts.cfm#_edn11
		'''

	more: 'http://cowspiracy.com/facts'
```

same as:

``` javascript
{
  "greatDocumentaries": [
    "earthlings.com",
    "forksoverknives.com",
    "cowspiracy.com"
  ],
  "importantFacts": {
    "emissions": "Livestock and their byproducts account for at least 32,000 million tons of carbon dioxide (CO2) per year, or 51% of all worldwide greenhouse gas emissions.\nGoodland, R Anhang, J. “Livestock and Climate Change: What if the key actors in climate change were pigs, chickens and cows?”\nWorldWatch, November/December 2009. Worldwatch Institute, Washington, DC, USA. Pp. 10–19.\nhttp://www.worldwatch.org/node/6294",
    "landuse": "Livestock covers 45% of the earth’s total land.\nThornton, Phillip, Mario Herrero, and Polly Ericksen. “Livestock and Climate Change.” Livestock Exchange, no. 3 (2011).\nhttps://cgspace.cgiar.org/bitstream/handle/10568/10601/IssueBrief3.pdf",
    "burger": "One hamburger requires 660 gallons of water to produce – the equivalent of 2 months’ worth of showers.\nCatanese, Christina. “Virtual Water, Real Impacts.” Greenversations: Official Blog of the U.S. EPA. 2012.\nhttp://blog.epa.gov/healthywaters/2012/03/virtual-water-real-impacts-world-water-day-2012/\n“50 Ways to Save Your River.” Friends of the River.\nhttp://www.friendsoftheriver.org/site/PageServer?pagename=50ways",
    "milk": "1,000 gallons of water are required to produce 1 gallon of milk.\n“Water trivia facts.” United States Environmental Protection Agency.\nhttp://water.epa.gov/learn/kids/drinkingwater/water_trivia_facts.cfm#_edn11",
    "more": "http://cowspiracy.com/facts"
  }
}
```


### USON

_μson - A compact human-readable data serialization format specially designed for shell_

github: [burningtree/uson](https://github.com/burningtree/uson)

Principles:

- Superset of JSON (every JSON is valid μson).
- Whitespace is not significant.
- String quoting `"` is optional.
- In Array or Object, comma `,` can be replaced by whitespace ` `.
- Assignation with colon `:` can be repeated to create nested objects.
- You can use own types, casting is done by `!` character.

USON:

```
number:12.05 text:Banana quotedText:"John Devilseed" empty:null good:true
```

same as:

```json
{
  "number": 12.05,
  "text": "Banana",
  "quotedText": "John Devilseed",
  "empty": null,
  "good": true
}
```

USON:

```
simple:[1 2 3] texts:[Malta Budapest "New York"] objects:[{id:1}]
```

same as:

```json
{
  "simple": [
    1,
    2,
    3
  ],
  "texts": [
    "Malta",
    "Budapest",
    "New York"
  ],
  "objects": [
    {
      "id": 1
    }
  ]
}
```



## JSON is the New CSV - JSON Formats for Line-Oriented Tables / Records 

_One Line, One Data Record_

[JSON Lines](#json-lines) •
[NDJSON ](#ndjson) 


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




## More Formats 

_: = {} []_

### HOCON

_Human-Optimized Config Object Notation_

github: [typesafehub/config/HOCON](https://github.com/typesafehub/config/blob/master/HOCON.md)

### HCL 

_HashiCorp Configuration Language_

github: [hashicorp/hcl](https://github.com/hashicorp/hcl)


### UCL

_Universal Configuration Language_

github: [vstakhov/libucl](https://github.com/vstakhov/libucl)


### AXON

_AXON is eXtended Object Notation_ 

web: [intellimath.bitbucket.io/axon](https://intellimath.bitbucket.io/axon/)



### And More

See [Format Extensions](https://github.com/burningtree/awesome-json#format-extensions), 
[Supersets](https://github.com/burningtree/awesome-json#supersets) and
[Related Formats](https://github.com/burningtree/awesome-json#related-formats)
in [Awesome JSON (@burningtree)](https://github.com/burningtree/awesome-json) 




## Meta

**License**

![](https://publicdomainworks.github.io/buttons/zero88x31.png)

The awesome list is dedicated to the public domain. Use it as you please with no restrictions whatsoever.

**Questions? Comments?**

Post them to the [wwwmake forum](http://groups.google.com/group/wwwmake). Thanks!
