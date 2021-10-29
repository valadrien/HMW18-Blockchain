# HMW18-Blockchain

# Setup Instructions(MacOS)

You will need the following programs to set up the Ethereum Blockchain:

- Git Bash

- MyCrypto

- Go Ethereum ('Geth')

# Create a blockchain with 'Geth' (Go Ethereum)

Generate the genesis block configurations with geth.

- Open Git Bash and change directories to the Blockchain-Tools folder.

- Run ./puppeth and name your network.

- Select the option to configure a new genesis block. Next select create new genesis from scratch.

- Choose the Clique - proof-of-authority consensus algorithm.

![image info](Week18_Blockchain_HW/sc1.png)
![image info](Week18_Blockchain_HW/sc2.png)

- Paste the account address(es) from the MyCrypto steps into the list of accounts to seal.

- Press enter enter when prompted for pre-funding the pre-compiled accounts with wei.

- Set a numeric network ID (0923 was used in this example).

- Now that you are back at the main menu, choose the Manage existing genesis option.

- Select Export genesis configurations. Hit enter and the files will be saved to the current directory 'Blockchain-Tools'. This will fail to create two of the files, but you only need json file with your network name (hwblockchain.json in this example). Press ctrl+C to exit the puppeth prompts.

![image info](Week18_Blockchain_HW/sc3.png)

- Initialize each node with the new heritageblock.json file using geth.

- Create accounts for two (or more) nodes for the network with a separate datadir for each using geth. Replace nodename with your node's name e.g. node1.

- ./geth heritageblock.json new --datadir node1

- Saving the 'Public address of the key' and 'Path of the secret key file' will allow you to restart the blockchain after closing.

- Initiate the nodes to follow the protocol set in the genesis block file heritageblock.json.

./geth init heritageblock.json --datadir node1

./geth init heritageblock.json --datadir node2

![image info](Week18_Blockchain_HW/sc4.png)

- Start mining with the first node. Make sure to capture the enode address. This will be used for the next step.

./geth --datadir node1 --mine --miner.threads 1

![image info](Week18_Blockchain_HW/sc5.png)

- Start the second node using the first node's enode address as the bootnode flag.

./geth --datadir node2 --port 30304 —rpc --bootnodes “enode://daf000294b86f66ffc7c481a89213d6b6441c6c1f996602345fa56a8ed3b568dcb330d3cc09e567843b29acde6c34cc637f1986df52549a23a323dee18d43638@127.0.0.1:30303”

- Below both nodes running; Node 1 on the right. Node 2 on the right. See both have recognized a peer to mine. 

![image info](Week18_Blockchain_HW/sc6.png)

# Send a test transaction

- Return the the MyCrypto app. On the lefthand-side click Change Network and the click +Add Custom Node.

- Enter the Node Name and Network Name. Set Network to Custom and Currency as ETH. The Network ID should be entered as the Chain ID. Use http://127.0.0.1:8545 as the the URL. Click 'Save & Use Custom Node.'
    * note that We had test trialed the same network configutation therfore in this case We are overwritting it. 

![image info](Week18_Blockchain_HW/sc7.png)

- I've failed at getting a transaction thru. None stop troubleshooting. Issues with versions and than saved information impeding my progress. 
- Have not fully graspped the account set up as the "pre Funding" of both provided accounts did now reflect on the balance when created. 

![image info](Week18_Blockchain_HW/sc8.png)

- Note that We were successful at creating the Custom ETH Network. See red circle in below image.

![image info](Week18_Blockchain_HW/sc9.png)
