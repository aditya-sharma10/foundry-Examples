⚡ Foundry Counter

A beginner-friendly Solidity project demonstrating ownership management, Ether transfers, and testing with Foundry cheatcodes.

📌 Overview

The Counter contract is a simple yet practical example for learning:

👤 Ownership control – restrict access to critical functions.

💰 Ether transfers – safely send Ether to the owner.

🛡 Access modifiers – enforce secure usage patterns.

🧪 Testing with Foundry – leverage cheatcodes for robust test coverage.

This project bridges theory and practice, making it ideal for those starting with smart contract development.

📝 Contract Features

✅ Owner Variable – Stores the contract owner as a payable address.
✅ Ownership Transfer – setOwner() lets the current owner transfer ownership.
✅ Secure Ether Transfer – sendVal() sends Ether to the owner, validating the input and transfer success.
✅ Modifier – ownerCheck ensures only the owner can perform restricted actions.
✅ Revert Messages – Provide clarity when conditions fail.

🛠 Technologies

Solidity ^0.8.30

Foundry (Forge & Cast)

forge-std/Test.sol for cheatcodes

🧪 Testing with Foundry

The tests showcase real-world Foundry cheatcode usage:

🎭 vm.prank → Simulates function calls from different addresses.

⚠️ vm.expectRevert → Expects transactions to fail with specific errors.

💵 vm.deal → Assigns Ether balances to addresses for testing transfers.

🏷 vm.label → Labels addresses in traces for easier debugging.

Example test snippet:

function test_Revert_When_NonOwnerCallsSetOwner() public {
    counter.setOwner(payable(address(0x123)));
    assertEq(counter.owner(), address(0x123));

    vm.prank(address(0x456)); // simulate non-owner
    vm.expectRevert("Only owner can call this function");
    counter.setOwner(payable(address(0x789))); // must revert
}

🎯 Purpose

📚 This repository is a learning resource, not production-ready code.
It helps developers practice:

Writing secure Solidity contracts.

Implementing modifiers & access control.

Handling Ether transfers safely.

Building confidence in Foundry testing.

🚀 Quick Start
# Clone repo
git clone https://github.com/your-username/foundry-counter.git
cd foundry-counter

# Install dependencies
forge install

# Build
forge build

# Run tests
forge test -vv

📖 Resources

📘 Foundry Book

🧾 Solidity Docs
