# Solution for Challenge

## Next Highest Number

```javascript
const nextHighestNumber = (num) => {
	let tempNum = num
		.toString()
		.split('')
		.map((item) => +item);
	let index = null;
	for (let i = tempNum.length - 2; i >= 0; i--) {
		if (tempNum[i] < tempNum[i + 1]) {
			index = i;

			break;
		}
	}
	if (index == null) return -1;
	const begin = tempNum.slice(0, index);

	tempNum = tempNum.filter((item, i) => i >= index).sort((a, b) => b - a);
	tempNum = +[...begin, ...tempNum].join('');
	return tempNum;
};
```

The source code is located [here](./nextHighestNumber.js)
