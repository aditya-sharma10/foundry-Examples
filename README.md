# ⚒️ Foundry-Examples  

This repository demonstrates a simple **Solidity smart contract** named `Counter` along with its corresponding **unit tests** written using **Foundry**.  

The project is designed for:  
- 🟢 Beginners exploring blockchain & smart contracts  
- 🔵 Intermediate developers who want to sharpen their skills in:  
  - Ownership control  
  - Ether transfers  
  - Unit testing with Foundry  

---

## 📦 Project Structure  

📂 foundry-Examples
┣ 📂 src # Solidity contracts
┣ 📂 script # Deployment scripts
┣ 📂 test # Unit tests written in Solidity
┗ 📄 README.md # Project documentation

yaml
Copy code

---

## 🚀 Getting Started  

### 1️⃣ Clone the repository  
```bash
git clone https://github.com/aditya-sharma10/foundry-Examples.git
cd foundry-Examples
2️⃣ Install dependencies
Make sure you have Foundry installed:

bash
Copy code
curl -L https://foundry.paradigm.xyz | bash
foundryup
3️⃣ Build the project
bash
Copy code
forge build
4️⃣ Run tests
bash
Copy code
forge test
🛠️ Example: Counter Contract
solidity
Copy code
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
✅ Features:

Increment & decrement functionality

Storage & retrieval of values

Fully tested using Foundry

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

📜 License
MIT License © 2025 Aditya Sharma
