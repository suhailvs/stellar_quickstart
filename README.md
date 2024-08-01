# Stellar Quickstart Docker Image

## To get new changes

Pull new changes in master branch. 
- go to: https://github.com/suhailvs/stellar_quickstart/tree/master
- click: Sync fork

Now rebase this branch with `master` branch and force push it. 
```
git switch master
git pull origin master
git switch main
git rebase master
git push -f origin main
```


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

## Create a new Address

https://developers.stellar.org/docs/build/guides/basics/create-account

```
# https://github.com/StellarCN/py-stellar-base
# pip install stellar-sdk
>>> from stellar_sdk import Keypair
>>> pair = Keypair.random()
>>> print(f"Secret: {pair.secret}",f"Public Key: {pair.public_key}")
Secret: SBSDA4H2D4OGT5UFHBHK5HSFHCMUS3P3R2ZHIESKUYZ2VSEYBJGOB4GU 
Public Key: GB3SSRJE7CETRO3WZYBKMSIH2HT74LV5DZ64IWPEVSAODVP6C6EVORWP
```

### Create Account
A valid keypair, however, does not make an account: in order to prevent unused accounts from bloating the ledger, Stellar requires accounts to hold a minimum balance of 1 XLM before they actually exist. 

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





