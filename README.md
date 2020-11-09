# cover-core-v1

## Contracts on Mainnet
* Protocol Factory: [0x45D619A4804B82c3af4c24Ccb460068a8A0D8D6a](https://etherscan.io/address/0x45D619A4804B82c3af4c24Ccb460068a8A0D8D6a#code)
* Protocol Implementation: [0xcC3B67F3AC058E376E839567a3B6e9f0D62Df74D](https://etherscan.io/address/0xcC3B67F3AC058E376E839567a3B6e9f0D62Df74D#code)
* Cover Implementation: [0x1349c51B28772F725e193c21597C0a41A715D504](https://etherscan.io/address/0x1349c51B28772F725e193c21597C0a41A715D504#code)
* covToken Implementation: [0xD84FDb46420a21dF9d4C14f6dD0c5881Ca052942](https://etherscan.io/address/0xD84FDb46420a21dF9d4C14f6dD0c5881Ca052942#code)
* ClaimManagement: [0xF52B078B3Db7e2253a803f09F1a2EEE0412c9aC2](https://etherscan.io/address/0xF52B078B3Db7e2253a803f09F1a2EEE0412c9aC2#code)

## Design
![cover core design](https://github.com/COVERProtocol/cover-core-v1/blob/main/cover_core_v1_design.jpg)

## Developement
* `npm install` install dependencies
* `npx hardhat compile` compile

### Run Test With in-process hardhat
* `npx hardhat test` run tests in a new terminal.

### Run Test With hardhat EVM (as [an independent node](https://hardhat.dev/hardhat-evm/#connecting-to-hardhat-evm-from-wallets-and-other-software))
* Run `npx hardhat node` to setup a local blockchain emulator in one terminal.
* `npx hardhat test --network localhost` run tests in a new terminal.
 **`npx hardhat node` restart required after full test run.** As the blockchain timestamp has changed.


### Run Tests With Ganache VM
* Install `npm install -g ganache-cli` if not already. See [details](https://docs.nethereum.com/en/latest/ethereum-and-clients/ganache-cli/).
* Run `ganache-cli` to setup a local blockchain emulator.
* `npx hardhat test --network localhost` run tests in a new terminal.

### Deploy to Your Local Hardhat Node
* Add required env vars into your `./.env` file. Set `COVER_TEST_ADDRESS` to the address your want to use as treasury and governance
* Run `npx hardhat run scripts/frontend-testing.js --network localhost`
