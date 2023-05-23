# Run Bee in Light mode

## Create a project directory
```bash
mkdir bee-light
cd bee-light
```

## Bee Setup (for host-mounted docker volume)
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

## Docker Compose Setup
Copy the relevant docker compose file from the quickstart repository into this directory 
```shell
wget https://raw.githubusercontent.com/rampall/docker-compose-bee-quickstart/main/single-bee/ultra-light-node/docker-compose.yaml -O ./docker-compose.yaml
```

## Run Bee 
Our project folder setup should now look like this:

![image](https://github.com/rampall/docker-compose-bee-quickstart/assets/520570/8fcf825c-f4ff-4f34-aa75-ea26ca6d9df4)

To run bee node:
```
docker compose up
```
