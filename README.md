# `neutron-1` Chain Details

The `neutron-1` chain will be launched as a consumer chain with Cosmos Hub network as provider chain.

* **Chain-ID**: `neutron-1`
* **denom**: `untrn`
* **minimum-gas-prices**: `0untrn`
* **timeout_commit**: `1s`
* **Spawn time**: `2023-05-08T11:00:00Z`
* **GitHub repo**: [neutron-org/neutron](https://github.com/neutron-org/neutron.git)
* **Release**: [`v1.0.0`](https://github.com/neutron-org/neutron/releases/tag/v1.0.0)
* **Genesis file with CCV state:** [neutron-1-genesis.json](neutron-1-genesis.json)

* **Reference binary**: [neutrond-linux-amd64](./neutrond-linux-amd64)
* **Binary sha256sum**: `82b608543f2989c7c631d555767800e48f54ede389d193913136b41e5c3293ab`
* **Pre genesis file published with proposal _without CCV state_:** [neutron-1-pre-genesis-without-ccv.json](./neutron-1-pre-genesis-without-ccv.json), verify with `shasum -a 256 neutron-1-pre-genesis-without-ccv.json`
* **SHA256 for pre genesis from proposal file _without CCV state_**: `4d897938a69a3809828e70f34c7400ec134817fe34ca4090dbe5991d72fa744c`

* **Final genesis file _without CCV state_:** [neutron-1-pre-genesis-final-without-ccv.json](./neutron-1-pre-genesis-final-without-ccv.json), verify with `shasum -a 256 neutron-1-pre-genesis-final-without-ccv.json.json`
* **SHA256 for final genesis file _without CCV state_**: `4d897938a69a3809828e70f34c7400ec134817fe34ca4090dbe5991d72fa744c`


* Genesis file hash
  * The SHA256 is used to verify against the genesis file (without CCV state) that the proposer has made available for review;
  * The `neutron-1-pre-genesis-without-ccv.json` file **cannot be used** to run the chain. Current pre genesis published in the proposal will not be used to generate final genesis, because of different configuration changes that was not available during proposal submission;
  * The `neutron-1-pre-genesis-final-without-ccv.json` file cannot be used to run the chain: it must be updated with the CCV (Cross Chain Validation) state after the spawn time is reached;
  * The genesis file includes following slashing parameters, `signed_blocks_window` has been set to `140000`, and `min_signed_per_window` has been set to `5%`;
* Binary hash
  * The `neutrond-linux-amd64` binary is only provided to verify the SHA256. It was built with Interchain Security release [`v1.0.0`](https://github.com/neutron-org/neutron/releases/tag/v1.0.0). You can generate the binary following the build instructions in that repo.
* Spawn time
  * Even if a proposal passes, the CCV state will not be available from the provider chain until after the spawn time is reached.

> Since [**Prop 792**](https://www.mintscan.io/cosmos/proposals/792) was published, Neutron released a new version, v1.0.0, which is going to be used for the mainnet launch. The only difference between v1.0.0-rc1, which was used in the proposal, and v1.0.0 is the upgrade of Interchain Security to the latest release, v1.2.1:
>
> https://github.com/octocat/linguist/compare/v1.0.0-rc1..v1.0.0
>
>**All validators are required to use v1.0.0 during the mainnet launch. The instructions on how to bulid v1.0.0 can be found in the [How to Join](#how-to-join) section.**

> If you want to build genesis by your own please take into account difference between the `ccvconsumer` section generated by version v9.0.3 of `gaiad` and the `ccvconsumer` section required for neutron to run. Please check and add `"soft_opt_out_threshold": "0.05"` to the `params` section if it absent.

For more information regarding the consumer chain creation process, see [CCV: Overview and Basic Concepts](https://github.com/cosmos/ibc/blob/main/spec/app/ics-028-cross-chain-validation/overview_and_basic_concepts.md).

## Endpoints

Seed nodes:

1. `e2c07e8e6e808fb36cca0fc580e31216772841df@p2p-erheim.neutron-1.neutron.org:26656`

Persistent nodes:

**TBA**

The following state sync node serve snapshots every 1000 blocks:

**TBA**

## How to Join

### Hardware Requirements

* 4 Cores
* 32 GB RAM
* 2x512 GB SSD

### Software Versions

| Name               | Version  |
|--------------------|----------|
| Neutron            | v1.0.0   |
| Go                 | >1.20    |


### Node manual installation

Build and install neutron binary. 

```
$ git clone -b v1.0.0 https://github.com/neutron-org/neutron.git
$ cd neutron
$ make install
```

after installation please check installed version by running:

`neutrond version --long`

You should see the following:
```
name: neutron
server_name: neutrond
version: 1.0.0 
commit: 2a9333c935b321cfa2cf213fb9adb38661d7f349

``` 

or you can download binary directly from our [official release](https://github.com/neutron-org/neutron/releases/tag/v1.0.0).