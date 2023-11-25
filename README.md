# SoJS

Professional fullstack dev since 2017


## Quick access


### json2array
Convert a JSON object to an array

#### Usage:
`json2array({"thing1":{"key1":"value"},"thing2":{"otherKey":"otherVal"}});`
`[{"key1":"value","key":"thing1"},{"otherKey":"otherVal","key":"otherVal"}]`
```js
function json2array(json) {
    var result = [];
    var keys = Object.keys(json);
    keys.forEach(function (key) {
        var endJSON = json[key];
        endJSON.key = key
        result.push(endJSON);
    });
    return result;
}
```

### SumArrays
Add two vectors togeth
```js
function sumArrays(...arrays) {
    const n = arrays.reduce((max, xs) => Math.max(max, xs.length), 0);
    const result = Array.from({ length: n });
    return result.map((_, i) => arrays.map(xs => xs[i] || 0).reduce((sum, x) => sum + x, 0));
}
```

### rand
Generates a random number X digits long
```js
function rand(digits) {
    return Math.floor(Math.random() * parseInt('8' + '9'.repeat(digits - 1)) + parseInt('1' + '0'.repeat(digits - 1)));
}
```


### isEmptyObject
Checks to see if an object is equal to `{}`
```js
function isEmptyObject(obj) {
    for (var key in obj) {
        if (obj.hasOwnProperty(key))
            return false;
    }
    return true;
}
```

### uid
Vanilla JS generate UID

```js
const uid = () => {
  let
    d = new Date().getTime(),
    d2 = ((typeof performance !== 'undefined') && performance.now && (performance.now() * 1000)) || 0;
  return 'xxxxxxxx-xxxx-4xxx-yxxx-xxxxxxxxxxxx'.replace(/[xy]/g, c => {
    let r = Math.random() * 16;
    if (d > 0) {
      r = (d + r) % 16 | 0;
      d = Math.floor(d / 16);
    } else {
      r = (d2 + r) % 16 | 0;
      d2 = Math.floor(d2 / 16);
    }
    return (c == 'x' ? r : (r & 0x7 | 0x8)).toString(16);
  });
};
```

### randRange
Generates a random number in range

```js
function randRange(min, max) {
  return Math.random() * (max - min) + min;
}
```
