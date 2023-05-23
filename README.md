# docker-compose-bee-quickstart

## Run Bee in Ultra-Light mode

Create a project directory
```
mkdir bee-ultra-light
cd bee-ultra-light
```

Create a directory that will be host-mounted and used by Bee to store keys and data
```
mkdir bee-home-dir
chmod 777 -R bee-home-dir
```

Generate a random string and save it to a file. 
This will be used as the password for Bee. 
Keep a copy of this password somewhere safe. It will be required for importing/exporting wallets (into Metamask for instance) 
```
openssl rand -base64 24 > ./bee-home-dir/password
```

