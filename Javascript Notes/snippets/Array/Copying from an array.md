```js
function copyArray(arr1, arr2){
arr1 = arr2.slice(0);
}
```

You can't just do arr1 = arr2, it will modify both arrays.