# cover-core-v1
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

## Deploy to Your Local Hardhat Node
* Add required env vars into your `./.env` file. Set `COVER_TEST_ADDRESS` to the address your want to use as treasury and governance
* Run `npx hardhat run scripts/frontend-testing.js --network localhost`
