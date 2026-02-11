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

## AiBridgeMCP v1.8.0 Prototype (Experimental)
This is an experimental release for developers and early adopters. Please note that some features are incomplete or under development.

⚠️ Status & Limitations
Experimental Build: This firmware is a prototype. Use at your own risk.
SSE Connection: Confirmed working with MCP Inspector v0.20.0.
Note: Direct SSE connection from Google Antigravity is currently not supported.
ASCOM/Alpaca Tools: Telescope control tools are currently disabled or unstable (IP/Timeout not implemented).
✅ Working Features
You can test the following MCP tools with this version:

File System (SPIFFS)
fs_list: List files in root directory.
fs_read: Read file content (max 4KB).
fs_write: Write content to file (new/overwrite).
fs_append: Append content to file.
fs_delete: Delete a file.
Serial Bridge
Interact with external MCUs via UART.

serial_write: Send data to serial port.
serial_read: Read data from serial port.
serial_query: Send command and wait for response.
serial_config: Change baud rate (Default: 115200bps).
Note: Baud rate setting resets to 115200bps after reboot.
Note: Hardware Serial port can be switched via SERIALONSTEP_SELECT_PIN (Serial vs Serial2), but currently only 
Serial
 is fully tested.
Alpaca Discovery
alpaca_discover_start / alpaca_discover_result: Discovery process should work.
🛠 Installation
Please refer to ESP32 Firmware Flashing Guide.pdf for flashing instructions.

![MCP Inspector 画面](./assets/mcp_inspector_sse_alpaca_discovery2.png)
