# Relay offline mode demo

This will spin up a Relay Proxy in offline mode and configure to use the `data.tar.gz` file (instructions on how to generate this file https://docs.launchdarkly.com/home/advanced/relay-proxy-enterprise/offline#enabling-offline-mode)

Once the Relay Proxy is up and running, curl the relay to test the connection (see Steps below on how to do this)


## Prerequisites
- Docker
- jq (brew install jq), this will structure the JSON output in commandline


### Steps
- Clone this repo
- Run `docker-compose up` inside the directory
- To test the endpoint `curl -X REPORT 127.0.0.1:8030/sdk/eval/user -H "Authorization: YOUR-SDK-KEY-HERE" -H "Content-Type: application/json" -d '{"key": "a00ceb", "email":"barnie@example.org"}' | jq '.'`
