# Connect 4

Exemplary event sourcing and CQRS implementation of the game _Connect 4_ using 

- Haskell
- PureScript
- Elm
- Postgres
- Redis
- GraphQL/Hasura
- No ES/CQRS framework
- No bullshit

## Overview

Components:

- [Command API](https://github.com/battermann/cosmic-ray-api) (Haskell, Postgres) [![Build Status](https://travis-ci.org/battermann/cosmic-ray-api.svg?branch=master)](https://travis-ci.org/battermann/cosmic-ray-api)
- [Read Model/Query API](https://github.com/battermann/cosmic-ray-rm) (Haskell, Hasura, Postgres) [![Build Status](https://travis-ci.org/battermann/cosmic-ray-rm.svg?branch=master)](https://travis-ci.org/battermann/cosmic-ray-rm)
- [Event Publisher](https://github.com/battermann/cosmic-ray-pub) (PureScript, Redis) [![Build Status](https://travis-ci.org/battermann/cosmic-ray-pub.svg?branch=master)](https://travis-ci.org/battermann/cosmic-ray-pub)
- [UI](https://github.com/battermann/cosmic-ray-ui) (Elm) [![Build Status](https://travis-ci.org/battermann/cosmic-ray-ui.svg?branch=master)](https://travis-ci.org/battermann/cosmic-ray-ui)

![alt text](./out/docs/C4_Context/C4_Elements.svg)

## Two player games

The player identity is tied to a browser instance. So to play a two player game ideally you should play on two different devices. If played on the same device make sure to use different browser instances.

## Prerequisites

- Make sure you also clone the git submodules e.g. with `git clone --recursive git@github.com:battermann/connect-4.git`
- [Docker Compose](https://docs.docker.com/compose/)
- [Task](https://taskfile.dev/#/installation)

## Run with docker

Run

```shell
task up
```

Note that if this task is run for the first time it will take a very very long time to build the Haskell containers.

Then browse to `http://localhost:3000/`.

## Run locally

### Prerequisites for running locally

- Elm
- create-elm-app
- node/npm
- stack
- ...

Go to `./ui` and run `npm install`.

### Start services locally

To run the application locally, run:

```shell
task db
```

Then run each of these commands in a separate terminal window:

```shell
task pub
```

```shell
task read-model
```

```shell
task cmd-api
```

```shell
task ui
```

## Todos

- Elm UI: Use one out and one in port
