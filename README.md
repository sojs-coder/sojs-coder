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
