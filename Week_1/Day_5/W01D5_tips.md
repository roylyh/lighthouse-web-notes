# Roy's Notes

## Eslint
```
npm install -g eslint
curl -o /vagrant/.eslintrc.json https://gist.githubusercontent.com/kvirani/6cdb9511522d4357839718a050e7dd3b/raw/.eslintrc.json
eslint <filename> --fix
```
json is a customized file which is used by LightHouse Labs
```
eslint [options] file.js
example:
eslint <filename> --fix
```

[How to set vscode fomatter as eslint](https://daveceddia.com/vscode-use-eslintrc/)

## Stock Market
```javascript
// divide and conquer
// divede the array into two and imagin the buy point and the sell point are from different subarrays
// recursion
const maxProfit = function(data) {
  let maxP = -1;
  if (data.length > 1) {
    const mid = Math.floor(data.length / 2);
    const data1 = data.slice(0, mid);
    const data2 = data.slice(mid);
    maxP = Math.min(...data1) < Math.max(...data2) ? Math.max(...data2) - Math.min(...data1) : -1;
    maxP = Math.max(maxProfit(data1),maxProfit(data2)) > maxP ? Math.max(maxProfit(data1),maxProfit(data2)) : maxP;
  }
  return maxP;
};

console.log(maxProfit([45, 24, 35, 31, 40, 38, 11]));
console.log(maxProfit([45,23,35]));
```