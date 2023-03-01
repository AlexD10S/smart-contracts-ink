# ink! Smart Contracts
Repository for learning purposes following the Substrate tutorial: https://docs.substrate.io/tutorials/smart-contracts to develop Smart Contracts using the ink! language.

Move to the folder of the Smart contract you want to test.
Run the tests:
```shell
cargo +nightly test
```

Build the WebAssembly for the contract:
```shell
cargo +nightly contract build
```

To deploy lthe SCs locally,  download a precompiled Substrate Contracts Node:
```shell
cargo install contracts-node --git https://github.com/paritytech/substrate-contracts-node.git --tag <latest-tag> --force --locked
```

And run:
```shell
substrate-contracts-node --dev
```
Then deploy them using the Contracts UI from Substrate: https://contracts-ui.substrate.io/ uploading the .contract file generated after the build.

Deploy the contract with CLI:
```shell
cargo contract instantiate --constructor new --args "false" --suri //Alice --salt $(date +%s)
```

Interact with the SC using cargo-contract
Example:
```shell
cargo contract call --contract SC-ADDRESS --message flip --suri //Alice 
cargo contract call --contract SC-ADDRESS --message get --suri //Alice --dry-run
```

### Troubleshooting
```error
ERROR: cargo-contract cannot build using the "stable" channel. Switch to nightly. See https://github.com/paritytech/cargo-contract#build-requires-the-nightly-toolchain
```

Run
```shell
rustup default nightly
```

### TODO
- Cross_contract_flipper has no unit test (not support yet), check:
https://substrate.stackexchange.com/questions/28/how-to-test-cross-contract-ink-contracts