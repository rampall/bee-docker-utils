# Run Bee in Ultra-Light mode

## Create a project directory

Step 1: 

```bash
mkdir bee-ultra-light
cd bee-ultra-light
```

## Bee Setup (for host-mounted docker volume)

Step 2: Create a directory that will be host-mounted and used by Bee to store keys and data

```shell
mkdir bee-home-dir
```

Step 3: Create a data directory for bee
```shell
mkdir ./bee-home-dir/.bee
```

Step 4: Generate a random string and save it to a file. 
This will be used as the password for Bee. 
Keep a copy of this password somewhere safe. It will be required for importing/exporting wallets (into Metamask for instance) 
```shell
openssl rand -base64 24 > ./bee-home-dir/password
```

Step 5: Copy the relevant bee config file from the quickstart repository into this directory 
```shell
wget https://raw.githubusercontent.com/rampall/docker-compose-bee-quickstart/main/bee/ultra-light-node/bee-config.yml -O ./bee-home-dir/.bee.yml
```

## Docker Compose Setup

Step 6: Copy the relevant docker compose file from the quickstart repository into this directory 
```shell
wget https://raw.githubusercontent.com/rampall/docker-compose-bee-quickstart/main/bee/ultra-light-node/docker-compose.yml -O ./docker-compose.yml
```

## Run Bee 
Our project folder setup should now look like this:

![image](https://github.com/rampall/docker-compose-bee-quickstart/assets/520570/8fcf825c-f4ff-4f34-aa75-ea26ca6d9df4)

```
tree -a .
```
```
.
├── bee-home-dir
│   ├── .bee
│   ├── .bee.yml
│   └── password
└── docker-compose.yml
```

Step 7: Run bee node:
```
docker compose up
```
