```js
function checkIsPrime(num) {
    if (num === 1){return false;}
    if (num === 2 || num === 3){return true;}
    if (num % 2 === 0)
    {
        return false;
    }else if(num % 3 === 0){
        return false
    }
    return true;
}

```