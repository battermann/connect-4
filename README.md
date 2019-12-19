# Connect 4

Connect 4 implemented with event sourcing and CQRS using Haskell, Elm, Postgres and Hasura.

Components:

- [Command API](./api/) (Haskell, Postgres)
- [Query API](./read-model/) (Haskell, Hasura, Postgres)
- [UI](./ui/) (Elm)

[Live Demo](https://cosmic-ray.surge.sh/)

## Prerequisites

- Install [Task](https://taskfile.dev/#/installation)

## Run with docker

TBD

## Run locally

### Prerequisites for running locally

- Elm
- create-elm-app
- node/npm
- stack
- ...

You also need to:

- go to `./ui` and install npm dependencies with `npm install`
- go to `./api` and `./read-model` and set up stack with `stack setup`

### Start services locally

To run the application locally, first start up the database and Hasura with `docker-compose`:

```shell
task db
```

Then run each of these commands in a separate terminal window:

```shell
task start-cmd-api
```

```shell
task start-query-api
```

```shell
task start-ui
```

## Todos

- Make event-store generic
- Extract generic event sourcing stuff into separate module
- Elm UI: Use one out and one in port
