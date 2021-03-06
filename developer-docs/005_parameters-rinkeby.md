---
description: A collection of links to get started on Rinkeby Boba
---

# Rinkeby Links

## Rinkeby Links and Endpoints

|                 |                                                                                          |
| --------------- | ---------------------------------------------------------------------------------------- |
| Rinkeby RPC     | [https://rinkeby.boba.network](https://rinkeby.boba.network)                             |
| Rinkeby ChainID | 28                                                                                       |
| Gateway         | [https://gateway.rinkeby.boba.network](https://gateway.rinkeby.boba.network)             |
| Blockexplorer   | [https://blockexplorer.rinkeby.boba.network](https://blockexplorer.rinkeby.boba.network) |
| Websocket       | [wss://wss.rinkeby-v2.boba.network](wss://wss.rinkeby-v2.boba.network)                   |

## Rinkeby Contract Addresses

The `AddressManger` is located at '0x93A96D6A5beb1F661cf052722A1424CDDA3e9418'. The `AddressManager` can be queried for current addresses like this:

```javascript
  this.AddressManager = new ethers.Contract(
    '0x93A96D6A5beb1F661cf052722A1424CDDA3e9418',
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
  "L1CrossDomainMessenger":"0x04059a546419f54db4bfafFae9d4af3b081C2a8D",
  "L1MultiMessageRelayer":"0x5C6263BCAa00C7f5988E148dB3CA178e1262E69f",
  "Proxy__L1CrossDomainMessenger":"0xF10EEfC14eB5b7885Ea9F7A631a21c7a82cf5D76",
  "Proxy__L1StandardBridge":"0xDe085C82536A06b40D20654c2AbA342F2abD7077",
  "TK_L1USDT": "0xD9BA894E0097f8cC2BBc9D24D308b98e36dc6D02",
  "TK_L2USDT": "0x9d0364c866A73e34649869525CD7576080259A42",
  "TK_L1DAI": "0x5592EC0cfb4dbc12D3aB100b257153436a1f0FEa",
  "TK_L2DAI": "0x0630f97C8938051a44b0A64e9D4d484295393Fe4",
  "TK_L1USDC": "0x4DBCdF9B62e891a7cec5A2568C3F4FAF9E8Abe2b",
  "TK_L2USDC": "0xB24898De59C8E259F9742bCF2C16Fd613DCeA8F7",
  "TK_L1WBTC": "0x577D296678535e4903D59A4C929B718e1D575e0A",
  "TK_L2WBTC": "0x3074A3d2570e06F74F06913965adDcd1161D7fDC",
  "TK_L1REP": "0x6e894660985207feb7cf89Faf048998c71E8EE89",
  "TK_L2REP": "0x7896be8b69069bd39d71b3Fc987C6c0AFF7c3b95",
  "TK_L1BAT": "0xbF7A7169562078c96f0eC1A8aFD6aE50f12e5A99",
  "TK_L2BAT": "0x3C07C6627Aa879cD6988A5256E9A04D69DbD9530",
  "TK_L1ZRX": "0xddea378A6dDC8AfeC82C36E9b0078826bf9e68B6",
  "TK_L2ZRX": "0x23b274b0856C2F55C392d4F051BD252dF6C202D7",
  "TK_L1SUSHI": "0xA434947525699FfbbF74260947c2906831FafD98",
  "TK_L2SUSHI": "0x799F1f4045AFd00DFaE47Ab01Fb94AdB2f120B2C",
  "TK_L1LINK": "0x01BE23585060835E02B77ef475b0Cc51aA1e0709",
  "TK_L2LINK": "0x1cC8d6d2f14ac432605558A30461ebF501EaE427",
  "TK_L1UNI": "0x1f9840a85d5aF5bf1D1762F925BDADdC4201F984",
  "TK_L2UNI": "0x803Ec6089Ab7CC320840EDBd4bB99399467E57E0",
  "TK_L1OMG": "0x2B203de02AD6109521e09985b3aF9B8c62541Cd6",
  "TK_L2OMG": "0xC5086AA4BB6F18B3D966381E18Bcc317CeD9507c",
  "TK_L1FRAX": "0xa23A5D188C8E2f4b3E029815a793972C58D89890",
  "TK_L2FRAX": "0x6FF9c8FF8F0B6a0763a3030540c21aFC721A9148",
  "TK_L1FXS": "0xb1efaEC30db0da6CD2ADbDE71D82A73DcA6aF182",
  "TK_L2FXS": "0x991AaC49780774D1e358ceA459070f9351022139",
  "TK_L1BOBA": "0x6A6676813d3D4317442CF84667425C13553F4a76",
  "TK_L2BOBA": "0xF5B97a4860c1D81A1e915C40EcCB5E4a5E6b8309",
  "L1CrossDomainMessengerFast": "0x2f28C228C2d9C8dB957E3A842C34E1c3f03f38CB",
  "Proxy__L1CrossDomainMessengerFast": "0xe2a82CE9671A283190DD5E3f077027979F2c039E",
  "L2LiquidityPool": "0x58E48905AbFcBd6eDcb7D7b4fA07C66C5eE5Fe56",
  "L1LiquidityPool": "0xBce090E95cc724f3A4dC9c770d46AFF10f9E49d6",
  "Proxy__L1LiquidityPool": "0x12F8d1cD442cf1CF94417cE6309c6D2461Bd91a3",
  "Proxy__L2LiquidityPool": "0x56851CB42F315D0B90496c86E849167B8Cf7108a",
  "L2TokenPool": "0x0DC3084Fd6aabb0CA9EFD20BcC791D5e6820564d",
  "L1Message": "0xDCeDc3dD78F11acDD53F4a56e085E99FF7CD970a",
  "L2Message": "0x5D349Ca5F9C8E99a2E6d2DddC6b15736ad0A233a",
  "AtomicSwap": "0x903cABDe08F7765d201B470178e19ED1b4f48006",
  "L2ERC721": "0xEdf91A2fBB745e4651eb57659929813bC3C01f14",
  "L2ERC721Reg": "0xf296469f3303760D20197C2a2c9Ab2aDe02bfDEB",
  "L1NFTBridge": "0x48b66666E38c0C7b4b8F863D8caEf607262183Ac",
  "L2NFTBridge": "0x9b175c83d6238cB4a48E6f3C025D43E35b04391f",
  "Proxy__L1NFTBridge": "0x40394f7EAb5aeB995132ba3bd3e46035FB66143a",
  "Proxy__L2NFTBridge": "0x92a5dfc88F58A01fB4dBfDccE13368f9a0D418c5",
  "L1MultiMessageRelayerFast": "0xEe4A28080C7785A1F14Bc143A8083b2F02B94f88"
}
```
