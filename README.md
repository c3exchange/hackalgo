# C3 Bounty - Single Transaction Deposit

## Overview

* **Short Description**: The objective of this bounty is to develop the creation of a deposit operation of Algos/ASAs to a smart contract using a single transaction.
* **Bounty**: 5000 ALGO tokens _(US residents will receive USDCa and have to opt-in to receive the asset in their wallet)_
* **Estimated Time Commitment**: 2 Weeks
(For the following info, please also add the according labels to the issue)
* **Category**: Development
* **Experience Level**: Beginner / Intermediate
* **Mode**: Traditional


## Description

### What is this task?
How deposit works now:
- User compiles a payment/asset transfer transaction of the desired amount
- User compiles an deposit app call transaction
- User group them, signs them once they are grouped, sends them
- Contract verifies that the group is coherent (i.e.: by checking that the sender is the same, the receiver is the address of the contract, by reading the deposited amount in the first txn, ...)
- Approves

Possible solution (developers can use this solution but we will value other ideas and if you use this solution we will value the minimal user security exposure) using rekey feature:
- User compiles a deposit app call transaction and sets the rekeyTo (LINK: https://developer.algorand.org/docs/get-details/transactions/transactions/#common-fields-header-and-type) field to the address of the contract
- Contract checks that the rekey is valid (i.e.: is set to the address of the contract) and reads the desired asset / amount
- Contract compiles an inner payment/asset transfer transaction from the user's address to the contract's address because it is allowed to by the previous rekeyTo. It also gives back authority over the user's address to the user's private key by setting the rekeyTo field to the original user.
- This is the trickiest bit because we want to rekey the user address (that is currently in our authority) and not the contract address (not sure if that's possible. This topic definitely deserves more research)
- Approves
### What are the requirements for the bounty taker?
Algorand Smart Contracts development skills

## Deliverables
### 1. Deliverable Name (e.g. the project code repository)

**Description**

- Contract (in Py Teal language)
- Description of how to create the transactions to call the contract
- An example of executing the contract using the Node.Js SDK

**Judging Criteria and Metrics** (optional)
  User Friendship - Fee Consumption

_Submission Procedure_
 * Make a submission on Gitcoin with the project link.




## Other Requirements
For questions, reach out to [HackAlgo on Discord](https://discord.gg/5zjRMSQM).

* **IMPORTANT** As gitcoin does not provide a way for us to contact you, after taking the bounty, please subscribe to the bounty issue to receive comments notifications from us. (You can find a "View on Github" button in this page to go to the bounty issue)
* Taking this bounty task means you have agreed to our [Bounty Agreement terms and policies](https://github.com/algorandfoundation/grow-algorand/blob/master/bounty-agreement.md).
* All project codes should be published on GitHub, with an [MIT license](https://opensource.org/licenses/MIT) or [Apache V2 license](https://www.apache.org/licenses/LICENSE-2.0).
* All contributions/PRs to public (Algorand) repositories should be open source and should follow the contributions rules of the relevant repository.
* All non-code documents should be using Markdown format.
* In the project description or repository readme, there should be a proper security notice. E.g., it should tell the visitor the project is not audited and should not be used in a production environment.
* You are not eligible to receive additional rewards through other Algorand programs like the [developer ambassadors](https://algorand.foundation/developers/dev-ambassadors) program.
