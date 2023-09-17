Its part of breaking changes in Ethers 6.

Replace

```js
const { upkeepNeeded } = await raffle.callStatic.checkUpkeep([]);

ethers.utils.parseETH("0.1");
```

with

```js
const { upkeepNeeded } = await raffle.checkUpkeep.staticCall("0x");

ethers.parseETH("0.1");
```
