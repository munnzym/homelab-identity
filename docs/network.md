# Homelab Network

## Primary Site

My primary homelab uses a private /24 subnet behind the home router.

A dedicated Debian LXC is used as the Tailscale subnet router.

## Setup

Tailscale is installed on a dedicated Linux container and advertises the local homelab subnet.

IP forwarding is enabled so the container can route traffic between the Tailscale network and the local LAN.

No management services are exposed directly to the internet.

## Routing

The Tailscale container acts as a subnet router for the local LAN.

Remote devices connect to Tailscale and access internal services through this router rather than through public port forwarding.

## Security

Access is limited to devices and users connected to the Tailscale network.

Management services such as Proxmox remain private and are only accessed over the private Tailscale connection.

## Testing

Remote access was tested from a mobile device connected to Tailscale.

The test confirmed access to internal management services through the private Tailscale network.
