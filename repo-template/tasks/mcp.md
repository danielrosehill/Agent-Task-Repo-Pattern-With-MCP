# MCP Server Configuration

This document defines the Model Context Protocol (MCP) servers required for this project. MCP servers extend AI agent capabilities by providing access to specialized functions, external information, and services.

## Required MCP Servers

### SSH Connectivity
- **Server**: `mcp-ssh`
- **Purpose**: Remote server access and command execution
- **Configuration**: Pre-configured with SSH keys for target environment
- **Usage**: Connect to and manage the Ubuntu VM at 10.0.0.x

## MCP Server Setup

The AI agent should ensure these MCP servers are available and properly configured before beginning task execution. If any required servers are unavailable, the agent should request setup assistance or alternative approaches.

### Verification Steps

1. **Check SSH connectivity**: Verify `mcp-ssh` can connect to the target server
2. **Test permissions**: Ensure adequate privileges for software installation and configuration
3. **Validate network access**: Confirm connectivity to camera RTSP feeds from target server

## Additional MCP Servers (Optional)

Depending on implementation choices, the following MCP servers may be beneficial:

- **Docker MCP**: For containerized deployment management
- **GitHub MCP**: If code needs to be committed or repositories managed
- **Memory MCP**: For persistent context and learning across sessions

## Configuration Notes

- MCP servers should be configured before task execution begins
- Authentication and access credentials are handled through the MCP server configurations
- Any MCP server failures should be logged and reported immediately
