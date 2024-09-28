# metadvance2

Description
Set up and operate a HyperChain on the Avalanche network with ease. This project offers a straightforward method to initialize, configure, and engage with your own HyperChain.

Getting Started
Install Dependencies
Navigate to your project directory and execute the following command to tidy up all dependencies:

bash
Copy code
go mod tidy
Configure Project Constants
Modify the consts/consts.go file by completing the necessary constants:

go
Copy code
const (
    HRP    = "SakshiChain"
    Name   = "SakshiToken" 
    Symbol = "STKN" 
)
Register Actions
In registry/registry.go, register the CreateAsset and MintAsset actions as shown below:

go
Copy code
consts.ActionRegistry.Register(&actions.CreateAsset{}, actions.UnmarshalCreateAsset, false)
consts.ActionRegistry.Register(&actions.MintAsset{}, actions.UnmarshalMintAsset, false)
Run the VM Locally
Ensure that Go is included in your system's PATH. If it's not, add it using one of the following commands:

bash
Copy code
export PATH=$PATH:$(go env GOPATH)/bin
# OR
export PATH=$PATH:/usr/local/go/bin
Then, execute these commands to run the VM:

bash
Copy code
MODE="run-single" ./scripts/run.sh
./scripts/build.sh
Import Demo Private Key
Import the demo private key provided in the project:

bash
Copy code
./build/token-cli key import demo.pk
./build/token-cli chain import-anr
Interact with Your HyperChain
Mint and Trade
Create Your Asset

Run the following command to create your asset:

bash
Copy code
./build/token-cli action create-asset
Mint Your Asset

Mint the asset using:

bash
Copy code
./build/token-cli action mint-asset
Check Your Balance

View your balance with:

bash
Copy code
./build/token-cli key balance
Terminate the Local Avalanche Network
To stop the local Avalanche network, execute:

bash
Copy code
killall avalanche-network-runner
Help
If you encounter any issues, consult the README file or use the relevant command to access help information.

Authors
Sakshi Sankhala
License
This project is licensed under the MIT License. See the LICENSE file for details.
