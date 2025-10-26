# linuxproject
# INTRODUCTION
This repository demonstrates a practical implementation of Linux setup using Ubuntu 24.04 LTS on VirtualBox. It includes basic shell command usage and automation scripts for backup, monitoring, and downloading tasks.

Shell Script Development

# BACKUP SCRIPT
Backup Script (backup.sh) Copies a directory to a backup folder with a timestamp.

#!/bin/bash
# Author: RYAN
# Date: 26-Oct-2025
# Purpose: Backup a directory with timestamp

SRC="/home/user/documents"
DEST="/home/user/backup_$(date +%Y%m%d_%H%M%S)"
cp -r "$SRC" "$DEST"
echo "Backup completed at $DEST"

# CPU/Memory Monitor
Logs CPU and memory usage every 10 seconds.

#!/bin/bash
# Logs CPU and memory usage every 10 seconds

while true; do
  echo "$(date): CPU: $(top -bn1 | grep "Cpu(s)") MEM: $(free -m | grep Mem)" >> usage.log
  sleep 10
done

# Automated Download
Downloads a file using wget and stores it in a predefined directory.

#!/bin/bash
# Downloads a file using wget

URL="https://example.com/file.zip"
DEST="/home/user/downloads"
wget "$URL" -P "$DEST"

