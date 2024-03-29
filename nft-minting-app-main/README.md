# Welcome to The Balinese NFT 💎

![](https://github.com/thebalinese/nft-minting-app-main/blob/main/nft-minting-app-main/logo-blob.jpg)

All the code in these repos was created and explained by HashLips on the main YouTube channel.

To find out more please visit:

[📺 YouTube](https://youtube.com/channel/UCSJ9xFbqHDUQlV3kEUVTgpA)

[💬 Telegram](https://t.me/thebalinese)

[🐦 Twitter](https://twitter.com/thebalineseNFT)

[ℹ️ Website](https://www.thebalinese.my.id/)

# The Balinese NFT minting dapp 🔥

This repo provides a nice and easy way for linking an existing NFT smart contract to this minting dapp. There are two ways of using this repo, you can go the simple route or the more complex one.

The simple route is so simple, all you need to do is download the build folder on the release page and change the configuration to fit your needs. (Follow the video for a walk through).

The more complex route allows you to add additional functionality if you are comfortable with coding in react.js. (Follow the below instructions for a walk through).

## Installation 🛠️

If you are cloning the project then run this first, otherwise you can download the source code on the release page and skip this step.

```sh
git clone https://github.com/thebalinese/nft-minting-app-main.git
```

Make sure you have node.js installed so you can use npm, then run:

```sh
npm install
```

## Usage ℹ️

In order to make use of this dapp, all you need to do is change the configurations to point to your smart contract as well as update the images and theme file.

For the most part all the changes will be in the `public` folder.

To link up your existing smart contract, go to the `public/config/config.json` file and update the following fields to fit your smart contract, network and marketplace details. The cost field should be in wei.

Note: this dapp is designed to work with the intended NFT smart contract, that only takes one parameter in the mint function "mintAmount". But you can change that in the App.js file if you need to use a smart contract that takes 2 params.

```json
{
  "CONTRACT_ADDRESS": "0x3BE31328CB9A64FA50EE41B015D33a90549d1C06",
  "SCAN_LINK": "https://polygonscan.com/token/0x3be31328cb9a64fa50ee41b015d33a90549d1c06",
  "NETWORK": {
    "NAME": "Polygon",
    "SYMBOL": "WETH",
    "ID": 137
  },
  "NFT_NAME": "The Balinese NFTs Limited Edition",
  "SYMBOL": "BALI",
  "MAX_SUPPLY": 100,
  "WEI_COST": 7000000000000000,
  "DISPLAY_COST": 0.7,
  "GAS_LIMIT": 285000,
  "MARKETPLACE": "Opeansea",
  "MARKETPLACE_LINK": "https://opensea.io/collection/thebalinesenfts",
  "SHOW_BACKGROUND": true
}
```

Make sure you copy the contract ABI from remix and paste it in the `public/config/abi.json` file.
(follow the youtube video if you struggle with this part).

Now you will need to create and change 2 images and a gif in the `public/config/images` folder, `bg.png`, `example.gif` and `logo.png`.

Next change the theme colors to your liking in the `public/config/theme.css` file.

```css
:root {
  --primary: #ebc908;
  --primary-text: #1a1a1a;
  --secondary: #ff1dec;
  --secondary-text: #ffffff;
  --accent: #ffffff;
  --accent-text: #000000;
}
```

Now you will need to create and change the `public/favicon.ico`, `public/logo192.png`, and
`public/logo512.png` to your brand images.

Remember to update the title and description the `public/index.html` file

```html
<title>The Balinese NFT</title>
<meta name="description" content="Mint your The Balinese Binance NFT" />
```

Also remember to update the short_name and name fields in the `public/manifest.json` file

```json
{
  "short_name": "BALI",
  "name": "The Balinese NFTs Limited Edition"
}
```

After all the changes you can run.

```sh
npm run start
```

Or create the build if you are ready to deploy.

```sh
npm run build
```

Now you can host the contents of the build folder on a server.

That's it! you're done.
