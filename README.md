# Proof-of-Concept-Roadmap
# Drosera Trap Proof of Concept (PoC) Roadmap





## Step 1: Come Up With a Trap Idea

The **first thing** to do when creating a PoC is to come up with a **Trap idea**.

### 📚 Learn What a Trap Is
To understand what makes a Trap, a Trap, go through the following resources:

- [Drosera Docs](http://dev.drosera.io)
- [Drosera Medium Blog](https://medium.com/@droseranetwork)
- [Drosera Workshops (Intro)](https://github.com/drosera-network/drosera-workshops/tree/main/workshops/intro)

Feed these resources to your **LLM (e.g., ChatGPT, Grok, Claude)** to help it learn and understand how a Trap is built.

> **Note:**  
> A **Trap** must always contain both a `collect` and a `shouldRespond` function — otherwise, it’s not truly a Trap.

---

## 💡 Step 2: Find Inspiration

Your Trap needs to be **unique** and have a **real-world use case**.

You can find inspiration by exploring:
- [Ethereum DApps](https://ethereum.org/en/dapps/)
- **EVM-compatible DeFi protocols**

(You can also share these with your LLM so it understands how to integrate with DApps.)

---

## 🧩 Step 3: Generate a PoC Trap

Once you’ve gathered your research and ideas, instruct your LLM to generate a **simple, unique, and useful PoC** Trap.  
It should be designed to interact with **an Ethereum DApp or any EVM-compatible DeFi protocol**.

> ⚠️ **Important Guidelines**
> - Ensure the Trap is supported by **Hoodi Network**
> - Use **Solidity version 0.8.20**
> - **Avoid constructor arguments** (unless absolutely necessary)
> - Your Trap interface **must include** the following:

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

import {ITrap} from "drosera-contracts/interfaces/ITrap.sol";
```
---

##  Step 4: Generate a Response Contract

After creating your Trap contract, ask your LLM to generate a Response Contract.
This contract defines the action to be taken when the Trap triggers a response.

---
##  Step 5: Create a `drosera.toml` file

Once you have both your Trap and Response Contract, generate a drosera.toml configuration file.
Here’s an example template:
```solidity
ethereum_rpc = "https://ethereum-hoodi-rpc.publicnode.com"
drosera_rpc = "https://relay.hoodi.drosera.io"
eth_chain_id = 560048
drosera_address = "0x91cB447BaFc6e0EA0F4Fe056F5a9b1F14bb06e5D"

[traps]

[traps.mytrap]
path = "out/DiscordNameTrap.sol/Trap.json"
response_contract = "0x25E2CeF36020A736CF8a4D2cAdD2EBE3940F4608"
response_function = "respondWithDiscordName(string)"
cooldown_period_blocks = 33
min_number_of_operators = 1
max_number_of_operators = 2
block_sample_size = 10
private_trap = true
whitelist = ["YOUR_OPERATOR_ADDRESS"]
```
Replace the values with those specific to your Trap.

---
##  Step 6: Deploy the Response Contract

You can deploy your Response Contract easily using [Remix IDE](https://remix.ethereum.org/).

> - **If you face deployment issues, copy your contract and error message, then ask your LLM to fix the specific error only.**

Once deployed, you’ll get a contract address update your `drosera.toml` file with that address under `response_contract`.

---

##  Step 7: Files You Should Have Ready

By this stage, you should have three key files ready (or more, depending on your Trap type):

 -> Solidity Trap Code

 -> Response Contract

 -> drosera.toml Configuration

---
##  🚀 Step 8: Deploy on Your VPS

Now it’s time to deploy your Trap on your VPS.

The process is similar to deploying a Cadet or Corporal Trap, except:

Your Trap code and drosera.toml will differ.

You won’t need to view a list of Discord names because it’s not a DiscordNameTrap.

---
##  🧰 Step 9: Troubleshooting
 
During the `forge build` or `drosera dryrun` you might encounter errors.

Here’s how to fix them:

Copy the error message and the Trap code that caused it.

Paste both (in quotes) into your LLM and ask it to fix only the stated error.

Replace the old code with the corrected one.

Run your `forge build` again.

Once your `forge build` works successfully:

Ask if your response contract or response function in `drosera.toml` needs any adjustment.

Repeat until your `drosera dryrun` passes.

If it still doesn’t, go back to the drawing board and refine your Trap logic.

---
##   Step 10: Final Deployment Steps

Once your dry run works, you’re almost done!

✅ Final Tasks:

1. Generate your Trap address

2. Opt-in your operator

3. Reload your configuration

4. Check proof of liveness

5. Cook up a GitHub repo

6. Create a support ticket and submit

> - 🧡 Job’s done, thanks for playing, kek!
> - For a visual reference, check out @Reiji4kt’s [video tutorial](https://x.com/Reiji4kt/status/1973679261547413736).


