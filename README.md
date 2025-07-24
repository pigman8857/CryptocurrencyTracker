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
