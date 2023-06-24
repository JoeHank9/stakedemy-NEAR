# Donation Contract

The smart contract exposes multiple methods to handle locked $stNear tokens for 12 months to gain access to our educational program. The rewards generated are used to gamify the educational platform and as a source of income for Stakedemy. At the end of the 12 months, users retrieve the tokens they had locked in our vault.

## 1. Build and Deploy the Contract
You can automatically compile and deploy the contract in the NEAR testnet by running:

```bash
./deploy.sh
```

Once finished, check the `neardev/dev-account` file to find the address in which the contract was deployed:

```bash
cat ./neardev/dev-account
# e.g. dev-1659899566943-21539992274727
```

## 1. Get Number of Donations

`deposit` forwards any attached money to the `beneficiary` while keeping track of it.

`deposit` is a payable method for which can only be invoked using a NEAR account. The account needs to attach money and pay GAS for the transaction.

```bash
# Use near-cli to deposit 1 NEAR
near call <dev-account> deposit --amount 3 --accountId <account>
```

**Tip:** If you would like to `deposit` using your own account, first login into NEAR using:

```bash
# Use near-cli to login your NEAR account
near login
```

and then use the logged account to sign the transaction: `--accountId <your-account>`.


### Methods for stNEAR from Metapool
````
near call meta-v2.pool.testnet deposit_and_stake '{"amount":}' --accountId ejemplo.testnet --deposit 1

near call meta-v2.pool.testnet ft_transfer '{}' --accountId ejemplo.testnet

near view meta-v2.pool.testnet ft_balance_of '{"account_id": "ejemplo.testnet"}'

near call meta-v2.pool.testnet ft_transfer '{"receiver_id": "joehank.testnet", "amount": "1000000000000000000000000", "msg": ""}' --accountId ejemplo.testnet --depositYocto 1 --gas 300000000000000
````