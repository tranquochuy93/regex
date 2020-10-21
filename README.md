# regex
### greedy and lazy search
```js
let text = 'BLA text text text  text text text BLA text text text text LOOK LOOK text text text BLA text text BLA';
// lazy
let matchs = text.match(/BLA.*?LOOK/g); // [BLA text text text  text text text BLA text text text text LOOK]
// greedy
matchs = text.match(/BLA.*LOOK/g); // [BLA text text text  text text text BLA text text text text LOOK LOOK]
```
### closest match
```js
let text = 'BLA text text text  text text text BLA text text text text LOOK LOOK text text text BLA text text BLA';
// lazy
let matchs = text.match(/BLA(?:(?!BLA|LOOK)[\s\S])*LOOK/g); // [BLA text text text text LOOK]

```
