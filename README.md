## Dependencies

* ethereumjs-testrpc 
* web3
* solc

Install missing dependencies with [npm](https://www.npmjs.com/). 

## Usage

Run the following commands to open the node console then deploy your contract to the test chain

```
rahulmanuwas/voting-contract$ node
> Web3 = require('web3')
> web3 = new Web3(new Web3.providers.HttpProvider("http://localhost:8545"));
> code = fs.readFileSync('Voting.sol').toString()
> solc = require('solc')
> compiledCode = solc.compile(code)
> abiDefinition = JSON.parse(compiledCode.contracts[':Voting'].interface)
> VotingContract = web3.eth.contract(abiDefinition)
> byteCode = compiledCode.contracts[':Voting'].bytecode
> deployedContract = VotingContract.new(['Rama','Nick','Jose'],{data: byteCode, from: web3.eth.accounts[0], gas: 4700000})
> deployedContract.address
> contractInstance = VotingContract.at(deployedContract.address)
```

Interact with the contract via the html page attached, just open it in your browser. See [this](https://medium.com/@mvmurthy/full-stack-hello-world-voting-ethereum-dapp-tutorial-part-1-40d2d0d807c2) tutorial for more details. 

## Credits

The credits for this code go to [maheshmurthy](https://gist.github.com/maheshmurthy).
