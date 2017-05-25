# Blockchain-learn
Learning blockchain development with hyperledger fabric


## Generating a Blockchain Network with IBM's Hyperldger Fabric v1

This tutorial shows you how to seup a local IBM hyperledger fabric blockchain network

- This assumes you already have a hyperledger profile created in you `~` directory
- First model the network in the Fabric Composer playground, http://composer-playground.mybluemix.net/editor
- Using the `Test` tab, test your network to ensure that transactions work as expected
- Follow steps in this tutorial, https://github.com/hyperledger/composer/wiki/Tutorial-2 (Some things might not work so I have a step by step guide of what worked for me)
	- Install compose-cli and other dependies described in the quickstart, https://hyperledger.github.io/composer/installing/quickstart.html
	- Clone composer quickstart repository like so:
		```
		git clone https://github.com/hyperledger/composer-sample-networks.git
		cp -r ./composer-sample-networks/packages/basic-sample-network/ ./my-network
		``` 
	- Update `package.json` in the `./my-network` directory directory
		- Change the `name` in `package.json` to whatever you want to call your network. (MUST BE IN lower-case. Will bite you later if any is upper case)
		- Update the description in `package.json` to something that makes sense for your network
	- Copy the your the contents of your model files from the composer playground to the `models/sample.cto` file
	- Copy the your the contents of your logic files from the composer playground to the `lib/logic.js` file
	- Copy the your the contents of your permission files from the composer playground to the `permissions.acl` file
	- Next, run `npm install` from `./my-network` directory to generate a Business network archive file
	- You may write unit tests and test your network as decribed here: https://github.com/hyperledger/composer/wiki/Tutorial-2
	- Deploy a Hyperledger Fabric network like so:
		- Go to `./my-network/dist` (A new .bna file was generated when `npm install` was ran, above)
		- Next, run
			`composer network deploy --archiveFile basic-sample-network.bna  -p hlfv1 -i admin -s adminpw` // basic-sample-network.bna is the .bna file in the cwd
	- Next, we will generate a rest api and test the endpoints
		- 




		
