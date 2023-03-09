<h1 align="center"> 🐍 Eopsin Pioneer Program 🐍 </h1>

This repository implements many educational Cardano Smart Contracts in Python using [eopsin](https://github.com/ImperatorLang/eopsin).
It also comes with off-chain code using [PyCardano](https://github.com/Python-Cardano/pycardano) and a host of test cases to ensure high quality of the resulting contracts.
Most of the code is in a similar format to the [plutus-pioneer-program](https://github.com/input-output-hk/plutus-pioneer-program).

## Installation

1. Install Python 3.8.
Installer [download](https://www.python.org/downloads/release/python-3810/)

2. Ensure `python3.8 --version` works in your command line.
In Windows, you can do this by copying the `python.exe` file to `python3.8.exe` in your `PATH` environment variable.

3. Install python poetry.
Follow the official documentation [here](https://python-poetry.org/docs/#installation).

4. Install a python virtual environment with poetry:
```bash
# install python dependencies
poetry install
# run a shell with the virtual environment activated
poetry shell
```

5. Install Docker.
Follow the official documentation [here](https://docs.docker.com/get-docker/).

### Cardano Node

Start a [Cardano Node](https://github.com/input-output-hk/cardano-node) and [Ogmios API](https://ogmios.dev/) with docker-compose:
```bash
# starts a cardano node and ogmios api on the preview testnet
docker-compose up
```

You can then access the `cardano-cli` using the docker image:
```bash
docker run --rm -it \
  --entrypoint cardano-cli \
  -e CARDANO_NODE_SOCKET_PATH=/ipc/node.socket \
  -v eopsin-pioneer-program_node-db:/data \
  -v eopsin-pioneer-program_node-ipc:/ipc \
  inputoutput/cardano-node
```
