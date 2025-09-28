# Thoth - Steem Blockchain Curation Bot

## Project Overview
This is a Python-based blockchain curation bot that runs on the Steem blockchain. It filters posts based on operator preferences, evaluates them through LLM API calls, and if approved, writes summaries and creates overview posts with automatic reward distribution.

## Project Status (Replit Setup)
**Last Updated**: September 27, 2025

### Completed Setup Tasks
✅ **Python 3.11 Environment**: Successfully installed Python 3.11 with package manager
✅ **Dependencies**: Installed core dependencies (langdetect, numpy, Requests)
✅ **Configuration**: Created config.ini from template with basic Replit-compatible settings
✅ **Workflow Setup**: Configured console workflow for Python application
✅ **Deployment**: Configured VM deployment target for production use

### Current Issues
⚠️ **Steem Library Compatibility**: The project depends on `steem==1.0.1` library which has Python 2/3 compatibility issues:
- Uses deprecated `pycrypto` library with Python 2 syntax
- Multiple syntax errors in crypto dependencies (exception handling, long literals)
- These are deep dependency issues in the blockchain library itself

### Technical Details
- **Language**: Python 3.11
- **Main Dependencies**: steem, langdetect, numpy, requests
- **Configuration**: Uses config.ini for settings, environment variables for API keys
- **Workflow**: Console application that streams from Steem blockchain
- **Deployment**: Configured as VM (maintains state, long-running process)

### Functionality Overview
- **Blockchain Integration**: Connects to Steem API for post streaming and data retrieval
- **AI Integration**: Uses LLM APIs (ArliAI/Gemini) for content curation decisions  
- **Post Management**: Creates summaries and manages beneficiary reward distribution
- **Author Validation**: Screens authors based on reputation, followers, activity
- **Content Validation**: Filters by language, tags, word count, engagement metrics

### Required Configuration (For Full Operation)
The application requires several environment variables and configuration:
1. `LLMAPIKEY` - LLM API key for content analysis
2. `UNLOCK` - Steem wallet password (recommended for posting functionality)
3. Steem API endpoint configuration
4. Posting account setup with proper keys

### Next Steps for Full Operation
1. **Resolve Steem Library Issues**: Either find Python 3 compatible blockchain library or use docker/compatibility layer
2. **API Key Setup**: Configure LLM API access for content analysis
3. **Steem Account Configuration**: Set up posting account and wallet integration
4. **Testing**: Verify blockchain connectivity and posting functionality

## Architecture Notes
- **Entry Point**: `src/main.py` - Main application logic and blockchain streaming
- **Helpers**: Modular design with separate validation, posting, and AI integration modules
- **Configuration**: Template-based config system with environment variable override support
- **Validation Pipeline**: Multi-stage screening (author, content, engagement, wallet validation)