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

## ARSW Token:
https://goerli.etherscan.io/address/0x84e4A9404974F503b39b746393954f6D46e922cf

## ARSW Farm:
https://goerli.etherscan.io/address/0x1D3cB38113ACDb215d97C8fa6534e7e36aA958e2
### API:
```solidity
interface ITokenStake {
    function addLPPool(IERC20 lpToken_, uint allocPoint_, uint lastRewardBlock_) external;
    function depositLP(uint _pid, uint _amount) external;
    function pendingLPReward(uint _pid, address _user) public view returns (uint[] memory pending);
    function withdrawLP(uint _pid, uint _amount) external;
    function setRewardPerBlock(uint _rewardPerBlock) external;
    function setArswAddress(IERC20Upgradeable token_) external;
}
```

## DIDRegistry Contract:

Contract address:
https://explorer.harmony.one/address/0x01fd38ca25cbb9e4c975b6ce329ca10153a8e927
https://goerli.etherscan.io/address/0x9B1b253Ab50970aD315F0a12F88e824070cd81F4



### API:
```solidity
interface IDIDRegistry {
    function registerDid(string memory did, string memory pubkey) external;
    function updateDid(string memory did, string memory pubkey) external;
    function getPublicKeyJwk(string memory did) view external returns(string memory pubkey);
    function getType() view external returns(string memory);
}
```
