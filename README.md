## Full stack NFT Metaverse Marketplace for Hackisitica'22 
Technologies used- Polygon, Solidity, IPFS, & Next.js

Video for the project:
https://youtu.be/vgSuUlOK5YM

![Header](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/pfofv47dooojerkmfgr4.png)

### Running this project

#### Local setup

To run this project locally, follow these steps.

1. Clone the project locally, change into the directory, and install the dependencies:

```sh
git clone https://github.com/dabit3/polygon-ethereum-nextjs-marketplace.git

cd polygon-ethereum-nextjs-marketplace

# install using NPM or Yarn
npm install

# or

yarn
```

2. Start the local Hardhat node

```sh
npx hardhat node
```

3. With the network running, deploy the contracts to the local network in a separate terminal window

```sh
npx hardhat run scripts/deploy.js --network localhost
```

4. Start the app

```
npm run dev
```

### Configuration

To deploy to Polygon test or main networks, update the configurations located in __hardhat.config.js__ to use a private key and, optionally, deploy to a private RPC like Alchemy.

```javascript
require("@nomiclabs/hardhat-waffle");

/**
 * @type import('hardhat/config').HardhatUserConfig
 */

// require("dotenv").config();
require("@nomiclabs/hardhat-ethers");

// const { API_URL, PRIVATE_KEY } = process.env;
const API_URL =
  "https://polygon-mumbai.g.alchemy.com/v2/8SaUxkAflwvV4i4GqzW5n-6tO7pxfGZP";
const PRIVATE_KEY =
  "2da7a4ec24e5c78199fb58397bb288558fae8167396db1e6381b80bb5b7a449a";
module.exports = {
  solidity: "0.8.4",
  defaultNetwork: "polygon_mumbai",
  networks: {
    hardhat: {},
    polygon_mumbai: {
      url: API_URL,
      accounts: [`0x${PRIVATE_KEY}`],
    },
  },
};

Tpo deploy on polygon through alchemy use this.
