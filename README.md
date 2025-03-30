# iotdb-mcp-server
A Model Context Protocol (MCP) server implementation for [IoTDB](https://github.com/apache/iotdb).

This server provides AI assistants with a secure and structured way to explore and analyze databases. It enables them to list tables, read data, and execute SQL queries through a controlled interface, ensuring responsible database access.

# Capabilities

* `list_resources` to list tables
* `read_resource` to read table data
* `list_tools` to list tools
* `call_tool` to execute an SQL
* `list_prompts` to list prompts
* `get_prompt` to get the prompt by name


# Usage
## Prerequisites
- Python with `uv` package manager
- IoTDB installation
- MCP server dependencies

## Development

```
# Clone the repository
git clone https://github.com/JackieTien97/iotdb_mcp_server.git
cd iotdb_mcp_server

# Create virtual environment
uv venv
source venv/bin/activate  # or `venv\Scripts\activate` on Windows

# Install development dependencies
uv sync
```


## Claude Desktop Integration

Configure the MCP server in Claude Desktop's configuration file:

#### MacOS

Location: `~/Library/Application Support/Claude/claude_desktop_config.json`

#### Windows

Location: `%APPDATA%/Claude/claude_desktop_config.json`


```json
{
  "mcpServers": {
    "iotdb": {
      "command": "~/PycharmProjects/iotdb_mcp_server/.venv/bin/python",
      "args": [
        "~/PycharmProjects/iotdb_mcp_server/src/iotdb_mcp_server/server.py"
      ],
      "env": {
        "IOTDB_HOST": "127.0.0.1",
        "IOTDB_PORT": "6667",
        "IOTDB_USER": "root",
        "IOTDB_PASSWORD": "root",
        "IOTDB_DATABASE": "test"
      }
    }
  }
}
```