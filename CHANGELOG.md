# Changelog

## 2.0.2

- Added browser-preview skill allowing agents to recognize browser functionality within front-end pages
- Added real-time tracking of token usage and credit consumption for every conversation round
- Added Birdeye and 12data as new data sources
- Added backend task continuation support for disconnected conversations due to network fluctuations or unexpected exits
- Improved chat homepage UI with centered input box and smooth animation transition to bottom after sending messages
- Improved context management with optimized context compact to prevent token overflow during deep multi-turn tool interactions
- Improved custom install management, fixing installation failures after reboots or automatic updates
- Improved Smart Routing with better model selection to reduce costs
- Improved model selection box with updated model configuration and categorization
- Improved wallet balance checking accuracy
- Improved charting system to reduce context bloat
- Upgraded skill installer skill for better performance
- Fixed issue where some users cannot connect to mainnet with EVM wallet plugin
- Fixed Phantom wallet recharge issue
- Fixed chat area width display issue
- Fixed issues with Hyperliquid tool TPSL functionality
- Fixed issues with Orderly tool
- Fixed issue with tool loader caching
- Fixed issue with networks not registered by Privy wallet

## 2.0.1

- Fixed issue where some users cannot connect to mainnet with EVM wallet plugin
- Fixed Phantom wallet recharge issue
- Fixed chat area width display issue

## 2.0.0

Starchild has evolved from a strategy creation tool into a complete personal AI agent platform. This major release introduces a sandboxed agent environment, multi-model AI routing, native crypto payment integration, and a comprehensive skill system - transforming how users research, trade, and automate their workflows.

- Added one-click agent deployment in secure sandboxed containers with 1024MB personal storage
- Added multi-model AI routing that reduces operational costs by up to 70% compared to standard OpenClaw deployments
- Added native Privy wallet integration supporting 29+ blockchains without exposing personal private keys
- Added customizable agent memory system that adapts to user preferences, trading styles, and time zones
- Added file system management for uploading and managing skills, images, scripts, and documents
- Added pre-loaded finance-specific skills spanning DeFi, prediction markets, and trading strategies
- Added skill creator functionality allowing users to create, download, and share custom skills
- Added recurring task scheduling that runs autonomously while users are offline
- Added human-readable skill format compatible with OpenClaw ecosystem
- Added web research capabilities across any topic or market
- Added code writing and review functionality
- Added document analysis and processing
- Added real-time market chat and analysis
- Added connections to trading venues, prediction markets, DeFi protocols, social platforms, and data feeds
- Added container-based isolation ensuring each user workspace remains private and secure
- Added sandboxed execution environment eliminating configuration vulnerabilities
- Added trustless wallet architecture preventing private key exposure during automated operations
- Added content moderation LLM to review all user-edited content
- Added protection against prompt injection, malicious inputs, and inappropriate content
- Added Paper Trading system upgrade with CoinGecko API integration, supporting all tokens with real-time prices
- Added instant entry feature for executing trades using natural language like "open long" or "buy now"
- Added XAU/XAG (gold/silver) trading support
- Added Watchlist and My Strategy sections to leaderboard
- Added profile picture editing in Account Management

## 1.1.1

- Added Paper Trading system upgrade with CoinGecko API integration, supporting all tokens with real-time prices
- Added content moderation LLM to review all user-edited content
- Added protection against prompt injection, malicious inputs, and inappropriate content
- Added instant entry feature for executing trades using natural language like "open long" or "buy now"
- Added XAU/XAG (gold/silver) trading support
- Added Watchlist and My Strategy sections to leaderboard
- Added profile picture editing in Account Management
- Improved chat page UI/UX
- Improved navigation bar and homepage UI styling
- Improved strategy generation to handle more complex strategies
- Improved chat flow and user guidance during strategy creation
- Improved strategy generation diversity and response formatting
- Improved tick size and execution accuracy for paper trading
- Improved strategy analysis accuracy with upgraded reasoning
- Improved connection stability with optimized heartbeat intervals
- Changed "All Time APR" to "ROE" on leaderboard, with APR shown for strategies over 30 days with positive ROE
- Fixed page crashes after creating strategies
- Fixed strategies failing due to API rate limiting
- Fixed connection timeouts during idle periods
- Fixed duplicate trade signals being sent
- Fixed price data not being read correctly in some API responses
- Fixed XAU/XAG validation errors when creating strategies
