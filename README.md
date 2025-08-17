# System Architecture Overview – MemeCoin Score Platform

This diagram illustrates the **HunterCoin Web3 Chat platform**, which collects, analyzes, and displays meme coin scores for users in real time.

## Users / Traders
- Log in to the platform, check meme coin scores, and interact via Web3 chat.

## Frontend (Web App)
- Provides a dashboard for users to view scores, request updates, and participate in chat.
- Communicates with backend APIs to fetch scores.

## Data Collection Bot
- Collects social media trends, on-chain data via Blockfrost, and Koios adapter data.
- Preprocesses and sends data to the backend for analysis.

## Backend API Service
- Connects the frontend, bot, and AI engine.
- Processes user requests and forwards data to AI for score calculation.

## AI / ML Engine
- Computes NDT Scores for meme coins based on collected data.
- Returns scores, metadata, and chat responses to the backend.

## Data Flow
- Users → Web App → Backend → Bot collects data → AI computes scores → Backend sends results → Users view scores on Web App.

This architecture ensures **transparent, real-time, AI-driven meme coin scoring**, allowing users to **check coin scores and engage with the platform efficiently**.

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
