# 📊 Cryptocurrency Portfolio Tracker (Main Module)

This is the **main orchestrator module** for the Cryptocurrency Portfolio Tracker project. It pulls together two core submodules:

- [`CryptocurrencyTrackerAPI`](https://gitlab.com/pigman8857/CryptocurrencyTrackerAPI): Backend service built with NestJS and TypeORM.

- [`CryptocurrencyTrackerWeb`](https://github.com/pigman8857/CryptocurrencyTrackerWeb): Frontend application built with React and Vite.

---

## 🧩 Project Structure

---

## 🚀 Getting Started

To clone this repository **with both submodules**, run the following command:

```bash
git clone --recurse-submodules <main_repo_url>
```

Or, if you've already cloned the main repo and want to initialize the submodules manually:

```
git submodule update --init --recursive

```

To pull the latest changes from both the main repo and its submodules:

```
git pull --recurse-submodules
```

This will pull in the necessary code from:

API (NestJS backend)

Web (Vite + React frontend)

👷 Development Notes

Each submodule has its own README and Docker setup. You can:

- Run frontend and backend separately with their Docker commands
- The frontend runs on port 3000 or 8080 depending on Docker config

- The backend runs on port 3001 by default

- Ensure ports don’t conflict when running in parallel

## Running

You might need to read README of each submodules as well.

#### Set up steps

```bash
# Install dependency
$ npm run sub:install

```

## More required packages

```bash
# install cross-env as global. cross-env is needed for db migration and running application commands
$ npm install -g cross-env

# ts-node is needed for migration commands
$ npm install ts-node --save-dev
# or below if you want to install as global
$ npm install -g ts-node

# typeorm cli, is used for database migration.
$ npm install -g typeorm
```

#### Build the image

**BEFORE BUILD THE IMAGE**

You will need to go to `./CryptocurrencyTrackerAPI/.env.development` and change `DATABASE_HOST` to `mysql`. It is the docker compose service name. Otherwise, API cannot connect to database.

```bash
$ npm run build:dev:images
```

Then run below commmand to start containers

```bash

$ npm run up:dev

```

#### Migrate the database file

The below commands run of the local code base not from the container.

**BEFORE migrate/revert**

You will need to go to `./CryptocurrencyTrackerAPI/.env.development` and change `DATABASE_HOST` back to `localhost`.
This is because we run migration from local machine, not from container environment.

```bash
# To start migrate/seed
$ npm run db:dev:migrate

# To revert/roll back
$ npm run db:dev:revert

```

#### Unit Test

30 July 2025 - We still have no unit test for Web and any e2e test.

```bash

# To Unit API module unit test
$ npm run api:test

# To Unit API module unit test with coverage
$ npm run api:test:cov

```
