# Changelog

All notable changes to this project will be documented in this file.

## [2.1.1] - 2025-06-19

### 🔧 CRITICAL BUGFIX

#### Fixed
- **CRITICAL**: Fixed missing `handleRequest` method that was preventing MCP initialization
- Resolved "Server exited before responding to `initialize` request" error
- Fixed MCP protocol handshake timeout issues

#### Technical Details
- Added missing `handleRequest` method to properly route MCP method calls
- Server now correctly responds to `initialize`, `tools/list`, and `tools/call` methods
- VS Code MCP integration now works without timeout errors

## [2.1.0] - 2025-06-19

### 🎉 MAJOR FEATURE UPDATE - REAL API IMPLEMENTATION

#### Added
- **REAL GitHub API integration** for all 37 tools using @octokit/rest
- Complete implementation of all consolidated tools with actual GitHub API calls
- Zero simulation - all tools now return real data from GitHub

#### Changed
- **BREAKING**: Removed all simulated responses 
- All 37 tools now use real GitHub API endpoints
- Updated dependencies to include @octokit/rest v20.0.2
- Enhanced error handling for API calls
- Improved response formatting for real data

#### Implemented Tools (37 total)
- ✅ **Core GitHub (7)**: user context, repository search/management, file operations, code search, commit history, branch/tag management
- ✅ **Issues (4)**: search, management, comments, assignments
- ✅ **Pull Requests (8)**: search, core operations, lifecycle, branch ops, comments, Copilot integration, reviews
- ✅ **Security (2)**: code scanning alerts, secret scanning alerts
- ✅ **Notifications (3)**: listing, actions, subscriptions
- ✅ **GitHub Actions (6)**: workflow discovery, details, execution, jobs, logs, artifacts
- ✅ **Versioning & Releases (7)**: version management, safety, GitHub releases, prereleases, documentation, publishing, toolset management

#### Technical Details
- Added @octokit/rest integration for all API calls
- Implemented proper authentication using GitHub tokens
- Real-time data from GitHub API endpoints
- Comprehensive error handling for API failures
- Maintained backward compatibility with MCP protocol

#### Testing
- ✅ Verified real API calls with live GitHub data
- ✅ Confirmed authentication works with GitHub tokens
- ✅ Tested multiple tool categories (user, issues, branches, repositories)

### Previous Versions

## [2.0.1] - 2025-06-19
- Initial optimized server with 37 consolidated tools (simulated responses)

## [2.0.0] - 2025-06-19
- First release of GitHub Advanced MCP Server