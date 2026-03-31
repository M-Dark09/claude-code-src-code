# Claude Code Source Code

This is the source code for Claude Code, Anthropic's official CLI tool for Claude. This is a leaked/public dump of the TypeScript and React source code.

## ⚠️ Important Notes

- **This is source code only** — there is no `package.json`, build configuration, or dependencies included
- **This is not a standalone project** — it was extracted from Anthropic's internal monorepo
- **Build requirements are missing** — the actual build process requires internal tooling and configuration
- **This requires significant setup** — you'll need to recreate the missing build infrastructure

## Project Structure

```
src/
├── commands/        # CLI commands and implementations
├── components/      # React/Ink UI components
├── services/        # API clients, auth, telemetry, MCP handling
├── tools/          # Tool definitions and implementations
├── utils/          # Utility functions
├── hooks/          # React hooks
├── state/          # State management
├── types/          # TypeScript type definitions
├── constants/      # Configuration constants
├── migrations/     # Data migrations
└── main.tsx        # CLI entry point
```

## Tech Stack

- **Runtime**: [Bun](https://bun.sh/) (modern JavaScript runtime)
- **Language**: TypeScript
- **UI Framework**: React + [Ink](https://github.com/vadimdemedes/ink) (terminal UI)
- **CLI Framework**: Commander.js
- **API Client**: Anthropic SDK (`@anthropic-ai/sdk`)
- **Authentication**: OAuth 2.0, Keychain (macOS), Registry (Windows)
- **Package Manager**: Bun

## What Would Be Needed to Run This

To actually build and run this project, you would need:

### 1. **Build Configuration**
   - `package.json` with all dependencies and scripts
   - `tsconfig.json` for TypeScript compilation
   - `bunfig.toml` for Bun configuration
   - Bun build/bundling configuration

### 2. **Key Dependencies** (not complete list)
   ```
   @anthropic-ai/sdk         - Claude API client
   @commander-js/extra-typings - CLI argument parsing
   react                      - UI library
   ink                        - Terminal React renderer
   chalk                      - Terminal styling
   lodash-es                  - Utility library
   zod                        - Runtime type validation
   ```

### 3. **Missing Configuration**
   - OAuth credentials configuration
   - Anthropic API endpoint configuration
   - Analytics/GrowthBook setup
   - MDM (Mobile Device Management) integration setup
   - Internal tool registrations and permissions

### 4. **Development Environment**
   - Bun runtime installed
   - Keychain/secrets management (platform-specific)
   - Node.js/npm (for compatibility)

## Architecture Highlights

### Entry Point
- `src/main.tsx` — CLI entry point with startup profiling and initialization
- Uses `commander.js` for argument parsing

### Core Systems
- **Query Engine** (`QueryEngine.ts`) — Orchestrates Claude API calls
- **Tool System** (`Tool.ts`) — Framework for extending Claude's capabilities
- **Task System** (`Task.ts`) — Background task management
- **Commands** (`src/commands/`) — CLI slash-commands and operations

### Services
- **API** (`services/api/`) — Anthropic Claude API integration
- **Auth** (`services/auth/`) — OAuth, API key, and session management
- **MCP** (`services/mcp/`) — Model Context Protocol server support
- **Analytics** (`services/analytics/`) — GrowthBook feature flags and telemetry
- **Remote Settings** (`services/remoteManagedSettings/`) — Device management policies

### State Management
- `state/` — Redux-like state management
- `history.ts` — Session history tracking
- `memdir/` — Memory system for remembering context

## Attempting to Build Locally

If you want to try building this:

```bash
# Install Bun (required)
curl -fsSL https://bun.sh/install | bash

# Attempt to install dependencies (will fail without package.json)
# You'd need to create a package.json first

# Try TypeScript compilation
bun build src/main.tsx --target bun
```

This will fail because:
1. No `package.json` exists
2. Dependencies are not specified
3. Build configuration is missing
4. Internal Anthropic modules are not available

## Why This Code Exists Here

This appears to be a snapshot of Claude Code's internal source at a specific point in time. It contains:
- ✅ All source TypeScript/React code
- ✅ Type definitions and interfaces
- ✅ Service implementations
- ✅ UI component code
- ❌ No build scripts or configuration
- ❌ No package dependencies
- ❌ No private keys or credentials (sanitized)
- ❌ No test files

## Learning Value

Despite not being runnable standalone, this code is valuable for:
- Understanding Claude Code's architecture
- Seeing how Anthropic structures a large CLI application
- Learning about Ink + React for terminal UIs
- Understanding MCP (Model Context Protocol) integration
- Studying async/concurrent operation handling in Node/Bun
- Examples of TypeScript in production code

## Legal Note

This source code was publicly leaked. Use at your own discretion and risk. This is not an official Anthropic release.
