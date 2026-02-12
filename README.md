# CargoChain

**CargoChain** is a decentralized supply chain application (dApp) built on the **Stellar network** using **Soroban smart contracts**.

## 📖 Project Description

CargoChain allows for a **conditional escrow** mechanism for logistics and transportation.
1.  **Seller** and **Buyer** agree on a shipment.
2.  **Buyer** deposits funds (XLM/USDC) into a smart contract.
3.  Funds are **locked** until the shipment reaches its destination.
4.  An **IoT Device** (simulated) updates the shipment's GPS location.
5.  Once the shipment is close enough to the target coordinates, the smart contract **automatically releases** the funds to the Seller.

This eliminates the need for trusted intermediaries and ensures that payment is only made upon successful delivery.

### Key Features
-   **Smart Contract Escrow**: Logic handles funds securely on-chain.
-   **GPS Location Verification**: Funds are released based on geographic proximity.
-   **Industrial Dashboard**: Real-time monitoring of sensor data (Temperature, Location).
-   **Freighter Wallet Integration**: Secure signing of transactions.

---

## ⚙️ Setup (Installation)

Follow these steps to set up the project locally.

### Prerequisites
-   **Node.js** (v18 or later)
-   **npm** or **yarn**
-   **Freighter Wallet** extension for your browser (set to **Testnet**)
-   *(Optional)* Rust & Soroban CLI (for contract development)

### Installation

1.  Clone the repository:
    ```bash
    git clone https://github.com/your-username/CargoChain.git
    cd CargoChain
    ```

2.  Install dependencies:
    ```bash
    npm install
    ```

---

## 🚀 Usage

### 1. Configure Environment

Create a `.env.local` file in the root directory (copy from `.env.local.example` if available).

```env
# Contract ID for the deployed CargoChain Smart Contract
NEXT_PUBLIC_CONTRACT_ID=CBWRT53NSNOCQ4CFZEDM5QVP5P2MKDTLX7HOHXCW3Q6FOPGNGHXOGYTR

# Stellar Testnet RPC URL
NEXT_PUBLIC_RPC_URL=https://soroban-testnet.stellar.org

# (Optional) Token Contract ID - Leave empty to use Native XLM
NEXT_PUBLIC_TOKEN_ID=
```

### 2. Start the Application

Run the development server:

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

### 3. Using the dApp

1.  **Connect Wallet**: Click the "Connect Wallet" button in the top right.
2.  **Buyer Role**:
    -   Go to the control panel.
    -   Click **"Deposit Funds"** to lock your payment in the contract.
    -   Confirm the transaction in Freighter.
3.  **IoT/Carrier Role**:
    -   Click **"Simulate IoT Signal"** to update the shipment location (e.g., reaching Berlin).
    -   Confirm the transaction.
4.  **Completion**:
    -   Watch the status change to **"RELEASED"**.
    -   Funds are transferred to the Seller.

---

## 🛠️ Project Structure

-   `app/`: Next.js App Router pages.
-   `components/`: React UI components (SensorReadout, EscrowControl, etc.).
-   `contracts/`: Rust source code for the Soroban smart contract.
-   `services/`: Helper functions to interact with the blockchain (`soroban.ts`).

## 📜 License
This project is for educational purposes.
