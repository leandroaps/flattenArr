# flattenArr
Array Flattening in 5 lines

```
function flattenArr(arrToFlatten) {
    return arrToFlatten.reduce((acc, value) => {
      if (value instanceof Array) {
        return acc.concat(flattenArr(value));
      }
      return acc.concat(value);
    }, []);
}
```

**Usage:**
```
const arr = [1, 2, 3, 4, [5, 6]];
flattenArr(arr) // [1, 2, 3, 4, 5, 6]
```


```
function flattenArr(arrToFlatten, depth) {
    return arrToFlatten.reduce((acc, value) => {
      if (value instanceof Array && depth > 0) {
        return acc.concat(flattenArr(value, depth - 1));
      }
      return acc.concat(value);
    }, []);
}
```

**Usage:**
```
const arr = [1, 2, 3, 4, [5, 6, [7, 8]]];
flattenArr(arr, 1) // [1, 2, 3, 4, 5, 6, [7, 8]]
```
