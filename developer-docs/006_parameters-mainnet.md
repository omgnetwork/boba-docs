---
description: A collection of links to get started on Mainnet Boba
---

# Mainnet Links

### Mainnet Links and Endpoints

|                   |                                                                                  |
| ----------------- | -------------------------------------------------------------------------------- |
| Mainnet RPC Read  | [https://lightning-replica.boba.network](https://lightning-replica.boba.network) |
| Mainnet Write RPC | [https://mainnet.boba.network](https://mainnet.boba.network)                     |
| Mainnet ChainID   | 288                                                                              |
| Gateway           | [https://gateway.boba.network](https://gateway.boba.network)                     |
| Blockexplorer     | [https://blockexplorer.boba.network](https://blockexplorer.boba.network)         |
| Websocket         | [wss://ws.mainnet.boba.network](wss://wss.mainnet.boba.network)                  |

### Mainnet Contract and Token Addresses

The `AddressManger` is located at '0x8376ac6C3f73a25Dd994E0b0669ca7ee0C02F089'. The `AddressManager` can be queried for current addresses like this:

```javascript
  this.AddressManager = new ethers.Contract(
    '0x8376ac6C3f73a25Dd994E0b0669ca7ee0C02F089',
    AddressManagerJson.abi,
    this.L1Provider
  )
  console.log("AddressManager Contract:",this.AddressManager)

  //obtain the current address of the Proxy__L1CrossDomainMessenger
  const address = await this.AddressManager.getAddress('Proxy__L1CrossDomainMessenger')

  /*********** NOTE *****************/
  /* If the contract is not in the AddressManager, then it will return the zero address: */
  /* 0x0000000000000000000000000000000000000000 */
```

As of Oct. 28 2021, the addresses are:

```json
{
  "L1CrossDomainMessenger":"0x12Acf6E3ca96A60fBa0BBFd14D2Fe0EB6ae47820",
  "OVM_L1CrossDomainMessenger":"0x12Acf6E3ca96A60fBa0BBFd14D2Fe0EB6ae47820",
  "Proxy__L1CrossDomainMessenger": "0x6D4528d192dB72E282265D6092F4B872f9Dff69e",
  "Proxy__L1StandardBridge":"0xdc1664458d2f0B6090bEa60A8793A4E66c2F1c00",
  "TK_L1OMG": "0xd26114cd6EE289AccF82350c8d8487fedB8A0C07",
  "TK_L2OMG": "0xe1E2ec9a85C607092668789581251115bCBD20de",
  "TK_L1USDT": "0xdac17f958d2ee523a2206206994597c13d831ec7",
  "TK_L2USDT": "0x5DE1677344D3Cb0D7D465c10b72A8f60699C062d",
  "TK_L1DAI": "0x6b175474e89094c44da98b954eedeac495271d0f",
  "TK_L2DAI": "0xf74195Bb8a5cf652411867c5C2C5b8C2a402be35",
  "TK_L1USDC": "0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48",
  "TK_L2USDC": "0x66a2A913e447d6b4BF33EFbec43aAeF87890FBbc",
  "TK_L1WBTC": "0x2260fac5e5542a773aa44fbcfedf7c193bc2c599",
  "TK_L2WBTC": "0xdc0486f8bf31DF57a952bcd3c1d3e166e3d9eC8b",
  "TK_L1REP": "0x221657776846890989a759ba2973e427dff5c9bb",
  "TK_L2REP": "0x8b5B1E971862015bc058234FC11ce6C4a4c536dD",
  "TK_L1BAT": "0x0d8775f648430679a709e98d2b0cb6250d2887ef",
  "TK_L2BAT": "0xc0C16dF1ee7dcEFb88C55003C49F57AA416A3578",
  "TK_L1ZRX": "0xe41d2489571d322189246dafa5ebde1f4699f498",
  "TK_L2ZRX": "0xf135f13Db3B114107dCB0B32B6c9e10fFF5a6987",
  "TK_L1SUSHI": "0x6b3595068778dd592e39a122f4f5a5cf09c90fe2",
  "TK_L2SUSHI": "0x5fFccc55C0d2fd6D3AC32C26C020B3267e933F1b",
  "TK_L1LINK": "0x514910771af9ca656af840dff83e8264ecf986ca",
  "TK_L2LINK": "0xD5D5030831eE83e22a2C9a5cF99931A50c676433",
  "TK_L1UNI": "0x1f9840a85d5af5bf1d1762f925bdaddc4201f984",
  "TK_L2UNI": "0xDBDE1347fED5dC03C74059010D571a16417d307e",
  "TK_L1DODO": "0x43Dfc4159D86F3A37A5A4B3D4580b888ad7d4DDd",
  "TK_L2DODO": "0x572c5B5BF34f75FB62c39b9BFE9A75bb0bb47984",
  "TK_L1TEST": "0xB68a38D3a10F28948EBf0f2450Fef348680F4714",
  "TK_L2TEST": "0xeDB79B0FD84c81E870b2fCB1D3CcF366179bA6D2",
  "TK_L1FRAX": "0x853d955acef822db058eb8505911ed77f175b99e",
  "TK_L2FRAX": "0xAb2AF3A98D229b7dAeD7305Bb88aD0BA2c42f9cA",
  "TK_L1FXS": "0x3432b6a60d23ca0dfca7761b7ab56459d9c964d0",
  "TK_L2FXS": "0xdc1664458d2f0B6090bEa60A8793A4E66c2F1c00",
  "TK_L1BOBA": "0x42bbfa2e77757c645eeaad1655e0911a7553efbc",
  "TK_L2BOBA": "0xa18bF3994C0Cc6E3b63ac420308E5383f53120D7",
  "L1CrossDomainMessengerFast": "0x329996D52cDbC617492428680A7a892e8f1c7c8C",
  "OVM_L1CrossDomainMessengerFast": "0x329996D52cDbC617492428680A7a892e8f1c7c8C",
  "Proxy__L1CrossDomainMessengerFast": "0xD05b8fD53614e1569cAC01c6D8d41416d0a7257E",
  "L2LiquidityPool": "0xB1a1B698E4c67c242441749C22575FA02B14D645",
  "L1LiquidityPool": "0x2B4c53C075c745eCC2AD3e3CF35E1cE4D246E92c",
  "Proxy__L1LiquidityPool": "0x1A26ef6575B7BBB864d984D9255C069F6c361a14",
  "Proxy__L2LiquidityPool": "0x3A92cA39476fF84Dc579C868D4D7dE125513B034",
  "L1MultiMessageRelayerFast": "0x16650A81cD8CC7e6d132bB98925efDeEA73E0d59"
}
```
