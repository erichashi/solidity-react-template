# Tutorial to create React-Solidity app

## React

### Creating the app:

https://create-react-app.dev/docs/getting-started#creating-a-typescript-app


```bash 
yarn create react-app my-app --template typescript
cd myapp

```
- Rm all files in ‘public’ except index.html
- “ ‘src’ except App.tsx, index.tsx, react-app-env.d.ts 


### Start the react app:
```bash
yarn start
```
Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

The page will reload if you make edits.\
You will also see any lint errors in the console.

### Deploy the app:
```bash
yarn build
```
Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.\
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.



## Solidity
https://hardhat.org/getting-started/#installation

In the project directory, you can run:

```bash
mkdir backend && cd backend
npm install --save-dev hardhat
npx hardhat
```
- select y > y > y
then select >Create a sample project
- rename scripts/sample-script.js to deploy.js


### Compile the contract:

```bash
cd my-app/backend/contracts
npx hardhat compile
```

### Deploy the contract:

```bash
cd my-app/backend/
```

#### Deploy to a real network like RINKEBY

```bash
npx hardhat run scripts/deploy.js --network RINKEBY
mkdir utils && touch utils/getContractAddress.js
```
copy to getContractAddress.js
```javascript
export default function getContractAddress(){
	return "CONTRACT_ADDRESS_HERE"
}
```
- All the react files will need the abi in backend/artifacts/contracts/Contract.sol) and the address in backend/utils/getContractAddress.js 
- Make sure you are connected at the rinkeby network at metamask

#### Deploy in localhost
In a separate terminal, keep runing the localhost by running:
```shell
npx hardhat node 
```
- copy one of these private keys and head over to MetaMask --> Click on Profile Pictrue --> Import Account

then
```shell
npx hardhat run scripts/deploy.js --network local
```



