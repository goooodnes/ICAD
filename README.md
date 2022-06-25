## ICAD kqcosmos-1 keplr wallet integration
<!--
#### Requirements 
[keplr wallet extension](https://google.com)
-->
### Auto installation
1) Just visit this link. Once the keplr window popup press the approve button.  
2) In the network section choose ICAD network  
3) That's it. Have fun:)  

### Manual installation

Open the developer console:

- Chromium based browsers: View> Developer>Developer Tools(ctrl-shift-j)

- Copy paste the code and press enter. Do not forget to edit rpc and rest api urls in the code! :


```markdown
await window.keplr.experimentalSuggestChain({
    chainId: "kqcosmos-1",
    chainName: "ICAD",
    rpc: "http://162.55.235.69:2865", // replace with your rpc url
    rest: "http://162.55.235.69:1387", // replace with your rest api url
    bip44: {
        coinType: 118,
    },
    bech32Config: {
        bech32PrefixAccAddr: "cosmos",
        bech32PrefixAccPub: "cosmos" + "pub",
        bech32PrefixValAddr: "cosmos" + "valoper",
        bech32PrefixValPub: "cosmos" + "valoperpub",
        bech32PrefixConsAddr: "cosmos" + "valcons",
        bech32PrefixConsPub: "cosmos" + "valconspub",
    },
    currencies: [ 
        { 
            coinDenom: "ATOM", 
            coinMinimalDenom: "uatom", 
            coinDecimals: 6, 
            coinGeckoId: "uatom", 
        }, 
    ],
    feeCurrencies: [
        {
            coinDenom: "ATOM",
            coinMinimalDenom: "uatom",
            coinDecimals: 6,
            coinGeckoId: "uatom",
        },
    ],
    stakeCurrency: {
        coinDenom: "ATOM",
        coinMinimalDenom: "uatom",
        coinDecimals: 6,
        coinGeckoId: "uatom",
    },
    coinType: 118,
    gasPriceStep: {
        low: 0.01,
        average: 0.025,
        high: 0.03,
    },
    
    features: [
        "cosmwasm", "ibc-transfer", "ibc-go", "wasmd_0.24+"
        ],
});
}
```
