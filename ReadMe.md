## video last 12:57.04s

 
## Install /chainlink-brownie-contracts:
```
forge install smartcontractkit/chainlink-brownie-contracts@1.2.0 --no-commit
```
in the foundry.toml add: 
`remappings = ['@chainlink/contracts=lib/chainlink-brownie-contracts/contracts']`

- Into the deploy script:
import{Script} from "forge-std/Script.sol"

- Deploy script: 
forge script script/DeployFund.s.sol

forge script script/DeployFundMe.s.sol --rpc-url http://127.0.0.1:8545

forge script script/DeployFundMe.s.sol --rpc-url http://127.0.0.1:8545 --broadcast --private-key 0xac0974bec39a17e36ba4a6b4d238ff944bacb478cbed5efcae784d7bf4f2ff80

- Convert hex to decimal:
cast --to-base 0x5FbDB2 dec

forge script script/DeployFundMe.s.sol --rpc-url $SEPOLIA_RPC_URL --private-key $PRIVATE_KEY --broadcast

forge fmt

## zksync deployment

1. install `foundry-zksync` from the resource in this linky
   https://github.com/matter-labs/foundry-zksync

   ```
   cd..
   ```
   ```
   git clone git@github.com:matter-labs/foundry-zksync.git
   ```

   ```
   cd foundry-zksync
   ```

   ```
   ./install-foundry-zksync
   ```

   ```
   forge --version
   ```


2. Compile with --zksync` 
   
   ```
   foundryup-zksync
   ```
   ```
   forge build --zksync
   ```

3. Reinstall vanilla foundry to continue working withot zksync
   `foundryup`

## Zksync Local Node

To deploy locally on a zkSync local chain, you'll need additional tools: 
1. **Docker**: Start the [Docker](https://www.docker.com/) dooemon
 `sudo systemctl start docker` and `sudo systemctl stop docker` will manage Docker lifecycles. Verify the installation with `docker --version` and `docker ps` commands.

2. **Node.js and npm**: Install [Node.js](https://nodejs.org/en) and [npm](https://www.npmjs.com/)
3.  **zksync-cli**: Once Docker and Node.js are installed, you can install the [zksync-cli](https://www.npmjs.com/package/zksync-cli) to manage your local zkSync development environment. Run `npx zksync-cli dev config` to set up your configuration. Choose the `in-memory` node option for a quick startup without persistent state and avoid additional options like a portal or block explorer unless you want to explore them independently.

npx zksync-cli dev config 
npx zksync-cli dev start

### Add helperConfig

- To test only one function, use the flag 
- `--mt`  //match test

### Interactions
`forge install Cyfrin/foundry-devops --no-commit
`
The import it into the interactions contract

import {DevOpsTools} from "foundry-devops/src/DevOpsTools.sol;

In foundry.toml, set
`ffi =true`
This allows foundry to run commands directly on your commandline

