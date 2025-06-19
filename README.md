# GitHub Advanced MCP Server v2.1.1

<div align="center">

[![npm version](https://badge.fury.io/js/%40andrebuzeli%2Fgithub-advanced-mcp.svg)](https://badge.fury.io/js/%40andrebuzeli%2Fgithub-advanced-mcp)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Node.js](https://img.shields.io/badge/Node.js-16+-green.svg)](https://nodejs.org/)

**Advanced GitHub MCP Server - 37 REAL API Tools (ZERO Simulation)**

</div>

## 🎉 What's New in v2.1.1

### 🔧 **CRITICAL BUGFIX**
- **✅ Fixed MCP initialization** - Server now properly responds to `initialize` requests
- **🔗 VS Code integration works** - No more timeout errors
- **🚀 All 37 tools operational** - Complete real API functionality restored

### ✨ **REAL API IMPLEMENTATION** (v2.1.0)
- **🚫 ZERO SIMULATION** - All 37 tools now use real GitHub API calls
- **✅ Complete @octokit/rest integration** for authentic GitHub data
- **🔗 Real-time GitHub API responses** for all operations
- **🛡️ Proper authentication** using GitHub tokens
- **📊 Live data** from actual GitHub repositories, issues, PRs, and more

### 🛠️ **All 37 Tools Implemented**
- **Core GitHub (7)**: User context, repos, files, code search, commits, branches
- **Issues (4)**: Search, management, comments, assignments
- **Pull Requests (8)**: Complete PR lifecycle with real data
- **Security (2)**: Code scanning & secret alerts
- **Notifications (3)**: Real GitHub notifications
- **Actions (6)**: Live workflow data & control
- **Versioning (7)**: Release management & publishing

### 📊 **Three Server Modes**

| Mode | Tools | Implementation | Best For |
|------|-------|----------------|----------|
| **Go Binary** | 78 | Native GitHub API | Production, high-throughput |
| **Standalone** | 78 | Node.js with real APIs | Development, compatibility |
| **Optimized** | 37 | **REAL APIs** (No simulation) | Clean interface, real data |

## 📦 Installation

```bash
npm install -g @andrebuzeli/github-advanced-mcp@latest
```

## 🛠️ Usage

### Choose Your Server Mode

```bash
# Go Binary (default - 78 tools)
export MCP_SERVER_TYPE=go
github-advanced-mcp

# Node.js Standalone (78 tools)
export MCP_SERVER_TYPE=standalone
github-advanced-mcp

# Optimized Consolidated (37 tools)
export MCP_SERVER_TYPE=optimized
github-advanced-mcp
```

### VS Code Integration

Add to your VS Code `settings.json`:

```json
{
  "mcp": {
    "servers": {
      "github-mcp": {
        "command": "github-advanced-mcp",
        "transport": "stdio",
        "env": {
          "MCP_SERVER_TYPE": "optimized",
          "GITHUB_TOKEN": "your_github_token_here"
        }
      }
    }
  }
}
```

## 🔧 Tool Categories (Optimized Mode)

### 🏢 **Core GitHub (7 tools)**
- `github_user_context` - User info & search
- `repository_search` - Repository discovery
- `repository_manager` - Create & fork repos
- `file_operations` - File CRUD operations
- `code_search` - Code search across repos
- `commit_history` - Browse commits
- `branch_tag_manager` - Branch & tag management

### 🐛 **Issues (4 tools)**
- `issue_search` - Search & list issues
- `issue_manager` - CRUD operations
- `issue_comments` - Comment management
- `issue_assignment` - User & Copilot assignment

### 🔄 **Pull Requests (8 tools)**
- `pull_request_search` - Search & list PRs
- `pull_request_core` - Get details, files, status
- `pull_request_lifecycle` - Create, update, merge
- `pull_request_branch_ops` - Branch operations
- `pull_request_comments` - Comments & interactions
- `pull_request_copilot` - Copilot reviews
- `pull_request_review_simple` - Direct reviews
- `pull_request_review_workflow` - Pending review workflow

### 🔒 **Security (2 tools)**
- `code_security_alerts` - Code scanning alerts
- `secret_security_alerts` - Secret scanning alerts

### 🔔 **Notifications (3 tools)**
- `notification_list` - List & get details
- `notification_actions` - Dismiss & mark read
- `notification_subscriptions` - Manage subscriptions

### ⚡ **GitHub Actions (6 tools)**
- `workflow_discovery` - List workflows & runs
- `workflow_details` - Get details & usage
- `workflow_execution` - Run, rerun, cancel
- `workflow_jobs` - List jobs
- `workflow_logs` - Logs management
- `workflow_artifacts` - Artifact operations

### 🧪 **Dynamic System (1 tool)**
- `toolset_manager` - Dynamic toolset management

### 📦 **Versioning & Release (6 tools)**
- `version_core` - Version bump & analysis
- `version_safety` - Preview & rollback
- `github_releases` - Create releases
- `prerelease_manager` - Alpha/beta/rc management
- `release_documentation` - Changelogs & notes
- `release_publishing` - Publish & tag management

## 💡 How Consolidation Works

Each consolidated tool uses an `action` parameter to specify the exact operation:

```json
{
  "name": "issue_manager",
  "arguments": {
    "action": "create",
    "owner": "user",
    "repo": "project",
    "title": "New Issue",
    "body": "Issue description"
  }
}
```

**Available actions:**
- `issue_manager`: `get`, `create`, `update`
- `file_operations`: `get`, `create`, `update`, `delete`, `push_multiple`
- `workflow_execution`: `run`, `rerun`, `rerun_failed`, `cancel`

## 🔑 Environment Variables

| Variable | Description | Default |
|----------|-------------|---------|
| `MCP_SERVER_TYPE` | Server mode: `go`, `standalone`, `optimized` | `go` |
| `GITHUB_TOKEN` | GitHub personal access token | Required |
| `GITHUB_PERSONAL_ACCESS_TOKEN` | Alternative token variable | - |

## 📚 Advanced Features

### 🔄 **Smart Version Management**
- Semantic versioning with commit analysis
- Safe rollback capabilities
- Preview mode for version changes
- Automated changelog generation

### 🚀 **Release Automation**
- GitHub releases with auto-generated notes
- NPM publishing integration
- Prerelease management (alpha/beta/rc)
- Tag management

### 🔒 **Security Integration**
- Code scanning alert management
- Secret scanning detection
- Security-first approach

## 🚀 Quick Start

1. **Install the package:**
   ```bash
   npm install -g @andrebuzeli/github-advanced-mcp@latest
   ```

2. **Set your GitHub token:**
   ```bash
   export GITHUB_TOKEN="your_github_personal_access_token"
   ```

3. **Configure VS Code** (add to settings.json):
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

4. **Start using with Copilot!** 🎉

## 🤝 Contributing

We welcome contributions! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## 📄 License

MIT License - see [LICENSE](LICENSE) file for details.

## 🏆 Credits

- **Original GitHub MCP Server**: GitHub Team
- **Advanced Features & Optimization**: Andre Buzeli
- **Community**: All contributors and users

---

<div align="center">

**Made with ❤️ for the GitHub community**

[Report Issues](https://github.com/Andre-Buzeli/github-mcp-server/issues) • 
[Request Features](https://github.com/Andre-Buzeli/github-mcp-server/issues/new) • 
[NPM Package](https://www.npmjs.com/package/@andrebuzeli/github-advanced-mcp)

</div>