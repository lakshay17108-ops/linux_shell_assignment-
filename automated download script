#!/bin/bash
# Purpose: Download a file from the internet and save it to a predefined directory
# Author: Baba tillu
# Date: 12-Nov-2025

URL="$1"
DEST_DIR="$HOME/downloads"

# Create destination directory if it doesn't exist
mkdir -p "$DEST_DIR"

# Extract filename from URL
FILENAME=$(basename "$URL")

# Download the file
wget "$URL" -O "$DEST_DIR/$FILENAME"

echo "Downloaded $FILENAME to $DEST_DIR"
