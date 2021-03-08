### How to launch new Blockchain

---

1. Open your browser and download and install (Go Ethereum Tools)[https://geth.ethereum.org/downloads/]
2. Install (MyCrypto Desktop App)[https://download.mycrypto.com/]
..1. Select create a new wallet
..2. Select generate a wallet (recommended to use Mnemonic Phrase)
..3. Store your Mnemonic Phrase or passphrase somewhere safe offline
3. Run `puppeth` in your command line interface
4. Select `Create a new genesis block from scratch` (2) and then select `Ethash proof of work` (1)
5. Press enter or yes to precombile
6. Specify your chain/network ID, this will be important later!
7. Select `Manage existing genesis` (2)
8. Select `Export genesis configurations` (2) and export genesis configurations to your desired directory
9. Use `geth --datadir node1 account new` and repeat the same process to create a second node
10. Initialize each node using the generated networkname.json with the command `geth --datadir <node> init networkname.json`
11. The nodes can now be used to begin mining blocks with `geth --datadir <node> --mine --miner.threads 1`
12. Scroll up to node1 mine and copy the enode for node2. In a separate command line window, run `geth --datadir node2 --port 30304 --rpc --botnodes "<enode>"`
13. Your private Proof of Authority blockchain should now be running! Now, we must create a custom network for node 1 and 2
14. Open the MyCrypto app and select Change Network at the bottom left.
15. Select "Add CUstom Node" and add the custom network information that you set earlier. Make sure you choose Custom in the Network column to reveal all options such as Chain ID
16. In the URL box, copy and paste http://127.0.0.1:8545. You can then save & use custom node
17. Select View & Send option on the left menu and click Keystore file
18. Select wallet file and navigate to the keystore directory inside of your node1 directory. Select the file there, provide your password when prompted and select Unlock.
19. In the To Address box, enter the account address from node2 and enter an amount of ETH
20. Send the transaction