# Quick Start Guide

## Installation

```bash
npm install -g @andrebuzeli/github-advanced-mcp@latest
```

## Setup

1. **Get a GitHub Personal Access Token:**
   - Go to GitHub Settings > Developer settings > Personal access tokens
   - Generate a new token with repo, read:user, and notifications permissions

2. **Set environment variable:**
   ```bash
   export GITHUB_TOKEN="your_github_personal_access_token"
   ```

3. **Configure VS Code MCP:**
   Add to your VS Code `settings.json`:
   ```json
   {
     "mcp": {
       "servers": {
         "github-mcp": {
           "command": "github-advanced-mcp",
           "transport": "stdio",
           "env": {
             "MCP_SERVER_TYPE": "optimized"
           }
         }
       }
     }
   }
   ```

## Test Installation

Run this command to test:
```bash
echo '{"jsonrpc":"2.0","id":1,"method":"initialize","params":{"protocolVersion":"2025-03-26"}}' | github-advanced-mcp
```

You should see a JSON response with server information.

## Usage Examples

### Get User Info
```json
{
  "name": "github_user_context",
  "arguments": {
    "action": "get_me"
  }
}
```

### Search Repositories
```json
{
  "name": "repository_search",
  "arguments": {
    "query": "react typescript",
    "sort": "stars",
    "order": "desc"
  }
}
```

### List Issues
```json
{
  "name": "issue_search",
  "arguments": {
    "action": "list",
    "owner": "facebook",
    "repo": "react",
    "state": "open"
  }
}
```

## Server Modes

- **optimized** (37 tools) - Recommended for most users
- **standalone** (78 tools) - Full Node.js implementation  
- **go** (78 tools) - Native Go binary (default)

Set mode with: `export MCP_SERVER_TYPE=optimized`

## Support

- 📖 [Full Documentation](README.md)
- 🐛 [Report Issues](https://github.com/Andre-Buzeli/github-mcp-server/issues)
- 📦 [NPM Package](https://www.npmjs.com/package/@andrebuzeli/github-advanced-mcp)