## Dev Environment on MAC OSX 12 (Monterey)

### Install Homebrew

Install instructions [here](https://brew.sh/)

### Install Node

Budibase requires a recent version of node (14+):
```
brew install node npm
node -v
```

### Install npm requirements

```
npm install -g yarn jest lerna
```
### Install Docker and Docker Compose

```
brew install docker docker-compose
```
### Clone the repo
```
git clone https://github.com/Budibase/budibase.git
```

### Check Versions

This setup process was tested on Mac OSX 12 (Monterey) with version numbers shown below. Your mileage may vary using anything else.

- Docker: 20.10.14
- Docker-Compose: 2.6.0
- Node: 18.3.0
- Yarn: 1.22.19
- Lerna: 5.1.4

### Build

```
cd budibase
yarn setup
```
The yarn setup command runs several build steps i.e.
```
node ./hosting/scripts/setup.js && yarn && yarn bootstrap && yarn build && yarn dev
```
So this command will actually run the application in dev mode. It creates .env files under `./packages/server` and `./packages/worker` and runs docker containers for each service via docker-compose.

The dev version will be available on port 10000 i.e.

http://127.0.0.1:10000/builder/admin