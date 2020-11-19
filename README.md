# cover-core-v1

## Contracts on Mainnet
* Protocol Factory: [0xedfC81Bf63527337cD2193925f9C0cF2D537AccA](https://etherscan.io/address/0xedfC81Bf63527337cD2193925f9C0cF2D537AccA#code)
* Protocol Implementation: [0xb6886B2C3537673941E4EAd63b95EaCb47173f6A](https://etherscan.io/address/0xb6886B2C3537673941E4EAd63b95EaCb47173f6A#code)
* Cover Implementation: [0xcB0900D9307Da7FD4e000A9093f24Ce25D937D42](https://etherscan.io/address/0xcB0900D9307Da7FD4e000A9093f24Ce25D937D42#code)
* covToken Implementation: [0xd18124029b167E03BBAaB8D5d6Fbb646aE020e1d](https://etherscan.io/address/0xd18124029b167E03BBAaB8D5d6Fbb646aE020e1d#code)
* ClaimManagement: [0xd33F2e0173Fd0aE2A64B208A7BD16bcdc68bC862](https://etherscan.io/address/0xd33F2e0173Fd0aE2A64B208A7BD16bcdc68bC862#code)

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
