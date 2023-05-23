# docker-compose-bee-quickstart

## Run Bee in Ultra-Light mode

Create a project directory
```bash
mkdir bee-ultra-light
cd bee-ultra-light
```

Create a directory that will be host-mounted and used by Bee to store keys and data
```shell
mkdir bee-home-dir
```

Create a data directory for bee
```shell
mkdir ./bee-home-dir/.bee
```

Generate a random string and save it to a file. 
This will be used as the password for Bee. 
Keep a copy of this password somewhere safe. It will be required for importing/exporting wallets (into Metamask for instance) 
```shell
openssl rand -base64 24 > ./bee-home-dir/password
```

Copy the relevant bee config file from the quickstart repository into this directory 
```shell
wget https://raw.githubusercontent.com/rampall/docker-compose-bee-quickstart/main/single-bee/ultra-light-node/bee-config.yaml -O ./bee-home-dir/.bee.yaml
```
