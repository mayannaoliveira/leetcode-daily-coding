## 2635. Apply Transform Over Each Element in Array

#### Javascript

```JavaScript
/**
 * @param {number[]} arr
 * @param {Function} fn
 * @return {number[]}
 */
var map = function(arr, fn) {
    const result = [];
    for (let i = 0; i < arr.length; i++) {
        result.push(fn(arr[i], i));
    }
    return result;
};
```

#### TypeScript

```TypeScript
function map(arr: number[], fn: (n: number, i: number) => number): number[] {
    const result: number[] = [];
    for (let i = 0; i < arr.length; i++) {
        result.push(fn(arr[i], i));
    }
    return result;
}
```
