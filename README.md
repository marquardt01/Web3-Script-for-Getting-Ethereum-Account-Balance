# Web3-Script-for-Getting-Ethereum-Account-Balance
Web3 script that allows you to retrieve the balance of an Ethereum account
const Web3 = require('web3');

// Connect to the Ethereum network
const web3 = new Web3('https://mainnet.infura.io/v3/YOUR_INFURA_PROJECT_ID');

// Get account balance
async function getAccountBalance(accountAddress) {
  try {
    const balance = await web3.eth.getBalance(accountAddress);
    return web3.utils.fromWei(balance, 'ether');
  } catch (error) {
    console.error('Failed to retrieve account balance:', error);
    return null;
  }
}

// Usage example
(async () => {
  const accountAddress = '0xYOUR_ACCOUNT_ADDRESS';
  const balance = await getAccountBalance(accountAddress);
  console.log(`Account balance: ${balance} ETH`);
})();
