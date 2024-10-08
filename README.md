

# Wireguard-Manager

## Overview

**Wireguard-Manager** is a Python script that helps you manage your VPN connection using the `wg-quick` utility for WireGuard. The script allows you to easily bring up or down the VPN interface, as well as check its current status. The output is color-coded for clarity, making it easier to see whether the VPN is active or not.

## Features

- **Set Up VPN**: Activates the VPN by bringing up the `wg0` interface.
- **Shut Down VPN**: Deactivates the VPN by bringing down the `wg0` interface.
- **Check Status**: Checks whether the `wg0` interface is currently up or down.

## Prerequisites

- Python 3.x
- WireGuard installed and configured (`wg-quick` command available).
- `colorama` Python package.

You can install the `colorama` package using pip:

```bash
pip install colorama
```

## Usage

### Command-Line Interface (CLI)

The script provides a simple CLI to manage your VPN:

```bash
setvpn [action]
```

Where `[ACTION]` can be one of the following:

- **`u`**: Bring up the VPN interface (`wg0`).
- **`d`**: Bring down the VPN interface (`wg0`).
- **`s`**: Check the current status of the VPN interface.

### Example Commands

- **Set Up VPN**:

  ```bash
  setvpn u
  ```

- **Shut Down VPN**:

  ```bash
  setvpn d
  ```

- **Check VPN Status**:

  ```bash
  setvpn s
  ```

### Output

The script uses `colorama` to print color-coded messages:

- **Cyan**: Indicates the script is attempting to set up or shut down the VPN.
- **Green**: Indicates success (VPN is up or down).
- **Red**: Indicates failure or an action that can't be performed (e.g., trying to bring up an already active VPN).

## Code Explanation

The script is structured into several functions:

- **`on_vpn()`**: Brings up the `wg0` VPN interface if it is not already active.
- **`off_vpn()`**: Brings down the `wg0` VPN interface if it is currently active.
- **`status()`**: Checks if the `wg0` interface is active by examining the network interfaces. Returns `True` if active, `False` otherwise.
- **`checkstatus(flag)`**: Prints the current status of the VPN based on the flag returned by the `status()` function.

## Contributors

- [@PdotG](https://github.com/PdotG)
- [@morcircles](https://github.com/morecircless)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

