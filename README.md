# flattenArr
Array Flattening in 5 lines

```
function flattenArr(arrToFlatten, depth) {
    return arrToFlatten.reduce((acc, value, index, array) => {
      if (value instanceof Array && depth) {
        return acc.concat(flattenArr(value, depth - 1));
      }
      return acc.concat(value);
    }, []);
}
```

**Usage:**
```
const arr = [1,2,3,[4,5, [4,6,7,[8, 9, [10]]]]];
console.log(flattenArr(arr, 1));
```

