#!/bin/bash

# Define colors for output
GREEN="\e[32m"
CYAN="\e[36m"
RESET="\e[0m"

# Check if a directory is provided
if [ -z "$1" ]; then
    echo "Usage: $0 <directory>"
    exit 1
fi

SOURCE_DIR="$1"
FONT_DIR="$HOME/.local/share/fonts"

# Create the font directory if it doesn't exist
mkdir -p "$FONT_DIR"

# Extract any .zip files in the source directory and subdirectories
echo -e "${CYAN}Checking for .zip files...${RESET}"
find "$SOURCE_DIR" -type f -iname "*.zip" -print0 | while IFS= read -r -d '' zipfile; do
    unzip -o "$zipfile" -d "$(dirname "$zipfile")"
    echo -e "${CYAN}Extracted: $zipfile${RESET}"
done

# Find and move .ttf fonts with green "Moved" message
echo -e "${CYAN}Moving .ttf font files...${RESET}"
find "$SOURCE_DIR" -type f -iname "*.ttf" -print0 | while IFS= read -r -d '' file; do
    mv "$file" "$FONT_DIR/"
    echo -e "${GREEN}Moved: $file -> $FONT_DIR/${RESET}"
done

# Update font cache
fc-cache -f -v

echo -e "${GREEN}Fonts moved and cache updated.${RESET}"
