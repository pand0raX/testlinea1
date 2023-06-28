# testlinea1

EVM-based Chains
The source data is in _data/chains. Each chain has its own file with the filename being the CAIP-2 representation as name and .json ans extension.

Example
{
  "name": "Ethereum Mainnet",
  "chain": "ETH",
  "rpc": [
    "https://mainnet.infura.io/v3/${INFURA_API_KEY}",
    "https://api.mycryptoapi.com/eth"
  ],
  "faucets": [],
  "nativeCurrency": {
    "name": "Ether",
    "symbol": "ETH",
    "decimals": 18
  },
  "features": [{ "name": "EIP155" }, { "name": "EIP1559" }],
  "infoURL": "https://ethereum.org",
  "shortName": "eth",
  "chainId": 1,
  "networkId": 1,
  "icon": "ethereum",
  "explorers": [{
    "name": "etherscan",
    "url": "https://etherscan.io",
    "icon": "etherscan",
    "standard": "EIP3091"
  }]
}
when an icon is used in either the network or a explorer there must be a json in _data/icons with the name used (e.g. in the above example there must be a ethereum.json and a etherscan.json in there) - the icon jsons look like this:

[
    {
      "url": "ipfs://QmdwQDr6vmBtXmK2TmknkEuZNoaDqTasFdZdu3DRw8b2wt",
      "width": 1000,
      "height": 1628,
      "format": "png"
    }
]
where:

the URL must be a IPFS url that is publicly resolveable
width and height are positive integers
format is either "png", "jpg" or "svg"
If the chain is an L2 or a shard of another chain you can link it to the parent chain like this:

{
  ...
  "parent": {
   "type" : "L2",
   "chain": "eip155-1",
   "bridges": [ {"url":"https://bridge.arbitrum.io"} ]
  }
}
