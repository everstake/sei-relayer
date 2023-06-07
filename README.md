# example-sei-relayer

**Disclaimer:**

Everstake assumes no responsibility for the development and maintenance of the smart contract. We have solely provided a public repository for storing the smart contract code. In the event of any issues or concerns regarding this smart contract, please direct all inquiries to the team at Wormhole and SEI Foundation.

Please note that Everstake shall not be held liable for any damages, losses, or liabilities arising from the use or reliance on the smart contract, including but not limited to errors, bugs, or security vulnerabilities. The use of the smart contract is at your own risk.

By accessing and utilizing the code stored in this repository, you acknowledge and agree that Everstake is not responsible for any actions, consequences, or outcomes resulting from the use of the smart contract.

It is recommended that you thoroughly review and assess the smart contract code, seeking professional advice if necessary, before engaging with it.

## Instruction
Run the spy, redis, and then the relayer.

**Run a wormhole network spy**

Testnet:

```bash
docker run --platform=linux/amd64 -p 7073:7073 --entrypoint /guardiand ghcr.io/wormhole-foundation/guardiand:latest spy --nodeKey /node.key --spyRPC "[::]:7073" --network /wormhole/testnet/2/1 --bootstrap /dns4/wormhole-testnet-v2-bootstrap.certus.one/udp/8999/quic/p2p/12D3KooWAkB9ynDur1Jtoa97LBUp8RXdhzS5uHgAfdTquJbrbN7i
```

Mainnet:

```bash
docker run --platform=linux/amd64 -p 7073:7073 --entrypoint /guardiand ghcr.io/wormhole-foundation/guardiand:latest spy --nodeKey /node.key --spyRPC "[::]:7073" --network /wormhole/mainnet/2 --bootstrap /dns4/wormhole-mainnet-v2-bootstrap.certus.one/udp/8999/quic/p2p/12D3KooWQp644DK27fd3d4Km3jr7gHiuJJ5ZGmy8hH4py7fP4FP7
```

**Run redis**

```bash
docker run --rm -p 6379:6379 --name redis-docker -d redis
```

**Run the relayer**

```bash
nvm use && npm ci && npm start
```
