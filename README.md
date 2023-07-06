# SPHINXPoW

## Introduction
This project is dedicated to the open-source post-quantum SPHINX blockchain. SPHINX is a blockchain protocol designed to provide secure and scalable solutions in the post-quantum era. The project aims to develop a robust and decentralized network using a Proof of Work (PoW) consensus algorithm initiated by the community. We thrilled to introduce a new design for Proof-of-Work operation.

## Getting Started
To get started with the SPHINX blockchain project, follow the instructions below:

1. Clone the repository: `git clone https://github.com/ChyKusuma/SPHINXPoW.git`
2. Install the necessary dependencies (List the dependencies or provide a link to the installation guide).
3. Explore the codebase to understand the project structure and components.
4. Run the project or make modifications as needed.

## Components of SPHINXPoW

#### SPHINX_256 Hash Function
The `SPHINX_256` hash function used in the code is based on [SWIFFTX](https://en.wikipedia.org/wiki/SWIFFT)
, which is a cryptographic hash function. It is designed to provide secure hashing capabilities in the post-quantum era. This hash function takes a message as input and produces a fixed-size output of 256 bits.

##### A lattice-based construction
In cryptography, SWIFFT is a collection of provably secure hash functions based on the concept of the fast Fourier transform (FFT). It distinguishes itself by providing a mathematical proof of its security and utilizing the LLL basis reduction algorithm. SWIFFT's security is linked to the difficulty of finding short vectors in cyclic/ideal lattices, making collision finding a challenging task. This property offers a stronger security guarantee compared to most other cryptographic hash functions.

Despite its provable security and desirable cryptographic and statistical properties, SWIFFT is not designed as a general-purpose hash function. It does not function as a pseudorandom function and is not suitable for applications requiring a random oracle. While SWIFFT achieves a reasonable throughput of 40Mbit/s on a 3.2 GHz Intel Pentium 4, it is less efficient than traditional hash functions that lack provable collision-resistance. As a result, SWIFFT finds practical use in scenarios where the proof of collision-resistance holds significant value, such as long-term trustworthy digital signatures.

A modified version of SWIFFT called SWIFFTX was proposed as a candidate for the SHA-3 function in the NIST hash function competition. However, it was not selected in the first round of evaluations. Presently, "Lattice-Based" cryptographic algorithms are gaining attention as promising solutions to mitigate security risks posed by quantum computers.

We present a problem that is as difficult as finding approximate short vectors in certain n-dimensional lattices. The hardness of this problem is comparable to finding γ(n)-approximate short vectors, where γ(n) is a function that grows logarithmically with n.

The problem becomes challenging due to the specific properties of the lattices and requires preprocessing of the number field to achieve the desired connection factors. Although the decision problems related to these lattices are not known to be NP-hard and can be solved in polynomial time, the search approximation problems remain highly complex. Even with advancements in computational number theory, the algorithms for ideal lattices perform similarly to those for general lattices.

To achieve the best connection factor, we instantiate our constructions using infinite families of number fields with constant root discriminant. While such families exist and can be computed, efficient constructions are still an area of research. Previous approaches were limited to a connection factor of γ(n) = O(n), but our work aims to improve upon this.

Our results focus on lattices that correspond to ideals in the ring of integers of an algebraic number field. We address the problem of finding approximate shortest vectors in these lattices. Additionally, we establish reductions between different worst-case problems on ideal lattices, demonstrating relationships between the shortest vector problem and the closest vector problem. These reductions are similar to those observed for general lattices.


### calculateHash Function
The `calculateHash` function in the `SPHINXMiningAlgorithm` namespace is used to calculate the hash of a given message with a specified number of required leading zeros. It iterates through nonce values until it finds a hash that meets the difficulty target. The function appends the nonce to the message, calculates the hash using the `SPHINX_256` hash function, and checks if the hash meets the required number of leading zeros.

### meetsDifficultyTarget Function
The `meetsDifficultyTarget` function is a custom function used to check if a given hash meets the difficulty target. It takes the hash and the required number of leading zeros as input and iterates through the hash characters to check if the hash has the required number of leading zeros. It returns `false` if any character is not '0', indicating that the hash does not meet the difficulty target.

### solveNonce Function
The `solveNonce` function in the `SPHINXPoW` namespace is responsible for solving the nonce value for a given data and difficulty level. It iterates through nonce values and combines them with the data to mine a block using the `mineBlock` function from the `Miner` class. It then checks if the mined block's hash meets the difficulty target by calling the `meetsDifficultyTarget` function.

### adjustDifficulty Function
The `adjustDifficulty` function is used to dynamically adjust the difficulty level based on the network hash rate and other factors. It calculates the expected number of blocks per day, adjusts the target blocks per day for developer mining, and calculates the network target hash rate. It then adjusts the difficulty target by reducing or increasing the target based on the network hash rate and a predefined adjustment factor.

### Mathematical Properties
The SPHINXPoW algorithm includes several mathematical operations for nonce calculation and difficulty adjustment. Here are some of the mathematical properties used in the code:

- `multiply` Function: This inline function is used to multiply the upper and lower digits of a number. It takes a number `k` as input, splits it into upper and lower digits, and multiplies them. If either the upper or lower digits are zero, the function returns `k` as it is.

- `extract_32_digits` Function: This inline function extracts 32 digits from a givennumber `k`. It uses mathematical operations like `frexp`, `modf`, and casting to extract the desired digits.

- `select_and_do_operation` Function: This inline function selects and performs mathematical operations based on a sequence number (`seq`) and a given number `k`. It supports operations like division, multiplication, addition, square root, exponential, trigonometric functions, logarithmic functions, and others. The function checks the sequence number and performs the corresponding operation on `k`. If the sequence number does not match any operation, it returns a default value of 1.

### isValidHash Function
The `isValidHash` function is used to check if a given hash has the required number of leading zeros. It iterates through the hash characters and checks if the number of leading zeros matches the required number. It returns `true` if the hash is valid, indicating that it meets the required leading zeros.

## Contributing
We welcome contributions from the developer community to enhance the SPHINX blockchain project. If you are interested in contributing, please follow the guidelines below:

1. Fork the repository on GitHub.
2. Create a new branch for your feature or bug fix: `git checkout -b feature/your-feature-name` or `git checkout -b bugfix/your-bug-fix`.
3. Make your modifications and ensure the code remains clean and readable.
4. Write tests to cover the changes you've made, if applicable.
5. Commit your changes: `git commit -m "Description of your changes"`.
6. Push the branch to your forked repository: `git push origin your-branch-name`.
7. Open a pull request against the main repository, describing your changes and the problem it solves.

## License
Specify the license under which the project is distributed (MIT License).

## Contact
If you have any questions, suggestions, or feedback regarding the SPHINX blockchain project, feel free to reach out to us at [sphinxfounders@gmail.com](mailto:sphinxfounders@gmail.com).
