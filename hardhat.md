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

```js
const { deployer } = await getNamedAccounts();
const iWeth = await ethers.getContractAt(
  "IWeth",
  "0x7b79995e5f793A07Bc00c21412e50Ecae098E7f9",
  deployer
);
-------------------------
const { deployer } = await getNamedAccounts();
const singer = await ethers.getSigner(deployer);
const iWeth = await ethers.getContractAt(
  "IWeth",
  "0x7b79995e5f793A07Bc00c21412e50Ecae098E7f9",
  singer
);
```

```

```
