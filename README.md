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

#### get last strings
```js
let string = '俺のフレンチ・イタリアンなどの本格一流料理を冷凍商品化しご自宅へお届け【俺のEC】(21-0119)　(s00000021625001)';
console.log(string.match(/\([^)]*\)\s\([^)]*\)$/)); // ["(21-0119)　(s00000021625001)"]
```
#### get last string without patheneses
```js
let str = "格安SIM/スマホ【BIGLOBEモバイル】（08-0207）(s00000000040003) asjdalkjlksdfj skldfjslkdfj slkdfjsd";
console.log(str.match(/(?<=（|\()[^)）]*(?=）|\))(?!.*\(|（)/));//["s00000000040003"]
```

#### check number(negative and positive number)
```js
/^\-?[0-9]+$/
```
