# SPHINX

## Introduction
This project is dedicated to the open-source post-quantum SPHINX blockchain. SPHINX is a blockchain protocol designed to provide secure and scalable solutions in the post-quantum era. The project aims to develop a robust and decentralized network using a Proof of Work (PoW) consensus algorithm initiated by the community.

## Getting Started
To get started with the SPHINX blockchain project, follow the instructions below:

1. Clone the repository: `git clone https://github.com/ChyKusuma/SPHINXPoW.git`
2. Install the necessary dependencies (List the dependencies or provide a link to the installation guide).
3. Explore the codebase to understand the project structure and components.
4. Run the project or make modifications as needed.

## Components

### SPHINX_256 Hash Function
The `SPHINX_256` hash function used in the code is based on [SWIFFTX]([https://link-to-swifftx-docs](https://en.wikipedia.org/wiki/SWIFFT)), which is a cryptographic hash function. It is designed to provide secure hashing capabilities in the post-quantum era. This hash function takes a message as input and produces a fixed-size output of 256 bits.

### calculateHash Function
The `calculateHash` function in the `SPHINXMiningAlgorithm` namespace is used to calculate the hash of a given message with a specified number of required leading zeros. It iterates through nonce values until it finds a hash that meets the difficulty target. The function appends the nonce to the message, calculates the hash using the `SPHINX_256` hash function, and checks if the hash meets the required number of leading zeros.

### meetsDifficultyTarget Function
The `meetsDifficultyTarget` function is a custom function used to check if a given hash meets the difficulty target. It takes the hash and the required number of leading zeros as input and iterates through the hash characters to check if the hash has the required number of leading zeros. It returns `false` if any character is not '0', indicating that the hash does not meet the difficulty target.

### solveNonce Function
The `solveNonce` function in the `SPHINXPoW` namespace is responsible for solving the nonce value for a given data and difficulty level. It iterates through nonce values and combines them with the data to mine a block using the `mineBlock` function from the `Miner` class. It then checks if the mined block's hash meets the difficulty target by calling the `meetsDifficultyTarget` function.

### adjustDifficulty Function
The `adjustDifficulty` function is used to dynamically adjust the difficulty level based on the network hash rate and other factors. It calculates the expected number of blocks per day, adjusts the target blocks per day for developer mining, and calculates the network target hash rate. It then adjusts the difficulty target by reducing or increasing the target based on the network hash rate and a predefined adjustment factor.

## Contributing
We welcome contributions from the developer community to enhance the SPHINX blockchain project. If you are interested in contributing, please follow the guidelines below:

1. Fork the repository on GitHub.
2. Create a new branch for your feature or bug fix: `git checkout -b feature/your-feature-name` or `git checkout -b bugfix/your-bug-fix`.
3. Make your modifications and ensure the code remains clean and readable.
4. Write tests to cover the changes you've made, if applicable.
5. Commit your changes: `git commit -m "Description of your changes"`.
6. Pushthe branch to your forked repository: `git push origin your-branch-name`.
7. Open a pull request against the main repository, describing your changes and the problem it solves.

## License
Specify the license under which the project is distributed (MIT License).

## Contact
If you have any questions, suggestions, or feedback regarding the SPHINX blockchain project, feel free to reach out to us at [sphinxfounders@gmail.com](mailto:sphinxfounders@gmail.com).
