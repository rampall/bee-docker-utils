# Run Bee as a full node with docker compose

## Github

- [Bee Full Node Quickstarter](https://github.com/rampall/docker-compose-bee-quickstart/tree/main/bee/full-node)
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
mkdir bee-fullnode
cd bee-fullnode
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
wget https://raw.githubusercontent.com/rampall/docker-compose-bee-quickstart/main/bee/full-node/bee-config.yml -O ./bee-home-dir/.bee.yml
```

## Docker Compose Setup

### Step 6: Copy the relevant docker compose file from the quickstart repository into this directory 
```shell
wget https://raw.githubusercontent.com/rampall/docker-compose-bee-quickstart/main/bee/full-node/docker-compose.yml -O ./docker-compose.yml
```

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

## Run Bee 

### Step 7: Run bee node with docker compose:
```
docker compose up
```
The bee node will now fire up and then request for funds to be added to the node's wallet address. Something like this:
```
bee        | "time"="2023-05-23 14:59:16.210262" "level"="warning" "logger"="node/chequebook" "msg"="cannot continue until there is at least min xDAI (for Gas) available on address" "min_xdai_amount"="0.000698400544" "address"="0xcde7Db709fa16aaE6f5e94042026453AC2b1A3DF"
```

## Fund your node's wallet

Copy your node's wallet address from the logs.

Visit https://www.gnosisfaucet.com/ and paste the address in the **Wallet** field to request 0.025 DAI. 

![image](https://github.com/rampall/docker-compose-bee-quickstart/assets/520570/d3b2f19c-869d-400b-b300-fef2336a3d2b)

The bee node's wallet should be now funded and the bee light node will proceed to sync with the Swarm network.

## Check Bee Dashboard

### Step 8: You can visit the Bee Dashboard at - http://localhost:8080/ 
