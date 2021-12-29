# Adding new Defi project
The JSON schema for Defi project includes: name, logoURI, homepage, CoinMarketCap ID, url, poolAddresses.

Follow the steps below to add a new token：
1) Fork this repo.
2) change the JSON file `defiProjectList.json`, adding such as: (PLEASE DO NOT REMOVE EXISITING PROJECTS)
```
{
    "name": "SunSwap",
    "logoURI": "https://coin.top/production/upload/logo/sun10.png",
    "homepage": "http://sun.io/",
    "CoinMarketCapID": "10529",
    "url": "https://apilist.tronscan.org/api/tvl",
    "category": "DEX",
    "poolAddresses": [
        "TKcEU8ekq2ZoFzLSGFYCUY6aocJBX9X31b",
        "TAkrcKsS5FW9f3ZfzvWy6Zvsz9uEjUxPoV"
    ]
}
```
* `CoinMarketCapID`: so your TVL can appear on Coinmarketcap. Find your ID through (https://api.coinmarketcap.com/data-api/v3/map/all?listing_status=active,inactive,untracked&start=1&limit=10000).

* `url`: the url result should be JSON format:
```
{
    "tvl": 3298643126.37
}
```
where `3298643126.37` unit is `$` (dollar), is `tokenAmount * currentTokenPrice`.

* `category`: (Yield/DEX/Lending/Minting/Assets/Insurance/Options/Indexes/Staking) Please choose only one.

* `poolAddresses`: the pool contract addresses related with this Defi project.

3) Submit PR with the changed JSON file.

Follow the PR template below:
```
## **Please provide the following information for your Defi project.**
Please include change to the `defiProjectList.json` file in the PR.
DON'T modify any other project on the list.

##### Twitter Link:
https://twitter.com/defi_sunio

##### List of audit links if any:
https://sun.io/docs/slowmist_audit_report_cn_sun.pdf

##### Homepage:
http://sun.io/

##### Logo (High resolution, preferably in .svg and .png, for application on both white and black backgrounds. Will be shown with rounded borders):
https://coin.top/production/upload/logo/sun10.png

#### URL to get TVL:
https://apilist.tronscan.org/api/tvl

##### Current TVL:
$3298643126.37

##### CoinMarketCap ID (so your TVL can appear on Coinmarketcap): (https://api.coinmarketcap.com/data-api/v3/map/all?listing_status=active,inactive,untracked&start=1&limit=10000)
10529

##### Short Description:
SUN is first integrated platform for stablecoin swap, stake-mining and self-governance on TRON.

##### Token address and ticker if any:
TSSMHYeV2uE9qYH95DqyoCuNCzEL1NvU3S

##### Pool addresses:
TKcEU8ekq2ZoFzLSGFYCUY6aocJBX9X31b, TAkrcKsS5FW9f3ZfzvWy6Zvsz9uEjUxPoV.

##### Category (Yield/DEX/Lending/Minting/Assets/Insurance/Options/Indexes/Staking) *Please choose only one:
DEX

##### Oracle used (WINkLink/Chainlink/Band/API3/TWAP or any other that you are using):
WINkLink

##### forkedFrom (Does your project originate from another project):

##### methodology (what is being counted as tvl, how is tvl being calculated):
All tokens staked in the pool MINUS borrowed assets are counted as TVL. Borrowed assets are not included in the TVL.

```
