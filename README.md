# PactChain
Polkadot Africa 

Mega Drive with Project: https://mega.nz/folder/2pxnAZrQ#uroiznaDnZViPukESJB96Q
LOOM Video: https://www.loom.com/share/3ee0063b8e8341868357dd146d0d36a9
# Legal Contract Management Platform on Polkadot

A comprehensive blockchain-based platform for managing legal contracts with enterprise-grade features, built on the Polkadot ecosystem.

## 🚀 Project Overview

This project is a full-stack legal contract management system that leverages Polkadot's blockchain technology to provide secure, transparent, and efficient contract lifecycle management. The platform includes AI-powered contract generation, multi-signature approval workflows, blockchain integration, and enterprise collaboration features.

## 📋 Table of Contents

- [Architecture](#architecture)
- [Project Structure](#project-structure)
- [Prerequisites](#prerequisites)
- [Installation Guide](#installation-guide)
- [Configuration](#configuration)
- [Development Workflow](#development-workflow)
- [Deployment](#deployment)
- [Features](#features)
- [Technology Stack](#technology-stack)
- [Contributing](#contributing)

## 🏗️ Architecture

### System Components

```
┌─────────────────────────────────────────────────────────────────┐
│                        Frontend (React)                        │
│  ┌─────────────┐  ┌──────────────┐  ┌───────────────────┐    │
│  │   Web UI    │  │ Mobile UI    │  │ Admin Dashboard   │    │
│  │  (React)    │  │ (Responsive) │  │   (Management)    │    │
│  └─────────────┘  └──────────────┘  └───────────────────┘    │
└─────────────────────────────────────────────────────────────────┘
                                │
                                ▼
┌─────────────────────────────────────────────────────────────────┐
│                    Backend API (Node.js)                       │
│  ┌─────────────┐  ┌──────────────┐  ┌───────────────────┐    │
│  │   Express   │  │  WebSocket     │  │   File Upload     │    │
│  │    API      │  │   Server       │  │    Service        │    │
│  └─────────────┘  └──────────────┘  └───────────────────┘    │
└─────────────────────────────────────────────────────────────────┘
                                │
                                ▼
┌─────────────────────────────────────────────────────────────────┐
│                  Blockchain Layer (Polkadot)                   │
│  ┌─────────────┐  ┌──────────────┐  ┌───────────────────┐    │
│  │  Smart      │  │  Parachain     │  │   Bridge          │    │
│  │ Contracts   │  │   Runtime      │  │  Integration      │    │
│  └─────────────┘  └──────────────┘  └───────────────────┘    │
└─────────────────────────────────────────────────────────────────┘
                                │
                                ▼
┌─────────────────────────────────────────────────────────────────┐
│                      Data Layer                                │
│  ┌─────────────┐  ┌──────────────┐  ┌───────────────────┐    │
│  │  PostgreSQL  │  │   SQLite       │  │   File Storage    │    │
│  │  (Primary)   │  │  (Backup)     │  │  (IPFS/Local)     │    │
│  └─────────────┘  └──────────────┘  └───────────────────┘    │
└─────────────────────────────────────────────────────────────────┘
```

## 📁 Project Structure

```
polkadot_project/
├── frontend/                    # React frontend application
│   ├── src/
│   │   ├── components/         # Reusable UI components
│   │   ├── pages/             # Page components
│   │   ├── hooks/             # Custom React hooks
│   │   ├── services/          # API service layer
│   │   └── utils/             # Utility functions
│   ├── public/                # Static assets
│   └── package.json           # Frontend dependencies
│
├── backend/                     # Node.js backend API
│   ├── src/
│   │   ├── controllers/       # Route controllers
│   │   ├── models/            # Data models
│   │   ├── routes/            # API routes
│   │   ├── middleware/        # Express middleware
│   │   └── services/          # Business logic
│   ├── migrations/            # Database migrations
│   └── package.json           # Backend dependencies
│
├── contract-parachain/          # Substrate parachain
│   ├── pallets/               # Runtime pallets
│   ├── runtime/               # Chain runtime
│   └── node/                  # Chain node
│
├── polkadot-sdk/              # Polkadot SDK (submodule)
├── pdf-parse-test/            # PDF processing utilities
├── visualizer/                # Contract visualization tools
└── README.md                  # This file
```

## 🔧 Prerequisites

### System Requirements
- **Operating System**: Ubuntu 20.04+ / macOS 10.15+ / Windows 10+
- **Memory**: Minimum 8GB RAM (16GB recommended)
- **Storage**: 50GB free space
- **Network**: Stable internet connection

### Development Tools
- **Node.js**: v18.0.0 or higher
- **npm**: v8.0.0 or higher
- **Rust**: v1.70.0 or higher
- **Docker**: v20.10 or higher
- **Git**: v2.30 or higher

### VS Code Extensions (Recommended)
```json
{
  "recommendations": [
    "rust-lang.rust-analyzer",
    "ms-vscode.vscode-typescript-next",
    "esbenp.prettier-vscode",
    "bradlc.vscode-tailwindcss",
    "ms-vscode.vscode-json",
    "ms-vscode.vscode-npm-script",
    "ms-vscode.vscode-eslint"
  ]
}
```

## 🚀 Installation Guide

### 1. Clone the Repository
```bash
git clone https://github.com/your-org/polkadot-legal-contracts.git
cd polkadot-legal-contracts
```

### 2. Environment Setup

#### Frontend Setup
```bash
cd frontend
npm install
npm run build
```

#### Backend Setup
```bash
cd backend
npm install
npm run migrate
npm run seed
```

#### Polkadot SDK Setup
```bash
git submodule update --init --recursive
cd polkadot-sdk
cargo build --release
```

#### Parachain Setup
```bash
cd contract-parachain
cargo build --release
```

### 3. Database Configuration

#### PostgreSQL Setup
```bash
# Install PostgreSQL
sudo apt-get install postgresql postgresql-contrib

# Create database
sudo -u postgres createdb legal_contracts_db
sudo -u postgres psql -c "CREATE USER contract_admin WITH PASSWORD 'your_password';"
sudo -u postgres psql -c "GRANT ALL PRIVILEGES ON DATABASE legal_contracts_db TO contract_admin;"
```

#### SQLite Setup (Development)
```bash
# SQLite is included in the project
# Database will be created automatically on first run
```

### 4. Polkadot SDK Environment Setup

## 🚀 Installation Guide

### 1. Clone the Repository
```bash
git clone https://github.com/your-org/polkadot-legal-contracts.git
cd polkadot-legal-contracts
```

### 2. Environment Setup

#### Frontend Setup
```bash
cd frontend
npm install
npm run build
```

#### Backend Setup
```bash
cd backend
npm install
npm run migrate
npm run seed
```

#### Polkadot SDK Setup
```bash
git submodule update --init --recursive
cd polkadot-sdk
cargo build --release
```

#### Parachain Setup
```bash
cd contract-parachain
cargo build --release
```

### 3. Database Configuration

#### PostgreSQL Setup
```bash
# Install PostgreSQL
sudo apt-get install postgresql postgresql-contrib

# Create database
sudo -u postgres createdb legal_contracts_db
sudo -u postgres psql -c "CREATE USER contract_admin WITH PASSWORD 'your_password';"
sudo -u postgres psql -c "GRANT ALL PRIVILEGES ON DATABASE legal_contracts_db TO contract_admin;"
```

#### SQLite Setup (Development)
```bash
# SQLite is included in the project
# Database will be created automatically on first run
```

### 4. Install Dependencies (Arch Linux)

Before installing the Polkadot SDK, you need to install some dependencies. For Arch Linux, you can do this with the following command:

```bash
sudo pacman -Syu --needed base-devel cmake openssl-1.1 protobuf clang
```

## 2. Install Rust

Substrate development requires a specific Rust toolchain setup. Follow these steps to install and configure Rust:

```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

Once `rustup` is installed, configure your shell to include the Cargo binary path:

```bash
source "$HOME/.cargo/env"
```

Then, run the following commands to set up the correct toolchain for Substrate development:

```bash
rustup default stable
rustup update
rustup update nightly
rustup component add rust-src --toolchain stable
rustup target add wasm32-unknown-unknown --toolchain stable
rustup target add wasm32v1-none --toolchain stable
rustup target add wasm32-unknown-unknown --toolchain nightly
```

## 3. Clone, Build, and Run the Polkadot SDK

With the dependencies and Rust toolchain in place, you can now clone the Polkadot SDK repository, build it, and run a local development node.

```bash
git clone https://github.com/paritytech/polkadot-sdk.git
cd polkadot-sdk
cargo build --release
./target/release/polkadot --dev
```

### Troubleshooting

#### Virtual Memory Errors

If you encounter errors related to virtual memory while building the Polkadot SDK, it's likely because the build process is consuming too much RAM. You can mitigate this by limiting the number of parallel jobs Cargo uses. To do this, open the `.cargo/config.toml` file in the `polkadot-sdk` directory and add the following lines under the `[build]` section:

```toml
[build]
jobs = 1
```

This will slow down the build process but should prevent memory-related errors. You can experiment with a higher number of jobs if your machine has more RAM.
