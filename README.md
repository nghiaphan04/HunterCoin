```mermaid
graph TD
    %% Users
    User[User or Trader]

    %% Frontend
    WebApp[HunterCoin Web App - Web3 Chat]

    %% Data Collection
    Bot[Data Collector Bot]
    Social[Social Media Data]
    OnChain[On-chain Data via Blockfrost]
    Koios[Koios On-chain Adapter]

    %% Backend & AI
    API[Backend API Service]
    AI[AI ML Engine - Compute NDT Score]

    %% Smart Contracts & Blockchain
    SC[Smart Contract for NFT Minting - CIP68]
    Cardano[Cardano Blockchain]

    %% Connections
    User -->|Login, Check Scores, Chat| WebApp
    WebApp -->|Request Scores or Mint NFT| API
    API -->|Fetch Data| Bot
    Bot --> Social
    Bot --> OnChain
    Bot --> Koios
    Bot -->|Send Collected Data| API
    API -->|Send Data to Analyze| AI
    AI -->|Return NDT Score and Metadata and Chat Response| API
    API -->|Send Mint Request| SC
    SC -->|Mint NFT CIP68| Cardano
    Cardano -->|Return Confirmation| SC
    SC --> API
    API -->|Return NDT Score and Chat Info| WebApp
    WebApp --> User


```
