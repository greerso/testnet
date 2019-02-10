# Gangnam testnet

[![Join the chat at https://gitter.im/ifdefelse/community](https://badges.gitter.im/ifdefelse/community.svg)](https://gitter.im/ifdefelse/community?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

The `--gangnam` testnet configurations

## Meta data: Gangnam

- Name: Gangnam
- Machine-readable name: `gangnam`
- Stage: _launched_
  - Genesis hash: `0x9a2a80100a4362bbf61d9c20c0fd6af6e3bc276c4d083e1547b35d89a4bfe7e4`
  - Network ID: `43568`
  - Chain ID: `43568`
  - Homestead: `1`
  - EIP150: `2`
  - EIP155: `3`
  - EIP158: `3`
  - Byzantium: `4`
  - Constantinople: `500`
  - ProgPoW: `3000`
- Status Dashboard: http://boot.gangnam.ethdevops.io/
- Block Explorer: https://gangnam.etherchain.org/
- Mining Pool: https://gangnam.wattpool.net/
- Gitter Support: https://gitter.im/ifdefelse/community/

Please see [gangnam-geth.json](gangnam-geth.json) for a genesis file compatible with Geth

Please see [gangnam-parity.json](gangnam-parity.json) for a genesis file compatible with Parity

Please see [bootnodes.txt](bootnodes.txt) to add peers.

## Connecting the clients

All clients supporting the ProgPoW v0.9.2 algorithm (EIP-1057) can sync with Gangnam Testnet.

#### Ethereum ProgPoW (Recommended)

Install Golang 1.10 & required compile tools and clone the repo, compile Ethereum ProgPoW node client.

```
sudo apt-get install -y golang-1.10 build-essential
sudo ln -s /usr/lib/go-1.10/bin/go /usr/bin/go
git clone https://github.com/ethereumprogpow/ethereumprogpow
cd ethereumprogpow
make geth
./build/bin/geth --gangnam
```

#### Parity ProgPoW (Recommended)

Install Rust & required compile tools and clone the repo, compile Parity ProgPoW node client.

```
sudo apt-get install -y build-essential gcc g++ libudev-dev pkg-config file make cmake
curl https://sh.rustup.rs -sSf | sh -s -- -y
source $HOME/.cargo/env
git clone https://github.com/ethereumprogpow/parity-progpow
cd parity-progpow
cargo build --release --features final
./target/release/parity --chain=gangnam
```

#### Go-Ethereum (work in progress)

ProgPoW support in Go-ethereum is still work in progress, but syncing the chain and all other Go-Ethereum features are available: [go-ethereum/#17731](https://github.com/ethereum/go-ethereum/pull/17731)

```
sudo apt-get install -y golang-1.10 build-essential
sudo ln -s /usr/lib/go-1.10/bin/go /usr/bin/go
git clone -b progpow https://github.com/holiman/go-ethereum
cd go-ethereum
make geth
./build/bin/geth --datadir gangnam init genesis
./build/bin/geth --datadir gangnam --networkid 43568 --bootnodes="enode://b89f336bfe23e24f13590f4d0e1249281d4ffb1a92a5337151a6592db841980cd6756b29f22fbf1990ac8a09ed4662f46a9745d820c6524b6365099d16772603@5.45.85.1:30303",
"enode://0a3fe912cfc1de4f23cf7f30f9bda221c8b6ee3214e496bd2895739642d7b0e7b8440896cb789ac239ea67f52de18e1b78940c7808f5ace3f25a6c4edf30405c@46.228.240.23:30303",
"enode://a45d27f2d627eeb71deec6cfecd8e0d87873e5529d3165f984c420f862ecb1be4f2dd483cb82a74822dd40206e73cb7bbbc27d74c38860105f516a5fa293265c@35.240.35.207:30303",
"enode://e61e62f45eb1fc99410cd717143321351e8ab8b4046c0b853c3f1c307c15b454e4e39c32bd08335ac48f74970f118a6c9f30d420d936f36bc5a449ebe45076a1@74.108.57.80:30303",
"enode://d470c8590de9fa487d1a4df777e5640cdb34c11ab41a1f1020a0f49243a101206d94faf04fa6ca28a11c3f4b042348c483f486cd5ae6210d82f5864d78b39435@35.240.35.207:30303",
"enode://4d7719eaa978e3d1ebc953fcfac83adf18f2642782de383d4a4c61f6f2a4d1492ae68c456d9bc7f41089f68cada1a586534c91941232760ef56b2ce33a3094d3@35.204.138.0:30303",
```

#### Parity-Ethereum (work in progress)

ProgPoW support in Parity-Ethereum is still work in progress, but syncing the chain and all other Parity-Ethereum features are available: [parity-ethereum/#9762](https://github.com/paritytech/parity-ethereum/pull/9762)

```
sudo apt-get install -y build-essential gcc g++ libudev-dev pkg-config file make cmake
curl https://sh.rustup.rs -sSf | sh -s -- -y
source $HOME/.cargo/env
git clone -b andre/progpow https://github.com/paritytech/parity-ethereum
cd parity-ethereum
cargo build --release --features final
./target/release/parity --chain="your-location/gangnam-parity.json"
```

## Contribute

Run a node, [join our Gitter Community](https://gitter.im/ifdefelse/community), and report bugs!

Read more about ProgPoW algorithm on [official EIP spec](https://eips.ethereum.org/EIPS/eip-1057), and download [Progminer mining software](https://github.com/gangnamtestnet/progminer/releases) for mining on Gangnam Testnet (Mining Pool or running node with RPC connection opened required for mining).
