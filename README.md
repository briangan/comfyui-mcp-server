# Fork of ComfyUI MCP Server joenorton/comfyui-mcp-server.git

[Original comfyui-mcp-server branch](https://github.com/joenorton/comfyui-mcp-server) was last updated around beginning of 2026.  Its ```mcp>=0.9.0``` requirement would automatically fetch the latest version of [mcp](https://pypi.org/project/mcp/), which is 2.2.0 for now, and together with mcp-types 2.2.0:
```
mcp                       2.2.0
mcp-types                 2.2.0
```

Attempt to run the server, would get error:
```
Traceback (most recent call last):
  File "/Volumes/devdrive/comfyui-mcp-server/server.py", line 13, in <module>
    from mcp.server.fastmcp import FastMCP
  File "/opt/anaconda3/envs/comfy-env/lib/python3.11/site-packages/mcp/server/fastmcp.py", line 16, in <module>
    raise ModuleNotFoundError(_MESSAGE, name=__name__)
ModuleNotFoundError: No module named 'mcp.server.fastmcp'. This is mcp 2.x, where FastMCP was renamed to MCPServer (from mcp.server.mcpserver import MCPServer) and other APIs changed; see the migration guide at https://py.sdk.modelcontextprotocol.io/v2/migration/#fastmcp-renamed-to-mcpserver or pin 'mcp<2' to keep running v1 code.
```

The problem is explained in the [Migrating v1 to v2 of MCP Server section](https://py.sdk.modelcontextprotocol.io/v2/migration/#fastmcp-renamed-to-mcpserver).

So if you have the mcp and mcp-types packages installed with 2+ version, you can grab this repository instead.