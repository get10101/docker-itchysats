# docker-itchysats

A repo facilitating running ItchySats inside a [Docker](https://www.docker.com/what-docker) container on a x86-64 (e.g. macOS, Linux, Windows) or ARMv7 system.

# Overview

ItchySats is a tool allowing CFD trading on Bitcoin - non-custodial, peer-to-peer, Bitcoin only.

You can find more information about ItchySats (along with complete source code) on the main github [repo](https://github.com/itchysats/itchysats).
[FAQ](https://github.com/itchysats/itchysats/blob/master/FAQ.md) might be another good source of knowledge if you get stuck.

# Quickstart

The following guide assumes that you have Docker running, having [docker-compose](https://docs.docker.com/compose/install/) installed is also recommended.
Docker website provides extensive tutorials on Docker installation, please refer there if you are new to Docker.

## Testnet

If you just want to check out the application, and want to try out a "demo" version, where you don't trade with real money, then this config is for you.

```
docker-compose project-directory=testnet up -d
```

## Mainnet

If you're ready to trade with real money, use the following command:

```
docker-compose project-directory=mainnet up -d
```

## User interface

Docker command starts an ItchySats service running in the background.
The service can be controlled via the provided web UI accessible on [https://localhost:8000](https://localhost:8000).
Web UI requires authentication via password generated from your `taker_seed`.

### Credentials

Credentials can be seen in Docker logs after typing in the following command (example for `mainnet`):

```
docker-compose project-directory=mainnet logs
```

It is strongly recommended to not store ItchySats logs outside your machine without filtering the credentials out.

## Stopping ItchySats

On the example of mainnet:

```
docker-compose project-directory=mainnet down
```


# Caveats

- at this stage there is no automated backup of the wallet seed and the database (please backup up 'data' directory inside `testnet` or `mainnet` and store it securely)
- due to using the same port, running mainnet and testnet version at the same time is not supported.

# Contact

In case none of the above questions match the problem you're having, please feel free to reach out to us via one of the following channels:

- [GitHub](https://github.com/itchysats/itchysats/discussions)
- [Telegram](https://t.me/joinchat/ULycH50PLV1jOTI0)
- [Twitter](https://twitter.com/itchysats)
- e-mail: hello (at) itchysats.network

## Contributing

We encourage community contributions whether it be a bug fix, feature suggestion or an improvement to the documentation.
