# Notes

## Stage for Future Updates - What's News?

### JSON with Commas and Comments (JWCC) 
- JSON with Commas and Comments @ <https://nigeltao.github.io/blog/2021/json-with-commas-comments.html>
  - Hacker News Discusion @ <https://news.ycombinator.com/item?id=26224255>, Feb 2021

### JSONC - A Json like file format with comments
- <https://komkom.github.io/>

```
{ /*
jsonc example
hit Format and check the json output
*/ // forgiving syntax

 hey:[this needs no commas ] // unquoted values

 give:[it,a,shot ] /* and lots of comments :) */ // try it for yourself

 "this":{
  "is":"also",
  "just":"a"
 },
 "json":"formatter"
}
```

### Visual Studio Code -JSON with Comments (JSONC)

- <https://code.visualstudio.com/docs/languages/json#_json-with-comments>

In addition to the default JSON mode following the JSON specification, 
VS Code also has a JSON with Comments (jsonc) mode. 
This mode is used for the VS Code configuration files such as `settings.json`, `tasks.json`, or `launch.json`. 
When in the JSON with Comments mode, you can use single line (`//`) as well as block comments (`/* */`) 
as used in JavaScript. 






## More Notes

### Bits On the Wire (by Tim Bray)

<https://www.tbray.org/ongoing/When/201x/2019/11/17/Bits-On-the-Wire>

JSON pros:

- Readers and writers are implemented in every computer language known to humankind, and they tend to interoperate correctly and frictionlessly with each other, particularly if you follow the interoperability guidelines in RFC 8259, which all the software I use seems to.

- It does a pretty good job of modeling nested-record structures.

- It's all-text, so humans can read it, which is super extra helpful.

- You can receive a JSON message you know nothing about and pick it apart successfully without knowing its schema, assuming it has one, which it probably doesn’t. So you can accomplish a task like "Pull out the item-count and item-price fields that are nested in the top-level order-detail field" with pretty good results given just a blob of raw JSON.

- You can reliably distinguish between numbers, strings, booleans, and null.


JSON cons:

- The type system is impoverished. There is no timestamp type, no way to know whether a number should be treated as an integer or float or Bignum, no way to signal when string values are really enums, and so on.

- Numbers are specially impoverished; in general you should assume that your repertoire is that of an IEEE double-precision float (but without NaN or ∞) which is adequate for most purposes, as long as you're OK with an integer range of ±253 (which you probably should be).

- Since JSON is textual, there is a temptation to edit it by hand, and this is painful since it’s nearly impossible to get the commas in the right places. On top of which there are no comments.

- JSON's textuality, and the fact that it carries its field labels along, no matter how deeply nested and often repeated, suggest that it is unnecessarily verbose, particularly when numeric values are represented in textual form. Also, the text needs to be converted into binary form to be loaded into objects (or structs, or dicts) for processing by code in memory.

- JSON doesn’t have a universally-accepted schema language. I have been publicly disappointed over "JSON Schema", the leading contender in that space; it’s just not very good. For a long time, the popular Swagger (now OpenAPI) protocols for specifying APIs used a variant version of a years-old release of JSON Schema; those are stable and well-tooled.



### Parsing JSON is a Minefield 💣 (by Nicolas Seriot)

<http://seriot.ch/parsing_json.php>


