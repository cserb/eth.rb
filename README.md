<!--
# @markup markdown
# @title Ethereum for Ruby
# @author Afri Schoedon
-->

# Ethereum for Ruby

[![GitHub Workflow Status](https://img.shields.io/github/actions/workflow/status/q9f/eth.rb/spec.yml?branch=main)](https://github.com/q9f/eth.rb/actions)
[![GitHub release (latest by date)](https://img.shields.io/github/v/release/q9f/eth.rb)](https://github.com/q9f/eth.rb/releases)
[![Gem](https://img.shields.io/gem/v/eth)](https://rubygems.org/gems/eth)
[![Gem](https://img.shields.io/gem/dt/eth)](https://rubygems.org/gems/eth)
[![Visitors](https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fgithub.com%2Fq9f%2Feth.rb&count_bg=%2379C83D&title_bg=%23555555&icon=rubygems.svg&icon_color=%23FF0000&title=visitors&edge_flat=false)](https://hits.seeyoufarm.com)
[![codecov](https://codecov.io/gh/q9f/eth.rb/branch/main/graph/badge.svg?token=IK7USBPBZY)](https://codecov.io/gh/q9f/eth.rb)
[![Maintainability](https://api.codeclimate.com/v1/badges/469e6f66425198ad7614/maintainability)](https://codeclimate.com/github/q9f/eth.rb/maintainability)
[![Top Language](https://img.shields.io/github/languages/top/q9f/eth.rb?color=red)](https://github.com/q9f/eth.rb/pulse)
[![Yard Doc API](https://img.shields.io/badge/documentation-API-blue)](https://q9f.github.io/eth.rb)
[![Usage Wiki](https://img.shields.io/badge/usage-WIKI-blue)](https://github.com/q9f/eth.rb/wiki)
[![Open-Source License](https://img.shields.io/github/license/q9f/eth.rb)](LICENSE)
[![Contributions Welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat)](https://github.com/q9f/eth.rb/issues)

A straightforward library to build, sign, and broadcast Ethereum transactions. It allows the separation of key and node management. Sign transactions and handle keys anywhere you can run Ruby and broadcast transactions through any local or remote node. Sign messages and recover signatures for authentication.

What you get:
- [x] Secp256k1 Key-Pairs and Encrypted Ethereum Key-Stores (JSON)
- [x] EIP-20 Token Transfers (ERC20)
- [x] EIP-55 Checksummed Ethereum Addresses
- [x] EIP-137 Ethereum Domain Name Service (ENS)
- [x] EIP-155 Replay protection with Chain IDs (with presets)
- [x] EIP-191 Ethereum Signed Messages (with prefix and type)
- [x] EIP-712 Ethereum Signed Type Data
- [x] EIP-1271 Smart-Contract Authentification
- [x] EIP-1559 Ethereum Type-2 Transactions (with priority fee and max gas fee)
- [x] EIP-2028 Call-data intrinsic gas cost estimates (plus access lists)
- [x] EIP-2718 Ethereum Transaction Envelopes (and types)
- [x] EIP-2930 Ethereum Type-1 Transactions (with access lists)
- [x] ABI-Encoder and Decoder (including type parser)
- [x] RLP-Encoder and Decoder (including sedes)
- [x] RPC-Client (IPC/HTTP) for Execution-Layer APIs
- [x] Solidity bindings (compile contracts from Ruby)
- [x] Full smart-contract support (deploy, transact, and call)

## Installation
Add this line to your application's Gemfile:

```ruby
gem "eth"
```

Or install it yourself as:

```shell
gem install eth
```

## Usage
Check out the
[![Yard API Docs](https://img.shields.io/badge/documentation-API-blue)](https://q9f.github.io/eth.rb)
and the
[![Usage Wiki](https://img.shields.io/badge/usage-WIKI-blue)](https://github.com/q9f/eth.rb/wiki)
for all the details and example snippets.

## Documentation
The documentation can be found at: https://q9f.github.io/eth.rb

For any specific version, docs can be generated by `yard`:

```shell
gem install bundler rdoc yard
git checkout $VERSION
yard doc
```

The goal is to have 100% API documentation available.

## Testing
The test suite expects working local HTTP and IPC endpoints with a prefunded developer account, e.g.:

```shell
geth --dev --http --ipcpath /tmp/geth.ipc &
```

It also expects an `$DRPC_TOKEN` in environment to test some ENS queries on mainnet.

To run tests, simply use `rspec`. Note, that the Ethereum test fixtures are also required.

```shell
git submodule update --init --recursive
bundle install
rspec
```

The goal is to have 100% specification coverage for all code inside this gem.

## Contributing
Pull requests are welcome! To contribute, please consider the following:
* Code should be fully documented. Run `yard doc` and make sure it does not yield any warnings or undocumented sets.
* Code should be fully covered by tests. Run `rspec` to make sure all tests pass. The CI has an integration that will assis you to identify uncovered lines of code and get coverage up to 100%.
* Code should be formatted properly. Try to eliminate the most common issues such as trailing white-spaces or duplicate new-lines. Usage of the `rufo` gem is recommended.
* Submit pull requests, questions, or issues to Github: <https://github.com/q9f/eth.rb>

## License and Credits
The `eth` gem is licensed under the conditions of [Apache 2.0](./LICENSE.txt). Please see [AUTHORS](./AUTHORS.txt) for contributors and copyright notices.

This gem is a complete rewrite of the old `eth` gem by Steve Ellis.
* <https://github.com/se3000/ruby-eth> (MIT)

It is not only a rewrite of the `eth` gem but also a partial merge of the `ethereum` gem by Marek Kirejczyk and Yuta Kurotaki.
* <https://github.com/EthWorks/ethereum.rb> (MIT)

This gem also includes a revised version of the ABI gem by Jan Xie and Zhang Yaning.
* <https://github.com/cryptape/ruby-ethereum-abi> (MIT)

It also contains a condensed version of the RLP gem by Jan Xie and Zhang Yaning.
* <https://github.com/cryptape/ruby-rlp> (MIT)
