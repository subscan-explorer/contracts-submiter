#### Contract Verification
This project is primarily designed for validating contract information through Subscan. Once the verification is complete, a new release will be created, and the compiled *.contract file will be uploaded to this release.

### Usage
#### For New Repositories
* Click the `Use this template` button to create a new repository.
* Develop your contract and adjust the [subscan_contract_hash_submission.yaml](./subscan_contract_hash_submission.yaml) configuration file to suit your needs.
* Create a tag prefixed with `subscan-verify` and push it to your repository. GitHub Actions will then automatically execute and submit the contract information to Subscan.

#### For Existing Repositories
* Copy the following files or directories to your project:
  * [subscan_contract_hash_submission.yaml](./subscan_contract_hash_submission.yaml)
  * [.github](./.github)
* Create a tag prefixed with `subscan-verify` and push it to your repository. GitHub Actions will then automatically execute and submit the contract information to Subscan.

#### Local Execution
* Download [submit-contracts-hash](https://storage.googleapis.com/wasm-compile-artifacts.gcs.subscan.io/submit-contracts-hash/latest/submit-contracts-hash) (note that this only supports Linux amd64).
* Create a configuration file. You can use [subscan_contract_hash_submission.yaml](./subscan_contract_hash_submission.yaml) as a template and modify it according to your needs.
* Run `./submit-contracts-hash -config ./subscan_contract_hash_submission.yaml`. **Please be aware that this program requires Docker. If Docker is not installed on your machine, you should install it first.**

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
