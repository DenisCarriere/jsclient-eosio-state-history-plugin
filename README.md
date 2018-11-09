# Javascript client for eosio state-history-plugin websocket interface

## Test 

### EOSIO Docker compiled with state_history_plugin
```
    docker run --rm --name fungi-eosio -d -p 8888:8888 -p 8889:8080 -p 9876:9876 tmuskal/fungi-eosio-dev /bin/bash -c "nodeos -e -p eosio --plugin eosio::producer_plugin  --disable-replay-opts --trace-history --plugin eosio::state_history_plugin --plugin eosio::history_plugin --plugin eosio::chain_api_plugin --plugin eosio::history_api_plugin --plugin eosio::http_plugin -d /mnt/dev/data --config-dir /mnt/dev/config --http-server-address=0.0.0.0:8888 --access-control-allow-origin=* --contracts-console --max-transaction-time=1000 --http-validate-host=false --verbose-http-errors
```

or compile and run https://github.com/EOSIO/eos/tree/state-history-plugin/

### Run listener

```
    npm install
    npm start
```

### 

* compile helloworld contract in contracts/helloworld

```
    cleos set code helloworld ./contracts/helloworld/helloworld.wasm
    cleos set abi helloworld ./contracts/helloworld/helloworld.abi
    cleos push action helloworld hi [1234] -p helloworld
```