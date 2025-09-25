# Stellar Quickstart Docker Image

## Quick Start

```
# initialize submodule: https://github.com/chatch/stellarexplorer
$ git submodule update --init
# run horizon, postgresql, stellar-core
$ docker run -d -p "8000:8000" --name stellar stellar/quickstart --local
$ cd stellarexplorer
$ npm i && npm i nodemon && npm run build && npm run dev
```

- Now visit: <http://localhost:3000>
- Live site: <https://steexp.com/>


To do that, send Friendbot the public key you created.
```
$ curl http://localhost:8000/friendbot?addr=GB3SSRJE7CETRO3WZYBKMSIH2HT74LV5DZ64IWPEVSAODVP6C6EVORWP
```

Now you can get account details:
```
curl -L 'http://localhost:8000/accounts/GB3SSRJE7CETRO3WZYBKMSIH2HT74LV5DZ64IWPEVSAODVP6C6EVORWP' \
-H 'Accept: application/json'
```

horizon api reference: https://developers.stellar.org/docs/data/horizon/api-reference





