# minewall

A simple firewall and server management setup script for Minecraft servers.

by [angeliust](https://github.com/angeliust)

---

## Overview

**minewall** provides a Bash script to quickly configure firewall rules and set up [PufferPanel](https://www.pufferpanel.com/) for Minecraft servers on Linux systems. This helps server administrators secure their Minecraft server ports and streamline management panel installation.

## Features

- Installs and configures `firewalld` to open Minecraft ports (default: 25565 TCP/UDP)
- Automates the installation of PufferPanel, an open-source game server management panel
- Sets up PufferPanel to start on boot and prompts to create an admin user

## Requirements

- Linux server with `sudo` privileges
- Internet connection

## Installation and Usage

1. Clone this repository or download the `minewall.sh` file:

    ```bash
    wget https://github.com/angeliust/minewall/raw/main/minewall.sh
    chmod +x minewall.sh
    ```

2. Run the script as root or with sudo:

    ```bash
    sudo ./minewall.sh
    ```

    The script will:
    - Install `firewalld` and open the default Minecraft port (25565) for both TCP and UDP
    - Install PufferPanel via its official repository and script
    - Enable and start the PufferPanel service
    - Prompt you to create a PufferPanel admin user

## What does the script do?

The core actions performed by `minewall.sh`:

```shell
apt install firewalld
firewall-cmd --permanent --zone=public --add-port=25565/tcp
firewall-cmd --permanent --zone=public --add-port=25565/udp
firewall-cmd --reload
curl -s https://packagecloud.io/install/repositories/pufferpanel/pufferpanel/script.deb.sh | sudo bash
apt-get install pufferpanel
systemctl enable pufferpanel
systemctl start pufferpanel
pufferpanel user add
```

- **Firewall configuration:** Opens required Minecraft server ports.
- **Panel setup:** Installs and starts PufferPanel for easy game server management.

## Customization

- To change the Minecraft port, edit the relevant `firewall-cmd` lines in `minewall.sh`.
- You can add more ports or services as needed.

## Security Note

Always review scripts from the internet before running them, especially as root. This script is intended for fresh or test server environments.

## Contributing

Contributions are welcome! If you'd like to suggest improvements or report issues, please open an [issue](https://github.com/angeliust/minewall/issues) or submit a pull request.

## License

Distributed under the MIT License. See [LICENSE](LICENSE) for more information.

---

*Secure and manage your Minecraft server in seconds with minewall!*
