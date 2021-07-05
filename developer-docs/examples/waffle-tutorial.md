# Waffle Tutorial

## Getting Started with the Optimistic Ethereum: Simple ERC20 Token Waffle Tutorial

Hi there! Welcome to our Optimistic Ethereum ERC20 Waffle example!

You can find the repo with all working Waffle examples [here](https://github.com/omgnetwork/optimism/tree/develop/examples/waffle)

If you're interested in writing your first L2-compatible smart contract using Waffle as your smart contract testing framework, then you've come to the right place! This repo serves as an example for how go through and compile & test your contracts on both Ethereum and Optimistic Ethereum.

Let's begin!

### Prerequisites

Please make sure you've installed the following before continuing:

* [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
* [Node.js](https://nodejs.org/en/download/)
* [Yarn 1](https://classic.yarnpkg.com/en/docs/install#mac-stable)
* [Docker](https://docs.docker.com/engine/install/)

### Setup

To start, clone this `Waffle-ERC20-Example` repo, enter it, and install all of its dependencies:

```text
git clone https://github.com/ethereum-optimism/Waffle-ERC20-Example.git
cd Waffle-ERC20-Example
yarn install
```

### Step 1: Compile your contracts for Optimistic Ethereum

Compiling a contract for Optimistic Ethereum is pretty easy! First we'll need to install the [`@eth-optimism/solc`](https://www.npmjs.com/package/@eth-optimism/solc) and [`solc`](https://www.npmjs.com/package/solc) packages. Since we currently only support `solc` versions `0.5.16`, `0.6.12`, and `0.7.6` for Optimistic Ethereum contracts, we'll be using version `0.7.6` in this example. Let's add these two packages:

```text
yarn add @eth-optimism/solc@0.7.6-alpha.1
yarn add solc@0.7.6
```

Next we just need to add a new Waffle config to compile our contracts. Create `waffle-ovm.json` and add this to it:

```text
{
  "compilerVersion": "./node_modules/@eth-optimism/solc",
  "sourceDirectory": "./contracts",
  "outputDirectory": "./build-ovm"
}
```

Here, we specify the new custom Optimistic Ethereum compiler we just installed and the new build path for our compiled contracts.

And we're ready to compile! All you have to do is specify the `waffle-ovm.json` config in your `waffle` command:

```text
yarn waffle waffle-ovm.json
```

Our `waffle-ovm.json` config file tells Waffle that we want to use the Optimistic Ethereum solidity compiler.

Yep, it's that easy. You can verify that everything went well by looking for the `build-ovm` directory.

Here, `build-ovm` signifies that the contracts contained in this directory have been compiled for the OVM, the Optimistic Virtual Machine, as opposed to the Ethereum Virtual Machine. Now let's move on to testing!

### Step 2: Testing your Optimistic Ethereum contracts

Testing with Waffle is easy. We've included a simple set of ERC20 tests inside [`Waffle-ERC20-Example/test/erc20.spec.js`](https://github.com/ethereum-optimism/Waffle-ERC20-Example/blob/main/test/erc20.test.js). Let's run these tests with `waffle`:

```text
yarn mocha 'test/*.spec.js' --timeout 10000
```

If everything went well, you should see a bunch of green checkmarks.

#### Testing an Optimistic Ethereum contract

Woot! It's finally time to test our contract on top of Optimistic Ethereum. But first we'll need to get a local version of an Optimistic Ethereum node running...

Since we're going to be using Docker, make sure that Docker is installed on your machine prior to moving on \(info on how to do that [here](https://docs.docker.com/engine/install/)\). **We recommend opening up a second terminal for this part.** This way you'll be able to keep the Optimistic Ethereum node running so you can execute some contract tests.

Now we just need to download, build, and install our Optimistic Ethereum node by running the following commands. 

{% page-ref page="../local-omgx.md" %}

With your local instance of Optimistic Ethereum up and running, let's test your contracts! Since the two JSON RPC provider URLs \(one for your local instance Ethereum and Optimistic Ethereum\) have already been specified in your `.env` file, all we need to do next is run the test command.

To do that, run:

```text
yarn TARGET=OVM mocha 'test/*.spec.js' --timeout 50000
```

Notice that we use the `TARGET=OVM` flag to let `mocha` know that we want to use the `build-ovm` folder as our path to our JSON files. \(Remember that these JSON files were compiled using the Optimistic Ethereum solidity compiler!\)

You should see a set of passing tests for your ERC20 contract
