```js
function isAscending(arr) {
    return arr.every(function (element, index) {
        return index === 0 || element >= arr[index - 1];
    });
}
```

```js
function isDescending(arr) {
    return arr.every(function (element, index) {
        return index === 0 || element <= arr[index - 1];
    });
}
```

