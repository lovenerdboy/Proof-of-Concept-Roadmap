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
