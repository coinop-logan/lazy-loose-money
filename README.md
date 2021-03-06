https://tamedu.github.io/lazy-loose-money

Running on `Ropsten Testnet`, contract address [0x34bdced976429993238aeb44347a8f9ce23d25d2](https://ropsten.etherscan.io/address/0x34bdced976429993238aeb44347a8f9ce23d25d2)

# Lazy Loose Money

Let say that i want to do running for 1 hour everyday for 100 days. I create a contract and deposit $100 in it. Everyday, I need to (somehow) inform the contract that I finish my running or not. Then after 100 days passed, depend on the completeness of my report, the contract will do some punishment. For example: lock $100 for 10 more-day for each day I did not do the running. So if I skip running for 6 day, the money will be lock there for 2-months. Other kinds of punishment could be: Burn a part of deposit money, give it to someone ...

I'm thinking of asking a friend (roommate for example) to do the checking for me. And how should I incentive my friend to inform the contract regularly and CORRECTLY?

**Here is a solution**

* If I cancel my commitment, I will loose half of my deposit money.

* If I keep my commitment contract run till the end:

    - My friend will get a portion of deposit money according to the number of days reported to the contract.

    - I will get the portion of deposit money according to the number of days I finished my commitment.

We can add more features, like supporters can visit and give the commitment some fund. I can blame the guardian (did not report correctly, ...) and both I him will loose money ...

## Smart contract development environment setup
Install `python`, `web3py` beta and `py-solc`
```
brew tap ethereum/ethereum
brew install python3 solidity
pip3 install --upgrade pip
pip install web3==4.0.0b13
pip install py-solc
```
install and run `geth`
```
brew tap ethereum/ethereum
brew install ethereum
```
### Init your local ethereum for the first time
```
./init_chain.sh
```

### Start `geth` server to deploy and test
Start geth server
```
./run_chain.sh
```

Then run
```
python3 deploy_and_test.py
```

### Start the HTML app
```
python -m SimpleHTTPServer
open http://localhost:8000/
```

## References
### Web3
http://web3py.readthedocs.io/en/latest/
https://github.com/ethereum/wiki/wiki/JavaScript-API

### solidity programming language
https://solidity.readthedocs.io/en/v0.4.21/

### BurnablePayment solidity contract
https://github.com/cryptoprimitive/contracts/blob/master/BurnablePayment.sol

Learn Factory pattern and burnable concept from the contract. Also learn how to struct my solidity code too :) Thanks [@coinop-logan](https://github.com/coinop-logan) to share the idea and introduce me to the blockchain world!

### Vuejs: My Automatic View :)
https://vuejs.org/v2/guide/

### tachyons: styling your HTML without touching CSS code :)
http://tachyons.io/

### Stickk app
http://www.stickk.com/tour/3

Stickk implemented the same idea. Can learn from it. Thanks [@joshpitzalis](https://github.com/joshpitzalis) to let me know.

> It’s important to know what your goal is. **But it’s more important to know what it’ll take you to actually accomplish your goal.**
>
> The possibility of losing money? A Referee who verifies your reports? Supporters who cheer you on along the way? Everyone’s different.
>
> Stickk data shows that creating a Commitment Contract with:
> * A Referee increases your chances of success by up to 2x
> * Financial stakes increase your chances of success by up to 3x
>
> What will it take for you?

### Create a virtualenv
Sometime you need to start from fresh, create a Python virtualenv is a good way to do it.
```
pip install virtualenv
virtualenv -p python3.6 --no-site-packages ~/my-venv
source ~/my-venv/bin/activate
```
