# Solidity-Logging-Library
An expensive library to do loggings in smart contracts 

## example

```javascript
import 'logging.sol';

contract MyContract is logging {

  function MyContract() {
    logging.log("Initiated");
  }
}
```

## view logs
Logging would log in two places for now, one the variable called lastLog and the other event log

```javascript
MyContract.lastLog.call()
[1467913219, "Initiated"]
```

```
(event log)
00000000000000000000000000000000000000000000000000000000577e9299
0000000000000000000000000000000000000000000000000000000000000040
0000000000000000000000000000000000000000000000000000000000000009
496e697469617465640000000000000000000000000000000000000000000000

timestamp -> 577e9299 -> GMT: Thu, 07 Jul 2016 17:34:17 GMT  // http://www.epochconverter.com/hex
message -> 496e697469617465640000000000000000000000000000000000000000000000 -> "Initiated"
```

##TODO
1. Log Stack
 * string[] public logStack; ?
 * mapping (uint => Log[]) public logStack; ?
2. Optimize gas usage

