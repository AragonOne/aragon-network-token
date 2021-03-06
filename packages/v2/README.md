# Aragon Network Token V2

[![Build Status](https://img.shields.io/github/workflow/status/aragon/aragon-network-token/ci:v2?style=flat-square)](https://github.com/aragon/aragon-network-token/actions?query=workflow%3Aci%3Av2)

A lightweight token supporting [ERC-2612](https://eips.ethereum.org/EIPS/eip-2612), [ERC-3009](https://eips.ethereum.org/EIPS/eip-3009), token mints, and token burns. Modelled after [UNI-LP](https://github.com/Uniswap/uniswap-v2-core/blob/v1.0.1/contracts/UniswapV2ERC20.sol) with minimal changes.

## Status

This package is in _preservation_ mode.

ANTv2 was deployed in October 2020.

## Development

```sh
yarn install
yarn test
```

This will compile the mocks in [`mocks/`](mocks/) and run the [unit tests](test/).

CI for this package is run through the [`ci_v2` Github action](../../.github/workflows/ci_v2.yml).

### Code style

To limit changes, [`ANTv2.sol`](contracts/ANTv2.sol) carries over the code style of the original `UNI-LP` codebase.

All other contracts use the typical Aragon code style.

## E2E tests

[E2E tests](e2e) are performed through a Ganache-based fork of mainnet state. To run them:

```sh
FORK_NODE=<URL of mainnet RPC> yarn test:e2e:pre-deploy
FORK_NODE=<URL of mainnet RPC> yarn test:e2e:post-deploy
```

### Pre-deploy

Tests a theoretical `ANTv2` and `ANTv2Migrator` deployment with mainnet's ANTv1.

See [the `buidler.config.e2e-pre.js` configuration](buidler.config.e2e.js) for more information about the fork's configuration.

### Post-deploy

Tests a deployed instance of `ANTv2` and `ANTv2Migrator` on mainnet with mainnet's ANTv1.

See [the `buidler.config.e2e-post.js` configuration](buidler.config.e2e.js) for more information about the fork's configuration.


### Rinkeby Network Addresses

* **ANTv1:** [0x59f24735b61e6ef7E5A52F5F7bB708D1c0141C5A](https://rinkeby.etherscan.io/address/0x59f24735b61e6ef7e5a52f5f7bb708d1c0141c5a)
* **ANTv2:** [0xf0f8D83CdaB2F9514bEf0319F1b434267be36B5c](https://rinkeby.etherscan.io/address/0xf0f8d83cdab2f9514bef0319f1b434267be36b5c)
* **ANJ:** [0x96286BbCac30Cef8dCB99593d0e28Fabe95F3572](https://rinkeby.etherscan.io/address/0x96286BbCac30Cef8dCB99593d0e28Fabe95F3572)
* **ANTv2Migrator:** [0xF45C53D13bF1F5f757E3331e258589a6f30e662F](https://rinkeby.etherscan.io/address/0xF45C53D13bF1F5f757E3331e258589a6f30e662F)
* **ANJNoLockMinter:** [0xEE25745890bc04bCF926436Ef3Ce490089d89F05](https://rinkeby.etherscan.io/address/0xEE25745890bc04bCF926436Ef3Ce490089d89F05)
* **ANJLockMinter:** [0x8A3475C25452B280a3Af1A8a9B4440e9f70f2f30](https://rinkeby.etherscan.io/address/0x8A3475C25452B280a3Af1A8a9B4440e9f70f2f30)
* **ANTv2MultiMinter**: [0xF64bf861b8A85927FAdd9724E80C2987f82a9259](https://rinkeby.etherscan.io/address/0xF64bf861b8A85927FAdd9724E80C2987f82a9259)

**Deployed By** : 0x94C34FB5025e054B24398220CBDaBE901bd8eE5e (Giorgi Lagidze)

### Mainnet Network Addresses

* **ANTv1:** [0x960b236A07cf122663c4303350609A66A7B288C0](https://etherscan.io/address/0x960b236a07cf122663c4303350609a66a7b288c0)
* **ANTv2:** [0xa117000000f279D81A1D3cc75430fAA017FA5A2e](https://etherscan.io/address/0xa117000000f279D81A1D3cc75430fAA017FA5A2e)
* **ANJ:** [0xcD62b1C403fa761BAadFC74C525ce2B51780b184](https://etherscan.io/address/0xcD62b1C403fa761BAadFC74C525ce2B51780b184)
* **ANTv2Migrator:** [0x078BEbC744B819657e1927bF41aB8C74cBBF912D](https://etherscan.io/address/0x078BEbC744B819657e1927bF41aB8C74cBBF912D)
* **ANJNoLockMinter:** [0xf6271c8eBF1C1C0384CBBD6Df8b84380623555Ef](https://etherscan.io/address/0xf6271c8eBF1C1C0384CBBD6Df8b84380623555Ef)
* **ANJLockMinter:** [0xAb788183FfAD7D3fAa54Cfc1f9EEf7ff981F4cfD](https://etherscan.io/address/0xab788183ffad7d3faa54cfc1f9eef7ff981f4cfd)
* **ANTv2MultiMinter**: [0xdFf202A4238458bF49A1eeE7Bc5582A45bbe0e38](https://etherscan.io/address/0xdFf202A4238458bF49A1eeE7Bc5582A45bbe0e38)

**Deployed By** : 0x9416C2191B49bC4E1E614f7d63035b294Ad30D19 (Sam Furter)


* ANTv2's minter can only be changed by ANTv2MultiMinter.
* ANJNoLockMinter is added as one of the minters in ANTv2MultiMinter.


## Credits

- UNI-LP: Uniswap
- SafeMath: DappHub



1. containerHash => 