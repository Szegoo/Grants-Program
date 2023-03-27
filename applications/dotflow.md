# Dotflow

- **Team Name:** Sergej Sakac
- **Payment Address:** 0x1e86CD18E4443B5f57b0133077954Cd84896964d (USDC)
- **[Level](https://github.com/w3f/Grants-Program/tree/master#level_slider-levels):** 2

## Project Overview :page_facing_up:

### Overview

#### Problem
We can most certainly agree that the future is multi-chain. As such, it is not uncommon for users to hold multiple accounts across various chains for reasons such as distinct address formats and security. However, this practice presents a challenge in managing multiple addresses. Adding to the complexity is the need to verify the address of the intended recipient, as it may have changed over time.

In summary, there are two key challenges to address: the management of multiple addresses and making sure the addresses of the recepients did not change in the meantime.

To mitigate these challenges, we aim to simplify the user experience by abstracting away the complexity of address management.

### Project Details

Our project will comprise of two smart contracts coded in ink!, and a React.js-based user interface.

The first contract will store users' address-related data in an entity called `Identity`. Each user will have their own `Identity`, which will contain their addresses across different chains. The Identity creators will be responsible for updating their addresses if any changes occur. Every Identity will be assigned a unique `IdentityId`, which will serve a crucial purpose in the second contract.

Additionally, this contract will feature a function that, based on input arguments, will return the appropriate destination address for fund transfers. This function will mainly be used by the user interface.

The second contract will be an address book that enables users to store the `IdentityId`s of the people they are most frequently engaged with . Each user will have the option to create their own address book, where they can add a nickname to each identity to differentiate them easily.

The UI we are going to build will serve the purpose of interacting with both of our contracts. Users will be able to create an identity and customize the addresses of their identity. Using the UI users will also be able to create their address book and customize it. The most important functionality the UI will provide will be routing.
When a user wants to transfer some funds to an identity the user will only have to worry about the token, start and destination chain and the identity they want to send the token to. Based on all of this the UI will query the first contract and based on that create a transaction that will route the funds to the proper address.

In case the start and destination chain are not the same, the UI will create an XCM message that will route the funds to the proper blockchain.

Our ink! smart contracts will be deployed on the Astar network,

### Ecosystem Fit

This project fits perfectly with the Polkadot ecosystem because it has everything we need to make it work. Polkadot is a multi-chain network, so a lot of users have different addresses on different chains for the same reasons we mentioned earlier. That's why the problems we talked about are important in this ecosystem.

XCM is going to be a core component of our project since it'll help us transfer funds between the parachains and the relay chain.

#### Target Audience
Our target audience is people who deal with sending assets frequently over the Polkadot network.

## Team :busts_in_silhouette:

### Team members

- Sergej Sakac [Szegoo](https://github.com/Szegoo)
- Names of team members

### Contact

- **Contact Name:** Sergej Sakac
- **Contact Email:** sakacszergej@gmail.com
- **Website:** https://github.com/Szegoo

### Legal Structure
We will be working as two individuals
- **Registered Address:** N/A
- **Registered Legal Entity:** N/A

### Team's experience

#### [Sergej Sakac](https://github.com/Szegoo) 
- More than three years of programming experience
- Active contributor to [Substrate](https://github.com/paritytech/substrate/pulls?q=is%3Apr+author%3ASzegoo)
- Member of the [fellowship](https://github.com/polkadot-fellows/seeding/pull/36)
- Contributor to [rmrk-pallets](https://github.com/rmrk-team/rmrk-substrate/pulls?q=is%3Apr+is%3Aclosed+author%3ASzegoo)


### Team Code Repos

- https://github.com/<your_organisation>/<project_1>
- https://github.com/<your_organisation>/<project_2>

Please also provide the GitHub accounts of all team members. If they contain no activity, references to projects hosted elsewhere or live are also fine.

- https://github.com/Szegoo

### Team LinkedIn Profiles (if available)

- http://linkedin.com/in/sergej-sakac-334a47252

## Development Roadmap :nut_and_bolt:

### Overview

- **Total Estimated Duration:** 2,5 months
- **Full-Time Equivalent (FTE):**  1.5 FTE
- **Total Costs:** 

### Milestone 1 Example — Basic functionality

- **Estimated duration:** 1 month
- **FTE:**  1,5
- **Costs:** 

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| **0a.** | License | MIT |
| **0b.** | Documentation | Both contracts and the website code will be well documented and open for everybody to check. The UI will have a simple UI that will be intuitive to use. |
| **0c.** | Testing and Testing Guide | Both ink! smart contracts will be well tested before deployed. The functionality for generating XCM messages will very well tested to make sure the funds are always transfered to the proper destination. |
| **0d.** | Docker | We will provide a Dockerfile that can be used to test all the functionality delivered with this milesone. |
| 1. | Identity Contract | We will build the Identity contract that was explained above. This includes functionality for creating identities, storing identity information, updating identity information. We will also implement the routing function that will return the destination address based on input arguments. |
| 2. | UI for Identity Contract | We will make a UI that will allow users to interact with the Identity Contract. Users will be able to access all of the functionality from the Identity Contract by using this UI |


### Milestone 2 Example — Additional features

- **Estimated Duration:** 1,5 month
- **FTE:**  1,5
- **Costs:** 

| Number | Deliverable | Specification |
| -----: | ----------- | ------------- |
| **0a.** | License | MIT |
| **0b.** | Documentation | Both contracts and the website code will be well documented and open for everybody to check. The UI will have a simple UI that will be intuitive to use. |
| **0c.** | Testing and Testing Guide | Both ink! smart contracts will be well tested before deployed. The functionality for generating XCM messages will very well tested to make sure the funds are always transfered to the proper destination. |
| **0d.** | Docker | We will provide a Dockerfile that can be used to test all the functionality delivered with this milesone. |
| 0e. | Article | We will publish a Medium article that explains all the things done in the grant. |
| 1. | Address Book Contract | We will write the code for the address book contract. This will contain the functionality for creating an address book, adding and modifying addresses. |
| 2. | Routing functionality. | We will write the logic for constructing XCM messages that will route the funds to the proper address. In case the destination chain is same as the start there will just be a simple transaction. The code for this will be stored on the frontend.
| 3. | UI for Address Book | We will make a UI that will allow users to interact with the Address Book Contract. Users will be able to access all of the functionality from the Address Book contract by using this UI |
| 4. | UI for sending tokns | We will make a UI that will allow users to send tokens by setting the destination to some `IdentityId`. The UI will abstract everything away and take care of routing. |


## Future Plans

For this grant our plan is to make it possible to route tokens based on the destination parachain.

Our future plan is to expand this and add more specifications based on which the tokens can be transfered. Our current ideas are:

- Route tokens based on the sender
- Route tokens based on the amount
- Route the tokens based on the token itself

## Additional Information :heavy_plus_sign:

**How did you hear about the Grants Program?** GitHub
