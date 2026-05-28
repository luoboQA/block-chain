# Are you looking for the source code for my book?

Please find it here: https://github.com/dvf/blockchain-book

The book is available on Amazon: https://www.amazon.com/Learn-Blockchain-Building-Understanding-Cryptocurrencies/dp/1484251709

# Learn Blockchains by Building One

[![Build Status](https://travis-ci.org/dvf/blockchain.svg?branch=master)](https://travis-ci.org/dvf/blockchain)

This is the source code for my post on [Building a Blockchain](https://medium.com/p/117428612f46). 

## Installation

1. Make sure [Python 3.6+](https://www.python.org/downloads/) is installed. 
2. Install [pipenv](https://github.com/kennethreitz/pipenv). 

```
$ pip install pipenv 
```
3. Install requirements  
```
$ pipenv install 
``` 

4. Run the server:
    * `$ pipenv run python blockchain.py` 
    * `$ pipenv run python blockchain.py -p 5001`
    * `$ pipenv run python blockchain.py --port 5002`

5. API
查看完整区块链
GET /chain
curl http://localhost:5002/chain

挖矿（创建新区块）
GET /mine
curl http://localhost:5002/mine

创建新交易
POST /transactions/new
curl -X POST http://localhost:5002/transactions/new \
  -H "Content-Type: application/json" \
  -d '{"sender": "Alice", "recipient": "Bob", "amount": 5}'

注册邻居节点
POST /nodes/register
curl -X POST http://localhost:5002/nodes/register \
  -H "Content-Type: application/json" \
  -d '{"nodes": ["http://localhost:5001"]}'

解决共识冲突
GET /nodes/resolve
curl http://localhost:5002/nodes/resolve