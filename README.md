# crypto-ticker

> This is a fork of [robertcalvert/vscode-crypto-ticker](https://github.com/robertcalvert/vscode-crypto-ticker), I re-published it with some changes.

Please donate to the original author (robertcalvert):

[![Donate Bitcoin](https://img.shields.io/badge/donate-bitcoin-orange)](https://www.blockchain.com/btc/address/36gjpzeQtePfhU41VkM39XLUywpXVmtoKW)

Welcome to crypto-ticker, a Visual Studio Code extension that allows you to keep an eye on cryptocurrency prices as you code!

### Default Settings

The default settings provide a set of basic tickers for BTC, ETH and LTC. The current prices are displayed in USD with colors based on the 24HOUR period.

![Example](https://github.com/forewing/vscode-crypto-ticker/raw/main/images/default.png)

### Customization

This extension uses [cryptocompare.com](https://min-api.cryptocompare.com/documentation) to retrieve the current cryptocurrency prices. Please consult their documentation for a list of supported *symbols*, *currencies* and *exchanges*.

You can fully customize your tickers using the crypto-ticker extension settings.

```javascript
// Specify your CryptoCompare API key
"crypto-ticker.apiKey": "YOUR_API_KEY",

// Specify the refresh interval in seconds
"crypto-ticker.interval": 60,

// Specify the opening period
"crypto-ticker.period": "24HOUR",

// Customize your high and low colors to suite your status bar
"crypto-ticker.higherColor": "lightgreen",
"crypto-ticker.lowerColor": "coral",

// Customize your tickers
"crypto-ticker.tickers": [
    {
        // The base cryptocurrency symbol
        "symbol": "BTC",

        // The comparison currency symbol
        "currency": "EUR",

        // The cryptocurrency exchange
        "exchange": "LocalBitcoins",

        // Create a custom ticker template
        "template": "{symbol} {price} {percent}"
    },
    {
        // You can even compare cryptocurrencies
        "symbol": "ETH",
        "currency": "BTC"
    },
    {
        // Wow such coin, much riches
        "symbol": "DOGE"
    }
]
```

These example settings create the following tickers:

![Example](https://github.com/forewing/vscode-crypto-ticker/raw/main/images/custom.png)

### Template Tags

You can use tags within your ticker template to customize the output as needed.

```javascript
"template": "{symbol} {price}" // The default template
```

The following tags are available to use:

Tag | Description
------------ | -------------
symbol | The cryptocurrency symbol
price | The current cryptocurrency price
open | The opening price for the given period
high | The highest price since the period opened
low | The lowest price since the period opened
change | The difference between the opening price and current price
percent | The change as a percent

### Icon

Icon made by [Vectors Market](https://www.flaticon.com/authors/vectors-market) from www.flaticon.com

## License

[MIT](LICENSE.md)
