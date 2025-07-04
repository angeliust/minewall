# minewall

A lightweight and configurable firewall solution for Minecraft servers.

by [angeliust](https://github.com/angeliust)

---

## Overview

**minewall** is a server-side firewall specifically designed for Minecraft servers. It helps server administrators protect their servers from unwanted connections, spam attacks, and unauthorized access, providing an additional layer of security and control.

## Features

- Easy to install and configure
- Supports allowlists/denylists for players and IPs
- Limits connections per IP to prevent brute-force or spam attacks
- Customizable ban/kick messages
- Lightweight: minimal impact on server performance
- Compatible with major Minecraft server platforms (Spigot, Paper, etc.)
- Logging of blocked/allowed connection attempts

## Installation

1. **Download** the latest release from the [releases page](https://github.com/angeliust/minewall/releases).
2. **Place** the plugin `.jar` file into your server's `plugins` directory.
3. **Restart** your Minecraft server.

## Configuration

After the first launch, a configuration file (`config.yml`) will be generated in the `plugins/minewall` directory.

Example configuration options:

```yaml
max_connections_per_ip: 3
whitelist:
  - 127.0.0.1
  - 192.168.1.10
blacklist:
  - 203.0.113.45
kick_message: "You are not allowed to connect to this server."
```

- **max_connections_per_ip**: Set the maximum simultaneous connections allowed from a single IP.
- **whitelist/blacklist**: Control which IPs are allowed or denied.
- **kick_message**: Custom message sent to blocked players.

## Usage

- The firewall works automatically based on your configuration.
- Use server commands (if available) to update the whitelist/blacklist without restarting the server.
- Monitor server logs for connection events.

## Commands

> _If your plugin provides any in-game or console commands, list them here._

| Command                | Description                         | Permission        |
|------------------------|-------------------------------------|-------------------|
| `/minewall reload`     | Reload the minewall configuration   | `minewall.reload` |
| `/minewall status`     | View current firewall status        | `minewall.status` |

## Contributing

Contributions are welcome! If you have suggestions, bug reports, or want to contribute code, please:

1. [Open an issue](https://github.com/angeliust/minewall/issues)
2. Fork the repository
3. Create a pull request

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## License

Distributed under the MIT License. See [LICENSE](LICENSE) for more information.

## Acknowledgements

- Inspired by other Minecraft security plugins and community feedback.

---

*Protect your Minecraft server with minewall!*
