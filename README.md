Gnosis Safe Tasks for KalyChain
=================

Install
-------
Set correct node version (see `.nvmrc`) with [nvm](https://github.com/nvm-sh/nvm)
```bash
nvm use
```

Install requirements with yarn:
```bash
yarn
```

Quick Start
-----------
### Setup

Create `.env` file to use the commands (see `.env.sample` for more info):

- `NETWORK` - Network that should be used (e.g. `rinkeby`, `mainnet` or `custom`)
- `PK` - Credentials for the account that should be used
- `NODE`- RPC node for `custom` network (optional)

### Help

Use `yarn safe help <command>` to get more information about parameters of a command.

Example:
```bash
yarn safe help create
```

### Create Safe
Creates and setups a Safe proxy via the proxy factory. All parameters of the Safe `setup` method can be configured.

#### Example
This will deploy a Safe that uses the first imported account as an owner and set the threshold to 1.
```bash
yarn safe create --network custom --singleton "<YOUR-GnosisSafeL2-ADDRESS-HERE>" --factory "<YOUR-GnosisSafeProxyFactory-ADDRESS-HERE>"

```

### Safe Info
Displays information about a Safe

#### Usage
```bash
yarn safe info <address>
```

### Propose Safe Transaction
Creates a proposal json file for a Safe transaction that can be shared. The name of the json file will be `<safe_tx_hash>.proposal.json` and it will be stored in the `cli_cache` folder.

#### Examples
This will create a transaction from the Safe to the target without any value or data.
```bash
yarn safe propose <address> --to <target>
```

This will create a transaction based on the sample tx input json that mints some WETH and sets an approve for it.
```bash
yarn safe propose-multi <address> tx_input.sample.json
```

### Show Proposal
Shows the information of the proposal. 
Note: This requires the proposal file created before for that Safe transaction in the `cli_cache`.

#### Usage
```bash
yarn safe show-proposal <safeTxHash>
```

### Sign Proposal
Signs a proposal with the imported account
Note: This requires the proposal file created before for that Safe transaction in the `cli_cache`.

#### Usage
```bash
yarn safe sign-proposal <safeTxHash>
```

### Submit Proposal
Submits a proposal with the imported account
Note: This requires the proposal file created before for that Safe transaction in the `cli_cache`.

#### Usage
```bash
yarn safe submit-proposal <safeTxHash>
```

### Show Transaction History
Displays the transaction history of a Safe based on events

#### Usage
```bash
yarn safe history <address>
```
KalyChain Deployments
-----------
### Testnet

Create2 Deployer: [0x4e59b44847b379578588920ca78fbf26c0b4956c](https://testnet.kalyscan.io/address/0x4e59b44847b379578588920ca78fbf26c0b4956c)
SimulateTxAccessor: [0x59AD6735bCd8152B84860Cb256dD9e96b85F69Da](https://testnet.kalyscan.io/address/0x59AD6735bCd8152B84860Cb256dD9e96b85F69Da)
GnosisSafeProxyFactory: [0xa6B71E26C5e0845f74c812102Ca7114b6a896AB2](https://testnet.kalyscan.io/address/0xa6B71E26C5e0845f74c812102Ca7114b6a896AB2) 
DefaultCallbackHandler: [0x1AC114C2099aFAf5261731655Dc6c306bFcd4Dbd](https://testnet.kalyscan.io/address/0x1AC114C2099aFAf5261731655Dc6c306bFcd4Dbd)
CompatibilityFallbackHandler: [0xf48f2B2d2a534e402487b3ee7C18c33Aec0Fe5e4](https://testnet.kalyscan.io/address/0xf48f2B2d2a534e402487b3ee7C18c33Aec0Fe5e4) 
CreateCall: [0x7cbB62EaA69F79e6873cD1ecB2392971036cFAa4](https://testnet.kalyscan.io/address/0x7cbB62EaA69F79e6873cD1ecB2392971036cFAa4)
MultiSend: [0xA238CBeb142c10Ef7Ad8442C6D1f9E89e07e7761](https://testnet.kalyscan.io/address/0xA238CBeb142c10Ef7Ad8442C6D1f9E89e07e7761)
MultiSendCallOnly: [0x40A2aCCbd92BCA938b02010E17A5b8929b49130D](https://testnet.kalyscan.io/address/0x40A2aCCbd92BCA938b02010E17A5b8929b49130D)
GnosisSafeL2: [0x3E5c63644E683549055b9Be8653de26E0B4CD36E](https://testnet.kalyscan.io/address/0x3E5c63644E683549055b9Be8653de26E0B4CD36E)
GnosisSafe: [0xd9Db270c1B5E3Bd161E8c8503c55cEABeE709552](https://testnet.kalyscan.io/address/0xd9Db270c1B5E3Bd161E8c8503c55cEABeE709552)

Security and Liability
----------------------
All contracts are WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.

License
-------
All smart contracts are released under LGPL-3.0

