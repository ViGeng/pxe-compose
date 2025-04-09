# PXE-Compose

Docker-based PXE boot environment compatible with existing DHCP networks, supporting heterogeneous devices (tested on x86_64 Ubuntu).

## Features

- Works with existing DHCP servers (proxy mode)
- (SHOULD) Support multiple architectures (x86_64, arm64, Raspberry Pi)
- Easy deployment with Docker Compose
- Minimal configuration required

## Setup

1. Clone and configure:

   ```bash
   git clone https://github.com/vigeng/pxe-compose.git
   cd pxe-compose
   # Edit dnsmasq.conf - update interface and IP address
   ```

2. Launch:

   ```bash
   docker-compose up -d
   ```

3. Set target devices to PXE boot

## Architecture

- **dnsmasq container**: DHCP proxy for PXE boot information
- **netboot.xyz container**: Boot menu and TFTP service

## Configuration

- `dnsmasq.conf`: Proxy DHCP settings and boot options
- `tftpboot/`: Boot files for different architectures

## Troubleshooting

- PXE not working? Check interface and IP in `dnsmasq.conf`
- See logs: `docker-compose logs -f`
- Verify ports 67-69 are available

## Tested On

- x86_64 Ubuntu clients

## License

[MIT License](LICENSE)

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.
