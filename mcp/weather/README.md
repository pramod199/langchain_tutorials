# Weather MCP Server

A simple MCP (Model Context Protocol) server that exposes US weather data from the [National Weather Service API](https://www.weather.gov/documentation/services-web-api) as tools.

Built by following the official MCP quickstart: https://modelcontextprotocol.io/docs/develop/build-server

## Tools

- `get_alerts(state)` — active weather alerts for a US state (two-letter code, e.g. `CA`).
- `get_forecast(latitude, longitude)` — short-term forecast for a location.

## Running

The server uses stdio transport, so it must be launched by an MCP client — running `uv run weather.py` directly in a terminal will fail with a JSON parse error because stdin isn't a JSON-RPC stream.

### Claude Desktop

Add to `~/Library/Application Support/Claude/claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "weather": {
      "command": "uv",
      "args": [
        "--directory",
        "/Users/pramod/src/langchain_tutorials/mcp/weather",
        "run",
        "weather.py"
      ]
    }
  }
}
```

### Claude Code

```bash
claude mcp add weather -- uv --directory /Users/pramod/src/langchain_tutorials/mcp/weather run weather.py
```

### MCP Inspector (standalone testing)

```bash
npx @modelcontextprotocol/inspector uv --directory /Users/pramod/src/langchain_tutorials/mcp/weather run weather.py
```
