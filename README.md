# ChromaSafe

ChromaSafe is a secure, browser-based solution for sharing files between your personal devices with end-to-end encryption. This Chrome extension allows you to transfer files directly between your devices without relying on third-party cloud storage services.

## Features

- **End-to-End Encryption**: All files are encrypted on the client-side using the WebCrypto API
- **Real-time Transfer**: Uses WebSockets for fast, real-time file transfers
- **Simple Pairing**: Easy device pairing with secure codes
- **No Middleman**: While a server facilitates the connection, it never has access to your files
- **Cross-Platform**: Works on any device with the Chrome browser

## Project Structure

```
ChromaSafe/
├── extension/                 # Chrome extension files
│   ├── background/            # Background script
│   │   └── background.js      # Handles WebSocket connections and message routing
│   ├── popup/                 # Extension popup UI
│   │   ├── popup.html         # Popup HTML
│   │   ├── popup.css          # Popup styles
│   │   └── popup.js           # Popup JavaScript
│   └── manifest.json          # Extension manifest
└── README.md                  # This file
```

## Getting Started

### Prerequisites

- Google Chrome browser (latest version recommended)
- Node.js (v14 or later) for the backend server
- npm (comes with Node.js)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/amitsahoo0704/ChromaSafe.git
   cd ChromaSafe
   ```

2. **Load the extension in Chrome**
   - Open Chrome and navigate to `chrome://extensions/`
   - Enable "Developer mode" (toggle in the top-right corner)
   - Click "Load unpacked" and select the `extension` directory

3. **Set up the backend server**
   ```bash
   cd server
   npm install
   npm start
   ```
   The server will start on `http://localhost:3000` by default.

## Usage

1. **Pairing Devices**
   - Click the ChromaSafe extension icon in your browser
   - On the first device, click "Generate New Pairing Code"
   - On the second device, enter the pairing code and click "Pair Device"

2. **Sending Files**
   - Once paired, drag and drop files into the drop zone or click to select files
   - The files will be encrypted and sent to your other device

3. **Receiving Files**
   - Incoming files will appear in the file list
   - Click on a file to download it (it will be decrypted automatically)

## Security

- **End-to-End Encryption**: Files are encrypted on the sender's device and can only be decrypted by the intended recipient
- **No Data Storage**: The server does not store any files or encryption keys
- **Secure Pairing**: Devices are paired using one-time codes that are never stored on the server

## Development

### Building the Extension

1. Install dependencies:
   ```bash
   cd extension
   npm install
   ```

2. Build the extension:
   ```bash
   npm run build
   ```
   The built files will be in the `dist` directory.

### Running Tests

```bash
npm test
```

## Contributing

Contributions are welcome! Please read our [contributing guidelines](CONTRIBUTING.md) before submitting pull requests.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Built with ❤️ for secure and private file sharing
- Uses the WebCrypto API for encryption
- Inspired by the need for simple, secure file transfer between personal devices
#
