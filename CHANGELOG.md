# Changelog

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
