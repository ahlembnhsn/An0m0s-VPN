# An0m0s VPN Manager | OpenVPN GUI Controller for Linux

<div align="center">

![Python Version](https://img.shields.io/badge/python-3.8%2B-blue)
![License](https://img.shields.io/badge/license-MIT-green)
![Platform](https://img.shields.io/badge/platform-Linux-lightgrey)
![OpenVPN](https://img.shields.io/badge/OpenVPN-compatible-orange)

**An0m0s VPN - Enterprise-grade OpenVPN GUI Manager with Killswitch Firewall Protection for Linux**

*Free open-source VPN controller | Network security | Privacy protection | OpenVPN client GUI*

[⭐ Star this repo](https://github.com/Anasx1111/An0m0s-VPN) • [🐛 Report Bug](https://github.com/Anasx1111/An0m0s-VPN/issues) • [💡 Request Feature](https://github.com/Anasx1111/An0m0s-VPN/issues)

</div>

---

## 📋 Overview

**An0m0s VPN Manager** is a modern, secure GUI application for managing OpenVPN connections on Linux systems. Built with Python and Tkinter, An0m0s VPN features a premium dark theme interface, network killswitch protection, and real-time connection monitoring. Perfect for users who want an easy-to-use OpenVPN GUI on Linux with advanced security features.

### What is An0m0s VPN?

An0m0s VPN Manager is a free, open-source OpenVPN client GUI designed specifically for Linux (Ubuntu, Debian, Kali Linux). It provides a user-friendly interface for managing VPN connections with built-in firewall killswitch to protect your privacy and prevent IP leaks.

## ✨ Key Features of An0m0s VPN

An0m0s VPN Manager offers powerful features for secure OpenVPN connections:

- **🎨 Premium Dark UI** - Modern, responsive interface with smooth animations designed for Linux desktop environments
- **🔒 Network Killswitch** - Blocks all internet traffic outside VPN tunnel using iptables firewall rules to prevent IP leaks
- **🌍 IP & Location Detection** - Real-time public IP address and geolocation tracking to verify VPN connection
- **⚡ Easy Configuration** - Simple .ovpn file upload and management for all OpenVPN providers
- **🛡️ Security First** - Root privilege management with pkexec for secure VPN operations
- **📊 Connection Monitoring** - Real-time VPN status and OpenVPN process tracking
- **🔄 Automatic Recovery** - Network restoration and cleanup tools for safe disconnection
- **📱 Responsive Design** - Adapts to different screen sizes (1-column/2-column layout)
- **🆓 Free & Open Source** - MIT licensed, completely free VPN manager software

## 🖼️ Screenshots

<div align="center">
  <img src="images/screenshot-main.png?raw=true" alt="An0m0s VPN Manager Interface" width="800">
  <p><em>An0m0s VPN Manager - Premium Dark Theme Interface</em></p>
</div>

### Key Interface Features:
- **Connection Dashboard** - Real-time IP address and location tracking
- **OpenVPN Profile Manager** - Easy .ovpn file configuration
- **Killswitch Toggle** - Visual security control with one-click activation
- **Control Panel* for An0m0s VPN

### System Requirements
- **Operating System**: Linux (tested on Debian, Ubuntu, Kali Linux, Mint)
- **Python**: 3.8 or higher
- **OpenVPN**: Must be installed for VPN functionality
- **Root Access**: Required for VPN and firewall management
- **Desktop Environment**: Any Linux DE with X11 support

### Python Dependencies
- `tkinter` - Python GUI library (usually pre-installed with Python)
- `requests` - For IP geolocation API calls

### Keywords
`OpenVPN GUI Linux`, `VPN Manager`, `Network Killswitch`, `Linux VPN Client`, `OpenVPN Controller`, `VPN GUI Ubuntu`, `Python VPN`, `Open Source VPN`, `Firewall Killswitch`, `VPN Privacy Tool`
### PyHow to Install An0m0s VPN

### 1. Clone the An0m0s VPN Repository
```bash
git clone https://github.com/Anasx1111/An0m0s-VPN.git
cd An0m0s-VPN
```

Or download the latest release from [GitHub releases page](https://github.com/Anasx1111/An0m0s-VPN/releases) 1. Clone the Repository
```bash
git clone https://github.com/Anasx1111/An0m0s-VPN.git
cd An0m0s-VPN
```

### 2. Install System Dependencies
```bash
# Ubuntu/Debian/Kali
sudo apt update
sudo apt install python3 python3-tk openvpn iptables
```

### 3. Install Python Dependencies
```bash
# Create virtual environment (recommended)
python3 -m venv env
source env/bin/activate

# Install required packages
pip install -r requirements.txt
```

### 4. Make the Script Executable
```bash
chmod +x An0m0s_vpn.py
```

## 🎯 Usage

### Running the Application

The application requires root privileges to manage VPN connections and firewall rules:

```bash
# Run with pkexec (recommended - GUI authentication)
pkexec python3 An0m0s_vpn.py

# Or with sudo
sudo python3 An0m0s_vpn.py
```

### Quick Start Guide

1. **Launch the application** with root privileges
2. **Load .ovpn file** - Click "Load .ovpn file" and select your OpenVPN configuration
3. **Enable Killswitch** (optional) - Toggle the killswitch to block all non-VPN traffic
4. **Start VPN** - Click "Start VPN" to establish connection
5. **Monitor Status** - View your connection status, IP, and location in real-time

### Killswitch Feature

The killswitch uses iptables to block all internet traffic except:
- VPN tunnel (tun/tap interfaces)
- VPN server connections
- Localhost traffic
- DNS and DHCP (before VPN connects)

**⚠️ Warning**: When killswitch is active and VPN disconnects, you will have no internet access until you disable the killswitch or reconnect.

### Getting OpenVPN Configuration Files

If you need a .ovpn configuration file, you can:
- Use the built-in link to download free configs
- Get configs from your VPN provider
- Create your own OpenVPN server configuration

## 🎮 Controls

| Button | Description |
|--------|-------------|
| **Load .ovpn file** | Upload OpenVPN configuration |
| **Start VPN** | Initiate VPN connection |
| **Force Stop** | Immediately terminate VPN process |
| **Status Check** | Verify VPN connection status |
| **Restore Network** | Remove all firewall rules |
| **Refresh** | Update IP and location info |
| **Killswitch Toggle** | Enable/disable traffic blocking |

## 🛠️ Technical Details

### Architecture
- **GUI Framework**: Tkinter with custom styling
- **VPN Management**: OpenVPN subprocess control
- **Firewall**: iptables for killswitch implementation
- **Networking**: Requests library for IP geolocation
- **Privilege Elevation**: pkexec for secure root access

### File Structure
```
An0m0s-VPN/
├── An0m0s_vpn.py      # Main application
├── requirements.txt    # Python dependencies
├── README.md          # Documentation
├── LICENSE            # MIT License
└── .gitignore         # Git ignore rules
```

### Security Considerations

1. **Root Privileges**: Application requires root for VPN/firewall management
2. **Killswitch Safety**: Automatically backs up iptables rules before modification
3. **Process Isolation**: VPN runs in separate subprocess
4. **Secure Cleanup**: Proper cleanup on application exit
5. **No Credentials Storage**: Never stores VPN credentials

## 🐛 Troubleshooting

### "App must run with root privileges"
- Use `pkexec` or `sudo` to run the application

### "OpenVPN not found"
```bash
sudo apt install openvpn
```

### "Failed to enable killswitch"
- Ensure `iptables` is installed
- Check if you have root privileges
- Verify no conflicting firewall rules

### VPN won't connect
- Verify .ovpn file is valid
- Check OpenVPN logs: `sudo journalctl -u openvpn`
- Ensure VPN server is reachable

### Internet blocked after closing app
- Reopen app and click "Restore Network"
- Or manually: `sudo iptables -F && sudo iptables -P INPUT ACCEPT && sudo iptables -P OUTPUT ACCEPT`

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request. For major changes:

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👤 Author

**Anas Gharaibeh**

- GitHub: [@Anasx1111](https://github.com/Anasx1111)
- LinkedIn: [Anas Gharaibeh](https://www.linkedin.com/in/anas-gharaibeh-9746b72b7/)
- Instagram: [@anas.gharibeh](https://www.instagram.com/anas.gharibeh/)

## 🙏 Acknowledgments

- OpenVPN community for the excellent VPN software
- Free VPN config providers
- Python Tkinter community

## ⚠️ Disclaimer

This tool is provided for educational and legitimate use only. Users are responsible for:
- Complying with their VPN provider's terms of service
- Following local laws and regulations
- Using VPN services responsibly

The author is not responsible for misuse of this software.

## 🔮 Future Enhancements

- [ ] Multi-VPN profile management
- [ ] Connection logs and history
- [ ] Auto-reconnect on disconnect
- [ ] Split tunneling support
- [ ] DNS leak protection
- [ ] Custom firewall rules
- [ ] System tray integration
- [ ] Dark/light theme toggle

## 🔍 SEO Keywords

An0m0s VPN, OpenVPN GUI Linux, VPN Manager, Linux VPN Client, OpenVPN Controller, Network Killswitch, VPN Firewall, Ubuntu VPN GUI, Debian VPN Manager, Kali Linux VPN, Python VPN GUI, Open Source VPN Client, Free VPN Manager, OpenVPN Tkinter, Linux Network Security, VPN Privacy Tool, IP Leak Protection, OpenVPN Frontend, VPN Connection Manager, Secure VPN Linux

---

<div align="center">

**⭐ If you find An0m0s VPN useful, please star this repository!**

Made with ❤️ by An0m0s | Anas Gharaibeh

**An0m0s VPN Manager** - The best free OpenVPN GUI for Linuxroject useful, please consider giving it a star!**

Made with ❤️ by An0m0s

</div>
