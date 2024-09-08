
# Project: Create a Custom Subnet

This project demonstrates how to create a custom virtual machine to enable users to mint and transfer tokens using the HyperSDK framework. The HyperSDK allows you to build a custom blockchain tailored to your specific needs, including token creation, transfer, and managing trading assets through order books.

## Prerequisites

Ensure you have the following installed before starting the project:

1. **WSL (Windows Subsystem for Linux)**: This project is developed on Ubuntu using WSL.
2. **Go Programming Language**: 
   Install Go by running:
   ```bash
   sudo snap install go --classic
   ```
   Verify installation with:
   ```bash
   go version
   ```
3. **GCC (GNU Compiler Collection)**:
   Install GCC on WSL:
   ```bash
   sudo apt update
   sudo apt install build-essential
   ```
   Verify the installation:
   ```bash
   gcc --version
   ```

## Installation Steps

1. **Clone the repository**:
   ```bash
   git clone https://github.com/NikhTheTech/Create-a-Custom-Subnet-main.git
   ```
2. **Open the repository in VS Code** (from Ubuntu terminal):
   ```bash
   code .
   ```
3. **Install dependencies**:
   Open a terminal in VS Code and run:
   ```bash
   go mod tidy
   ```
4. **Ensure Go is on your path**:
   ```bash
   export PATH=$PATH:$(go env GOPATH)/bin
   ```
   If it doesn't work, try:
   ```bash
   export PATH=$PATH:/usr/local/go/bin
   ```

## Running the Project

1. **Launch the Subnet**:
   ```bash
   MODE="run-single" ./scripts/run.sh
   ```
   (This may take a few minutes.)

2. **Build the project**:
   ```bash
   ./scripts/build.sh
   ```
   The compiled CLI will be in `./build/token-cli`.

3. **Import the demo private key**:
   ```bash
   ./build/token-cli key import demo.pk
   ./build/token-cli chain import-anr
   ```

4. **Interact with the HyperChain**:
   - **Create an asset**:
     ```bash
     ./build/token-cli action create-asset
     ```
   - **Mint your asset**:
     ```bash
     ./build/token-cli action mint-asset
     ```
   - **View balance**:
     ```bash
     ./build/token-cli key balance
     ```
   - **Transfer tokens**:
     ```bash
     ./build/token-cli action transfer
     ```
   - **Create an order**:
     ```bash
     ./build/token-cli action create-order
     ```
   - **Fill an order**:
     ```bash
     ./build/token-cli action fill-order
     ```
   - **Close an order**:
     ```bash
     ./build/token-cli action close-order
     ```

5. **Shut down the network**:
   ```bash
   killall avalanche-network-runner
   ```

## Watch Activity in Real-Time

Run the following to watch on-chain activity in real time:
```bash
./build/token-cli chain watch
```

## Acknowledgements

This project is based on the [TokenVM](https://github.com/Metacrafters/tokenvm.git). Special thanks to the Metacrafters team for their contributions to the blockchain community.

--- 

You can modify or adjust it as needed for your project!
