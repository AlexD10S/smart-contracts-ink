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

To deploy lthe SCs locally, move to substrate-node-template and run:
```shell
substrate-contracts-node --dev
```
Then deploy them using the Contracts UI from Substrate: https://contracts-ui.substrate.io/ uploading the .contract file generated after the build.
