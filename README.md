# 🌾 Blockchain-Based Supply Chain Transparency for Agricultural Produce

A complete full-stack blockchain application with modern UI, smooth animations, and professional dashboards for agricultural supply chain transparency.

![License](https://img.shields.io/badge/license-MIT-green)
![Solidity](https://img.shields.io/badge/Solidity-^0.8.20-blue)
![Node](https://img.shields.io/badge/Node-v18+-green)
![React](https://img.shields.io/badge/React-18.2-blue)

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Configuration](#configuration)
- [Running the Application](#running-the-application)
- [Smart Contract Deployment](#smart-contract-deployment)
- [API Documentation](#api-documentation)
- [User Roles](#user-roles)
- [Screenshots](#screenshots)
- [Contributing](#contributing)
- [License](#license)

## 🎯 Overview

This project implements a blockchain-based supply chain transparency system for agricultural produce. It enables complete traceability from farmer to consumer with immutable records stored on the blockchain.

### Key Actors

1. **Farmer** - Creates batches and uploads produce information
2. **Distributor** - Accepts and transfers batches
3. **Transport** - Manages shipping and updates
4. **Retailer** - Confirms arrivals and quality checks
5. **Consumer** - Views complete product history via QR codes

## ✨ Features

### Blockchain Features
- ✅ Solidity smart contracts (^0.8.20)
- ✅ Role-based access control (RBAC)
- ✅ Immutable batch tracking
- ✅ Complete ownership history
- ✅ Quality inspection records
- ✅ Testnet deployment ready

### Backend Features
- ✅ RESTful API with Express.js
- ✅ MongoDB database integration
- ✅ JWT authentication
- ✅ IPFS file storage
- ✅ QR code generation
- ✅ Ethers.js blockchain integration

### Frontend Features
- ✅ Modern React.js application
- ✅ Tailwind CSS styling
- ✅ Framer Motion animations
- ✅ Role-based dashboards
- ✅ Responsive design
- ✅ QR code scanning
- ✅ Interactive progress tracker
- ✅ Real-time batch updates

## 🛠️ Tech Stack

### Blockchain
- **Solidity** ^0.8.20
- **Hardhat** - Development environment
- **Ethers.js** - Blockchain interaction
- **OpenZeppelin** - Security standards

### Backend
- **Node.js** - Runtime environment
- **Express.js** - Web framework
- **MongoDB** - Database
- **Mongoose** - ODM
- **JWT** - Authentication
- **IPFS** - Decentralized storage
- **QRCode** - QR generation

### Frontend
- **React.js** 18.2 - UI library
- **React Router** - Routing
- **Tailwind CSS** - Styling
- **Framer Motion** - Animations
- **Lucide React** - Icons
- **Axios** - HTTP client
- **Chart.js** - Data visualization

## 📁 Project Structure

```
├── blockchain/               # Smart contracts & Hardhat
│   ├── contracts/
│   │   └── SupplyChain.sol
│   ├── scripts/
│   │   └── deploy.js
│   ├── hardhat.config.js
│   └── package.json
│
├── backend/                  # Express API server
│   ├── config/
│   │   └── db.js
│   ├── controllers/
│   │   ├── authController.js
│   │   ├── batchController.js
│   │   └── userController.js
│   ├── middleware/
│   │   ├── auth.js
│   │   └── roles.js
│   ├── models/
│   │   ├── User.js
│   │   └── Batch.js
│   ├── routes/
│   │   ├── authRoutes.js
│   │   ├── batchRoutes.js
│   │   └── userRoutes.js
│   ├── services/
│   │   ├── blockchainService.js
│   │   ├── ipfsService.js
│   │   └── qrService.js
│   ├── server.js
│   └── package.json
│
└── frontend/                 # React dashboard
    ├── public/
    ├── src/
    │   ├── components/
    │   │   ├── Button.js
    │   │   ├── Card.js
    │   │   ├── Modal.js
    │   │   ├── Navbar.js
    │   │   ├── ProgressTracker.js
    │   │   └── LoadingSpinner.js
    │   ├── context/
    │   │   ├── AuthContext.js
    │   │   └── BlockchainContext.js
    │   ├── pages/
    │   │   ├── Auth/
    │   │   │   ├── Login.js
    │   │   │   └── Register.js
    │   │   ├── Dashboard/
    │   │   │   ├── FarmerDashboard.js
    │   │   │   ├── DistributorDashboard.js
    │   │   │   ├── TransportDashboard.js
    │   │   │   ├── RetailerDashboard.js
    │   │   │   └── ConsumerDashboard.js
    │   │   ├── BatchDetails.js
    │   │   └── QRScan.js
    │   ├── App.js
    │   └── index.js
    ├── tailwind.config.js
    └── package.json
```

## 🚀 Installation

### Prerequisites

- Node.js v18+ and npm
- MongoDB (local or Atlas)
- MetaMask or similar Web3 wallet
- IPFS node (optional, for local development)

### 1. Clone the Repository

```bash
git clone <repository-url>
cd "Blockchain-Based Supply Chain Transparency for Agricultural Produce"
```

### 2. Install Blockchain Dependencies

```bash
cd blockchain
npm install
```

### 3. Install Backend Dependencies

```bash
cd ../backend
npm install
```

### 4. Install Frontend Dependencies

```bash
cd ../frontend
npm install
```

## ⚙️ Configuration

### 1. Blockchain Configuration

Create `blockchain/.env`:

```env
SEPOLIA_RPC_URL=https://sepolia.infura.io/v3/YOUR_INFURA_PROJECT_ID
MUMBAI_RPC_URL=https://polygon-mumbai.g.alchemy.com/v2/YOUR_ALCHEMY_KEY
PRIVATE_KEY=your_private_key_here
ETHERSCAN_API_KEY=your_etherscan_api_key
```

### 2. Backend Configuration

Create `backend/.env`:

```env
NODE_ENV=development
PORT=5000

# MongoDB
MONGODB_URI=mongodb://localhost:27017/supply-chain

# JWT
JWT_SECRET=your_jwt_secret_key_change_in_production
JWT_EXPIRE=7d

# Blockchain
BLOCKCHAIN_RPC_URL=http://127.0.0.1:8545
CONTRACT_ADDRESS=your_contract_address_after_deployment
BLOCKCHAIN_PRIVATE_KEY=your_private_key_for_transactions

# IPFS
IPFS_URL=http://127.0.0.1:5001
IPFS_GATEWAY=https://ipfs.io/ipfs

# Frontend
FRONTEND_URL=http://localhost:3000
```

### 3. Frontend Configuration

Create `frontend/.env`:

```env
REACT_APP_API_URL=http://localhost:5000/api
REACT_APP_CONTRACT_ADDRESS=your_contract_address_after_deployment
REACT_APP_RPC_URL=http://127.0.0.1:8545
REACT_APP_IPFS_GATEWAY=https://ipfs.io/ipfs
```

## 🏃 Running the Application

### Step 1: Start Local Blockchain

```bash
cd blockchain
npx hardhat node
```

This starts a local Ethereum network on `http://127.0.0.1:8545`

### Step 2: Deploy Smart Contract

In a new terminal:

```bash
cd blockchain
npx hardhat run scripts/deploy.js --network localhost
```

Copy the contract address from the output and update:
- `backend/.env` → `CONTRACT_ADDRESS`
- `frontend/.env` → `REACT_APP_CONTRACT_ADDRESS`

### Step 3: Start MongoDB

Make sure MongoDB is running:

```bash
# If using local MongoDB
mongod

# Or use MongoDB Atlas connection string
```

### Step 4: Start Backend Server

```bash
cd backend
npm run dev
```

Backend runs on `http://localhost:5000`

### Step 5: Start Frontend

```bash
cd frontend
npm start
```

Frontend runs on `http://localhost:3000`

## 📜 Smart Contract Deployment

### Local Network (Hardhat)

```bash
cd blockchain
npx hardhat run scripts/deploy.js --network localhost
```

### Testnet (Sepolia)

```bash
cd blockchain
npx hardhat run scripts/deploy.js --network sepolia
```

### Testnet (Mumbai)

```bash
cd blockchain
npx hardhat run scripts/deploy.js --network mumbai
```

### Verify Contract

```bash
npx hardhat verify --network sepolia <CONTRACT_ADDRESS>
```

## 📡 API Documentation

### Authentication

#### Register User
```http
POST /api/auth/register
Content-Type: application/json

{
  "name": "John Doe",
  "email": "john@example.com",
  "password": "password123",
  "walletAddress": "0x...",
  "role": "Farmer",
  "phoneNumber": "+1234567890",
  "organization": "Green Farms"
}
```

#### Login
```http
POST /api/auth/login
Content-Type: application/json

{
  "email": "john@example.com",
  "password": "password123"
}
```

### Batch Management

#### Create Batch (Farmer Only)
```http
POST /api/batch/create
Authorization: Bearer <token>
Content-Type: application/json

{
  "batchId": "BATCH-2024-001",
  "productName": "Organic Tomatoes",
  "quantity": 100,
  "unit": "kg",
  "metadata": {}
}
```

#### Transfer Batch
```http
POST /api/batch/transfer
Authorization: Bearer <token>
Content-Type: application/json

{
  "batchId": "BATCH-2024-001",
  "toAddress": "0x...",
  "message": "Transferred to distributor"
}
```

#### Record Quality
```http
POST /api/batch/quality
Authorization: Bearer <token>
Content-Type: application/json

{
  "batchId": "BATCH-2024-001",
  "qualityData": {
    "temperature": "4°C",
    "humidity": "60%",
    "notes": "Excellent condition"
  }
}
```

#### Get Batch Details
```http
GET /api/batch/:id
```

## 👥 User Roles

### Farmer 🌾
- Create new batches
- Upload produce information
- Record initial quality checks
- View own batches

### Distributor 📦
- Accept batches from farmers
- Transfer to transport
- Record quality inspections
- Track inventory

### Transport 🚚
- Update shipping status
- Record location updates
- Transfer to retailers
- Track deliveries

### Retailer 🏪
- Confirm arrivals
- Perform quality checks
- Update stock status
- Mark as completed

### Consumer 🛒
- Scan QR codes
- View complete history
- Verify blockchain records
- Read-only access

## 🎨 Design Features

### Animations
- Page transitions with Framer Motion
- Card hover effects
- Button ripple effects
- Progress tracker animations
- Timeline animations
- Loading skeletons
- Fade-in on scroll

### UI Components
- Modern SaaS-style design
- Responsive layout
- Dark mode ready
- Professional color palette
- Consistent spacing
- Clean typography

## 🔐 Security Features

- JWT authentication
- Role-based access control
- Password hashing (bcrypt)
- Rate limiting
- Helmet.js security headers
- Input validation
- CORS configuration

## 📱 QR Code Features

QR codes contain:
- Batch ID
- Blockchain reference
- Contract address
- Verification URL

Scanning opens: `/batch/:batchId` with complete history

## 🧪 Testing

### Smart Contract Tests

```bash
cd blockchain
npx hardhat test
```

### Backend Tests

```bash
cd backend
npm test
```

## 🌐 Deployment

### Backend Deployment (Heroku/Railway)

1. Set environment variables
2. Deploy:
```bash
git push heroku main
```

### Frontend Deployment (Vercel/Netlify)

1. Build:
```bash
cd frontend
npm run build
```

2. Deploy `build/` folder

### Smart Contract (Mainnet)

⚠️ **For production, ensure thorough testing and audit**

```bash
npx hardhat run scripts/deploy.js --network mainnet
```

## 🤝 Contributing

Contributions are welcome! Please:

1. Fork the repository
2. Create a feature branch
3. Commit changes
4. Push to the branch
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License.

## 👨‍💻 Author

Built with ❤️ for transparent supply chains

## 🙏 Acknowledgments

- OpenZeppelin for secure smart contract patterns
- Hardhat for development environment
- React community for amazing tools
- Tailwind CSS for styling framework

## 📞 Support

For issues and questions:
- Open an issue on GitHub
- Contact: your@email.com

---

**Ready for hackathons, college reviews, and portfolio showcases!** 🚀
