# FleetDM Uninstaller for macOS

This repository contains a script to completely remove FleetDM from your macOS system. The script handles the removal of all FleetDM components, including the desktop app, MDM profiles, and associated files.

## What the Script Does

The uninstaller performs the following actions:
- Force quits the fleet-desktop application
- Removes FleetDM LaunchDaemon
- Cleans up all FleetDM-related files and directories
- Removes MDM enrollment profiles (if present)
- Verifies the removal of all Fleet-related components

## Prerequisites

- macOS operating system
- Administrator privileges (sudo access)
- Terminal access

## Installation and Usage

You can run the uninstaller using a single command in your terminal:

```bash
curl -L https://raw.githubusercontent.com/voiceflow-gallagan/fleet-desktop-cleaner/refs/heads/main/cleanup_macos.sh -o cleanup_macos.sh && chmod +x cleanup_macos.sh && sudo ./cleanup_macos.sh
```

Or follow these steps individually:

1. Download the script:
```bash
curl -L https://raw.githubusercontent.com/voiceflow-gallagan/fleet-desktop-cleaner/refs/heads/main/cleanup_macos.sh -o cleanup_macos.sh
```

2. Make the script executable:
```bash
chmod +x cleanup_macos.sh
```

3. Run the script with sudo privileges:
```bash
sudo ./cleanup_macos.sh
```

## What Gets Removed

The script will remove:
- Fleet Desktop application
- Fleet MDM enrollment profiles
- LaunchDaemon configurations
- All Fleet-related files and directories
- Orbit components and configurations

## Notes

- You will be prompted for your administrator password when running the script
- The script creates logs in `/tmp/fleet_remove_log.txt`
- If your device is MDM-enrolled, the script will attempt to remove the enrollment profile
- After running the script, it's recommended to verify in System Settings > General > Device Management that no Fleet profiles remain

## Troubleshooting

If you encounter any issues:
1. Check the logs in `/tmp/fleet_remove_log.txt`
2. Verify that you have administrator privileges
3. Ensure you're running the script with sudo
4. Check System Settings > General > Device Management for any remaining profiles
