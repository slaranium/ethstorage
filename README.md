
# SIMPLE GUIDE
## Proceed to this step if you reveived the DM 


## Creating Your First Unstoppable dApp on Ethereum

This guide will show you how to deploy a basic decentralized application (dApp) on the Ethereum blockchain using the [ethfs-cli](https://github.com/ethstorage/ethfs-cli/) tool.


## System Requirements
- MacOS Version 14+, Ubuntu 20.04+, or Windows with WSL2
- Node.js 17+



## Step-by-Step Guide

### Step 1: Prepare Your Application

1. Create a folder named `dist`.
2. Inside `dist`, add two files:

   - `app.html` with the following content:

     ```html
     <html>
         <head>
             <script>
                 async function fetchData() {
                     const url = 'web3://0xf14e64285Db115D3711cC5320B37264708A47f89:11155111/greeting';
                     const response = await fetch(url);
                     const data = await response.text();
                     document.getElementById('content').textContent = data;
                 }
                 window.onload = fetchData;
             </script>
         </head>
         <body>
             <div id="content"> Loading greeting... </div>
             <br>
             <img src="./degen.jpeg" alt="">
         </body>
     </html>
     ```

   - `degen.jpeg` (an image file, e.g., `degen.jpeg`).
  



### Step 2: Smart Contract Using the Account that was selected

[Deploy a simple smart contract on Sepolia](https://remix.ethereum.org/)



```solidity
pragma solidity >=0.8.2 <0.9.0;

contract App {
    function greeting() public pure returns (string memory) {
        return "LFG, Degen!";
    }
}
```






### Step 3: Install ethfs-cli

Install `ethfs-cli` using npm:

```bash
npm i -g ethfs-cli

```





### Create a FlatDirectory Contract
Create a FlatDirectory on Sepolia:

```
ethfs-cli create -p <your-private-key> -c 11155111
```

### You'll get an address for your FlatDirectory.



--------

### Step 5: Upload Your Application
Upload your application to the FlatDirectory:

```
ethfs-cli upload -f dist -a <flat-directory-address> -c 11155111 -p <your-private-key> -t 1
```
Replace <flat-directory-address> with the address from the previous step. This will deploy the files using Ethereum's native storage. 



### Step 6: Access Your dApp
Once deployed, you can access your dApp via a web3 URL:

```
web3://<flat-directory-address>:11155111/app.html
```


### For example 
```
web3://0x49EDFB27a463545337487D39a8349760B345F160:11155111/app.html
```



### Step 7: Reduce Costs with BLOBs (Optional)
To reduce upload costs using Ethereum's EIP-4844 BLOBs:

Install the eth-blob-uploader tool: 
```
npm i -g eth-blob-uploader
```


Upload your files using BLOBs:
```
eth-blob-uploader -r <Sepolia RPC URL> -p <your-private-key> -f dist/app.html -t <any-address>
eth-blob-uploader -r <Sepolia RPC URL> -p <your-private-key> -f dist/degen.jpeg -t <any-address>
```




# Testing your dApp 

[Visit this webpage and paste link](https://w3url.eth.1.w3link.io/#/)



## Now fill the form 

[Fill form here](https://dawme4mo.forms.app/ethstorage-2nd-campaign-submission?ref=blog.ethstorage.io) 

## Official guide 
[Official Guide](https://blog.ethstorage.io/building-unstoppable-dapps-on-ethereum-ethstorages-2nd-public-testnet-campaign/)


 














