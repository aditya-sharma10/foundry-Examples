# ⚒️ Foundry-Examples  

This repository demonstrates simple **Solidity smart contracts** along with their corresponding **unit tests** written using **Foundry**.  

The project is designed for:  
- 🟢 Beginners exploring blockchain & smart contracts  
- 🔵 Intermediate developers who want to sharpen their skills in:  
  - Ownership control  
  - Ether transfers  
  - Event handling  
  - Unit testing with Foundry  

---

## 📦 Project Structure 

📂 foundry-Examples
┣ 📂 src # Solidity contracts
┣ 📂 script # Deployment scripts
┣ 📂 test # Unit tests written in Solidity
┗ 📄 README.md # Project documentation

---

## 🚀 Getting Started  

### 1️⃣ Clone the repository  
```bash
git clone https://github.com/aditya-sharma10/foundry-Examples.git
cd foundry-Examples
```

### 2️⃣ Install dependencies

``` Make sure you have Foundry installed:


+ curl -L https://foundry.paradigm.xyz | bash
+ foundryup
```

### 3️⃣ Build the project
```
forge build
```

4️⃣ Run tests
```
forge test
```

###🛠️ Example Contracts
``` 1️⃣ Counter Contract
pragma solidity ^0.8.0;

contract Counter {
    uint256 public number;

    function increment() public {
        number++;
    }

    function decrement() public {
        number--;
    }
}
```
✅ Features:

Increment & decrement functionality

Storage & retrieval of values

Fully tested using Foundry


###2️⃣ Event Contract
```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.30;

contract Event {
    event Transfer(address indexed from, address indexed to, uint256 amount);

    function transfer(address from, address to, uint256 amount) public {
        emit Transfer(from, to, amount);
    }

    function transferMany(address from, address[] calldata to, uint256[] calldata amounts) public {
        for (uint256 i = 0; i < to.length; i++) {
            emit Transfer(from, to[i], amounts[i]);
        }
    }
}
```
###🧪 Example Tests (Using Foundry)
```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.30;

import {Test} from "forge-std/Test.sol";
import {Event} from "../src/Event.sol";

contract EventTest is Test {
    Event public eventContract;

    // Called before each test
    function setUp() public {
        eventContract = new Event();
    }

    // Define the same event signature locally for expectEmit
    event Transfer(address indexed from, address indexed to, uint256 amount);

    // Test single transfer event
    function testTransfer() public {
        vm.expectEmit(true, true, false, true); // check indexed from, to; skip data topics; check value
        emit Transfer(address(1), address(2), 100);

        eventContract.transfer(address(1), address(2), 100);
    }

    // Test multiple transfer events
    function testMultipleEvent() public {
        address ;
        to[0] = address(1);
        to[1] = address(2);
        to[2] = address(3);

        uint256 ;
        amounts[0] = 100;
        amounts[1] = 200;
        amounts[2] = 300;

        // Loop through each expected event
        for (uint256 i = 0; i < to.length; i++) {
            vm.expectEmit(true, true, false, true);
            emit Transfer(address(0xabc), to[i], amounts[i]);
        }

        eventContract.transferMany(address(0xabc), to, amounts);
    }
}
```
✅ Notes / Best Practices:

vm.expectEmit: Sets the expectation for an event before the actual call. Parameters (checkTopic1, checkTopic2, checkTopic3, checkData) allow selective matching of indexed and non-indexed event parameters.

Local event declaration: The test must declare the event locally with the same signature for expectEmit to work.

Multiple event tests: For transferMany, call vm.expectEmit for each event individually.

Naming conventions: Descriptive names improve readability (e.g., eventContract, EventTest).

```
📚 Resources

📖 Foundry Book

🛠 Solidity Docs

🧪 Ethereum Docs

🤝 Contributing

Contributions are welcome! 🎉

Fork this repo

Create a new branch (feature/my-feature)

Commit your changes

Push and open a Pull Request
```


