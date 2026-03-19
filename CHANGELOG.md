# Changelog

## 2.1.0

- Added new models:
  - x-ai/grok-4.20-beta (standard)
  - openai/gpt-5.4-nano (budget)
  - qwen/qwen3.5-9b (budget)
  - openai/gpt-5.4-mini (standard)
- Added website snapshot service optimizing image display for the project
- Added skill market
- Added close button to toast for more intuitive user operation
- Added display of all launched websites when browser has no tabs
- Added V1 self learning module for AI to learn from its mistakes
- Improved workspace sizing bar - double-clicking will snap it back to default position
- Improved agent error messages
- Fixed issues with skill install, empty response and error handling
- Fixed job cost tracking
- Fixed Hyperliquid integration to all instances
- Fixed prompt to show transactions on onchain transactions when returned in call

## 2.0.9

- Added real-time display writing during SSE output
- Added more logs and persistent logging in machine for debugging
- Improved projects UI optimization
- Improved display, editing, and deletion of inserted messages
- Improved SSE reconnection mechanism for web + tgbot
- Improved proactive skill system with further enhancements
- Improved websearch system that now uses past searches to build on the next search to create a more refined and deterministic research function and reduces duplicate searches and loops
- Fixed issue where the project resets after being set to public
- Fixed issue where forward messages in tgbot group chats and private chats could not recognize context
- Fixed issue where tgbot group chats did not recognize images + text
- Fixed positioning issue of the workspace right-click menu
- Fixed agent tool timeout handling and AI error retry logic
- Fixed schedule task refactoring and error reporting issues
- Fixed memory inject issues in agent
- Removed old orderly skills (orderly and orderly one) and replaced with the official orderly skill

## 2.0.8

- Added official skills repository infrastructure with dedicated repo for building and publishing skills
- Added GitHub Actions workflow for automatic frontmatter validation and skills.json rebuild
- Added container pre-install system for automatic official skills installation/updates on first launch
- Added skills-lock.json for tracking installed skill versions
- Added /compact command in Telegram bot
- Added /mute command in Telegram bot to disable scheduled job notifications
- Added project showcase in workspace displaying user-deployed websites
- Added asset information display in agent wallet
- Added option to hide usage information in Telegram bot responses
- Added safety net prompt in Telegram bot credits
- Improved launch my agent process optimization
- Improved charting system with enhanced functionality
- Improved core prompts for better agent responses
- Fixed issue where thread sharing images were not displaying
- Fixed voice input functionality bug
- Fixed Telegram bot inter-user messaging issue
- Fixed Orderly integration issues
- Fixed wallet-related bugs
- Fixed Polymarket integration
- Removed whitelist requirement for private chat functionality in Telegram
- Changed skills management to npx skills system with integration documentation

## 2.0.7

- Added Telegram bot service supporting private bot binding
- Added voice input support for web interface
- Added support for deleting completed and canceled scheduled tasks
- Added identifiers to Telegram threads for easier distinction
- Added model prices in model selection
- Added dashboard skill with comprehensive monitoring capabilities
- Added one-shot prompt system that proactively fixes errors until task completion
- Improved chat input box by removing character limit
- Improved display during tool execution
- Improved display of tables in Telegram
- Improved charting skill with overhauled prompt handling
- Improved agent understanding of proxy system
- Improved agent file editing to check for similar tasks and edit instead of recreating files to save tokens
- Improved dynamic chunking to prevent timeouts on long-running tasks by splitting into smaller subtasks within token limits
- Improved skill prompt handling and overhauled problematic prompts
- Fixed issue where dragging an image into chat input box resulted in duplicate images
- Fixed timezone handling for scheduled tasks in container
- Fixed issue where currentModel settings were being reset
- Fixed issue where messages were refreshed due to jobs resulting in information loss
- Fixed issue where Telegram could not recognize files sent to users
- Fixed errors in Bash Tool
- Fixed chart not showing in chat with added guardrails and definite prompts
- Fixed error issues regarding maximum iteration limits
- Fixed CoinGecko tools
- Fixed Birdeye tools
- Changed to unified marketplace
- Changed Telegram replies to display specific model name
- Enhanced tool schema validation for Gemini models
- Removed skills MCP integration
- Removed some supported networks from wallet integration after review

## 2.0.6

- Added preview-dev to guide web development
- Added dialog input box to cache user input information
- Added agent reply and user input copy function
- Added support for the Gemini 3.1 Flash-Lite
- Added support for internal API calls within localhost in machine
- Added model smart selection for scheduled tasks
- Added model cost in the agent runtime information
- Added new skills and endpoints
- Fixed the issue of authentication information disorder caused by the refresh token not being deleted
- Fixed the abnormal status display issue when the agent is working in the background
- Fixed the issue of port occupation in the preview server
- Fixed persisting user customized installation issues
- Fixed charting not showing in chat
- Fixed skills and tools issues
- Fixed job scheduler

## 2.0.5

- Added credit system
- Added support for inserting messages in dialogue to continue conversations
- Improved user agent creation time, reducing from 20-30 seconds to around 5 seconds
- Improved prompt cache to increase cache hit rate
- Improved memory management
- Updated default model from Sonnet 4 to Sonnet 4.6
- Fixed tool loader
- Fixed display anomalies caused by SSE disconnection when running in background on mobile
- Fixed logout caused by wallet disconnection
- Fixed issue where clicking a link on mobile cannot directly open workspace

## 2.0.4

- Added gift card redemption
- Improved decision tree prompt
- Improved wallet policy prompt 
- Fixed skill loader to detect all tools new and old
- Fixed Orderly skill commodities handling when it comes to externally added skills
- Fixed loading message not disappearing after SSE disconnection when conversation already completed

## 2.0.3

- Added support for multiple simultaneous conversations
- Added scheduled task execution with detailed logs
- Added share page with on-demand data loading to optimize performance
- Added prompt cache update
- Improved memory system
- Improved browser-preview skill by removing localhost text
- Fixed issues with Twelve Data API
- Fixed issue where images displayed incorrectly when using preview service
- Fixed issue where some users could not load more historical conversations
- Fixed occasional issue where input box image could not be cleared after sending a message
- Fixed issue of data loss after sharing
- Fixed issue where thinking data was not persistently saved after disconnecting chat

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
