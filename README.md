#### Contract Verification
This project is primarily designed for validating contract information with Subscan.

### Usage
#### New Repository
* Click the `Use this template` button to create a new repository.
* Construct your own contract and modify the [subscan_contract_hash_submission.yaml](./subscan_contract_hash_submission.yaml) configuration according to your requirements.
* Create a tag and push it to your repository, subsequently, the GitHub action will automatically operate and submit the contract information to Subscan.

#### Existing Repository
* Copy the following files or directories to your project,
    * [subscan_contract_hash_submission.yaml](./subscan_contract_hash_submission.yaml)
    * [.github](./.github)
* Whenever a new tag is associated with your project, GitHub action will automatically operate and submit the contract information to Subscan.

### Configuration
Default configuration file [subscan_contract_hash_submission.yaml](./subscan_contract_hash_submission.yaml)

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
