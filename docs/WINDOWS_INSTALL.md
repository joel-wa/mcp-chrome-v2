# Windows Installation Guide 🔧

Detailed installation and configuration steps for Chrome MCP Server on Windows computers.

## 📋 Installation

1. **Download the latest Chrome extension from GitHub**

Download link: https://github.com/hangwin/mcp-chrome/releases

2. **Install mcp-chrome-bridge globally**

Ensure Node.js is installed on your computer. If not, please install it first.

```bash
# Make sure to install the latest version of the npm package (current latest version is 1.0.14), otherwise there may be issues
npm install -g mcp-chrome-bridge
```

3. **Load Chrome Extension**

   - Open Chrome and navigate to `chrome://extensions/`
   - Enable "Developer mode"
   - Click "Load unpacked" and select `your/downloaded/extension/folder`
   - Click the extension icon to open the extension, then click connect to see the MCP configuration
     <img width="475" alt="Screenshot 2025-06-09 15 52 06" src="https://github.com/user-attachments/assets/241e57b8-c55f-41a4-9188-0367293dc5bc" />

4. **Using with CherryStudio**

Select streamableHttp as the type, and fill in http://127.0.0.1:12306/mcp as the URL

<img width="675" alt="Screenshot 2025-06-11 15 00 29" src="https://github.com/user-attachments/assets/6631e9e4-57f9-477e-b708-6a285cc0d881" />

Check the tools list. If you can see the tools listed, it means it's ready to use.

<img width="672" alt="Screenshot 2025-06-11 15 14 55" src="https://github.com/user-attachments/assets/d08b7e51-3466-4ab7-87fa-3f1d7be9d112" />

```json
{
  "mcpServers": {
    "streamable-mcp-server": {
      "type": "streamable-http",
      "url": "http://127.0.0.1:12306/mcp"
    }
  }
}
```

## 🚀 Installation and Connection Issues

### If connection fails after clicking the extension's connect button

1. **Check if mcp-chrome-bridge is installed successfully**, ensure it's installed globally

```bash
mcp-chrome-bridge -v
```

<img width="612" alt="Screenshot 2025-06-11 15 09 57" src="https://github.com/user-attachments/assets/59458532-e6e1-457c-8c82-3756a5dbb28e" />

2. **Check if the manifest file is placed in the correct directory**

Path: C:\Users\xxx\AppData\Roaming\Google\Chrome\NativeMessagingHosts

3. **Check if there are logs in the npm package installation directory**

You need to check your installation path (if unclear, you can open the manifest file from step 2, the path inside is the installation directory). For example, if the installation path is as follows, check the log content:
C:\Users\admin\AppData\Local\nvm\v20.19.2\node_modules\mcp-chrome-bridge\dist\logs
<img width="804" alt="Screenshot 2025-06-11 15 09 41" src="https://github.com/user-attachments/assets/ce7b7c94-7c84-409a-8210-c9317823aae1" />
