# Ethernaut

The Ethernaut is a Web3/Solidity based wargame inspired on overthewire.org, played in the Ethereum Virtual Machine. Each level is a smart contract that needs to be 'hacked'.
Here are my solutions for each level.

##0.Hello Ethernaut

> contract.info()
< [[PromiseResult]]: "You will find what you need in info1()."

> contract.info1()
< [[PromiseResult]]: "Try info2(), but with \"hello\" as a parameter."

> contract.info2("hello")
< [[PromiseResult]]: "The property infoNum holds the number of the next info method to call."

> contract.abi

> let x = await contract.infoNum()

> x.toString()
< '42'

> contract.info42()
< [[PromiseResult]]: "theMethodName is the name of the next method."

> contract.theMethodName()
< [[PromiseResult]]: "The method name is method7123949."

> contract.method7123949()
< [[PromiseResult]]: "If you know the password, submit it to authenticate()."

> contract.password()
< [[PromiseResult]]: "ethernaut0"

> contract.authenticate("ethernaut0")

Submit the instance by clicking the orange button.

(-(-_(-_-)_-)-) Well done, You have completed this level!!!




