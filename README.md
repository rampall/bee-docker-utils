# docker-compose-bee-quickstart

## Run Bee in Ultra-Light mode

Create a project directory
```bash
rp@pc:~$ mkdir bee-ultra-light
rp@pc:~$ cd bee-ultra-light
```

Create a directory that will be host-mounted and used by Bee to store keys and data
```shell
rp@pc:~/bee-ultra-light$ mkdir bee-home-dir
```

Create a data directory for bee
```shell
rp@pc:~/bee-ultra-light$ mkdir ./bee-home-dir/.bee
```

Generate a random string and save it to a file. 
This will be used as the password for Bee. 
Keep a copy of this password somewhere safe. It will be required for importing/exporting wallets (into Metamask for instance) 
```shell
rp@pc:~/bee-ultra-light$ openssl rand -base64 24 > ./bee-home-dir/.bee/password
```

Copy the relevant bee config file from the quickstart repository into this directory 
```shell
rp@pc:~/bee-ultra-light$ wget https://raw.githubusercontent.com/rampall/docker-compose-bee-quickstart/main/single-bee/ultra-light-node/bee-config.yaml -O ./bee-home-dir/.bee.yaml
```
