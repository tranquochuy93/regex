# regex
#### get any characters thay may be break line(\r\n) character
```js
let text = 'BLA text text text  text text text BLA text text text text LOOK ' + '\r\n' + 'LOOK text text text BLA text text BLA';
// greedy
matchs = text.match(/BLA.*LOOK/g); // [BLA text text text  text text text BLA text text text text LOOK]
matchs = text.match(/BLA[\s\S]*LOOK/g); // [BLA text text text  text text text BLA text text text text LOOK \r\nLOOK]
// fastest
matchs = text.match(/BLA[^]*LOOK/g); // [BLA text text text  text text text BLA text text text text LOOK \r\nLOOK]
```
#### greedy and lazy search
```js
let text = 'BLA text text text  text text text BLA text text text text LOOK LOOK text text text BLA text text BLA';
// lazy
let matchs = text.match(/BLA.*?LOOK/g); // [BLA text text text  text text text BLA text text text text LOOK]
// greedy
matchs = text.match(/BLA.*LOOK/g); // [BLA text text text  text text text BLA text text text text LOOK LOOK]
```
#### closest match
```js
let text = 'BLA text text text  text text text BLA text text text text LOOK LOOK text text text BLA text text BLA';
// lazy
let matchs = text.match(/BLA(?:(?!BLA|LOOK)[\s\S])*LOOK/g); // [BLA text text text text LOOK]

```
- Positive lookahead: X(?=Y) finds X and then checks if there’s Y IMMEDIATELY after it
- Negative lookahead: X(?!Y), it means "search X, but only if not followed by Y"
- Positive lookbehind: (?<=Y)X, matches X, but only if there’s Y before it.
- Negative lookbehind: (?<!Y)X, matches X, but only if there’s no Y before it.
# ?: none group capture????????????
