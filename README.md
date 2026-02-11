# AiBridgeMCP - Standalone MCP Server for ESP32

_Last updated: 2026-02-07 (JST)_

AiBridgeMCP is a lightweight, standalone Model Context Protocol (MCP) server implementation running on ESP32.  
It enables AI agents (such as Claude, Gemini, or ChatGPT) to interact directly with telescope control systems via the ASCOM Alpaca protocol.

## 🚀 Key Breakthrough: Direct SSE Connection

Unlike many other MCP implementations that require a PC-side proxy,  
**AiBridgeMCP supports direct SSE (Server-Sent Events) transport**.  
This allows AI clients to establish a persistent connection directly to the ESP32 hardware over your local network.

## 🌟 Features

- **True Standalone**: No Python or Node.js proxy needed on the client side.  
- **Direct SSE Transport**: SSE for downstream (server → client) and HTTP POST for upstream (client → server).  
- **Alpaca Discovery**: Automatically finds ASCOM Alpaca compatible devices (such as **OnStepNinja** or **AiBridge**) in your network.  
- **Hardware Control**: Ready to integrate with telescope mounts including **NS-5000** and **OnStep** systems.

![MCP Inspector 画面](./assets/mcp_inspector_sse_alpaca_discovery2.png)
