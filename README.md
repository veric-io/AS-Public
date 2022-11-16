## LP Manager Contract:
Contract address: https://goerli.etherscan.io/address/0xdD854d6f073354038d6B6Ea1Eb57fA8Cc1875b91

### API:
```solidity
interface ILPManager {
    event PoolCreated(address indexed token, address pool, uint);
    event LiquidityAdded(address indexed token, address to, uint);
    event LiquidityRemoved(address indexed token, address to, uint);
    // Create LP Pool for given token
    function createPool(address token) external returns (address pool);
    // Removing "Liquidity" (LP token) of "token" (e.g. USDC) and send them back to "to" address  
    function removeLiquidity(address token, uint liquidity, address to) external returns (uint amount);
    // Adding "amount" of "token" (e.g. USDC) and send liquidity(LP token) to "to" address
    function addLiquidity(address token, uint amount, address to) external returns (uint liquidity);
}
```
## Test Token:
USDC: https://goerli.etherscan.io/address/0x4600029b3b2426d627dFde7d57AbCFdC96aEC147

DAI: https://goerli.etherscan.io/address/0x581857409579161Dabd2C4994f78b2F1B3671bc2

## DIDRegistry Contract:

Contract address: https://explorer.harmony.one/address/0xde51bb12d5cef80ff2334fe1019089363f80b46e?activeTab=7

### API:
```solidity
interface IDIDRegistry {
    function registerDid(string memory did, address pubkey) external;
    function updateDid(string memory did, address pubkey) external;
    function getPublicKeyJwk(string memory did) view external returns(address pubkey);
    function getType() view external returns(string memory);
}
```
