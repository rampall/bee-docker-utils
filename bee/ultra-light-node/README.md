# How to run Bee in Ultra-Light mode with Docker Compose

## Github

- [Ultra Light Bee Node Quickstarter](https://github.com/rampall/docker-compose-bee-quickstart/tree/main/bee/ultra-light-node)
- [All Quickstarters](https://github.com/rampall/docker-compose-bee-quickstart)

## Prerequisites

- latest `docker` cli must be installed
- The following ports must be free and available
    - **1633**
    - **1634** 
    - **1635**
    - **8080**

### Step 1: Create a project directory

```bash
mkdir bee-ultra-light
cd bee-ultra-light
```

## Bee Setup 

### Step 2: Create a home directory that will be host-mounted and used by Bee to store keys and data

```shell
mkdir bee-home-dir
```

### Step 3: Create a data directory for bee
```shell
mkdir ./bee-home-dir/.bee
```

### Step 4: Generate a random string and save it to a file. 
This will be used as the password for Bee. 
Keep a copy of this password somewhere safe. It will be required for importing/exporting wallets (into Metamask for instance) 
```shell
openssl rand -base64 24 > ./bee-home-dir/password
```

### Step 5: Copy the relevant bee config file from the quickstart repository into this directory 
```shell
wget https://raw.githubusercontent.com/rampall/docker-compose-bee-quickstart/main/bee/ultra-light-node/bee-config.yml -O ./bee-home-dir/.bee.yml
```

## Docker Compose Setup

### Step 6: Copy the relevant docker compose file from the quickstart repository into this directory 
```shell
wget https://raw.githubusercontent.com/rampall/docker-compose-bee-quickstart/main/bee/ultra-light-node/docker-compose.yml -O ./docker-compose.yml
```

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

## Run Bee 
Step 7: Run bee node with docker compose:
```
docker compose up
```

## Check Bee Dashboard
Step 8: Visit the Bee Dashboard at - http://localhost:8080/ 
