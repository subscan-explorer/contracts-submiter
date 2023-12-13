#### Contract Verification
This project is primarily designed for the validation of contract information via Subscan.

### Usage
#### For New Repositories
* Click the `Use this template` button to create a new repository.
* Construct your contract and modify the [subscan_contract_hash_submission.yaml](./subscan_contract_hash_submission.yaml) configuration file according to your needs.
* Create and push a tag prefixed with `subscan-verify` to your repository. GitHub Actions will then automatically execute and submit the contract information to Subscan.

#### For Existing Repositories
* Copy the following files or directories to your project:
  * [subscan_contract_hash_submission.yaml](./subscan_contract_hash_submission.yaml)
  * [.github](./.github)
* Create and push a tag prefixed with `subscan-verify` to your repository. GitHub Actions will then automatically execute and submit the contract information to Subscan.

#### Local Execution
* Download [submit-contracts-hash](https://storage.googleapis.com/wasm-compile-artifacts.gcs.subscan.io/submit-contracts-hash/latest/submit-contracts-hash) (only supports Linux amd64).
* Create a configuration file. You can use the [subscan_contract_hash_submission.yaml](./subscan_contract_hash_submission.yaml) as a starting point and modify it according to your needs.
* Run `./submit-contracts-hash -config ./subscan_contract_hash_submission.yaml`. **Note that this program requires Docker. If Docker is not installed on your machine, please install it first.**

### Configuration
The default configuration file is [subscan_contract_hash_submission.yaml](./subscan_contract_hash_submission.yaml).

```yaml
# The working directory during compilation, default is "."
working_directory: .
# The relative path of Cargo.toml, relative to the working directory, default is "Cargo.toml"
manifest_path: Cargo.toml
# rustup toolchain version, default is "stable"
toolchain: stable
# The tag for https://github.com/paritytech/cargo-contract, default is "v2.2.1"
compiler_tag: v2.2.1
# Rust version, default is "1.68.0"
rust_version: 1.68.0
# The arguments for the compiler, default is "--release"
compiler_args: --release
```
