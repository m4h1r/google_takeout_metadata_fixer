# Google Photos Metadata Fixer

## Description
When exporting photos via Google Takeout, Google doesn't apply all metadata to the image files. This script addresses this issue by iterating through folders, looking for `.json` metadata files and their corresponding photos. It then extracts the correct "photo taken" date from the JSON and writes it to the photo's EXIF data, ensuring your photos have accurate timestamps.

## Features
- Recursively processes all subdirectories
- Updates EXIF data including CreateDate, DateTimeOriginal, and ModifyDate
- Sets correct file system timestamps for each photo
- Applies GPS data if available in the JSON file

## Prerequisites
This script requires two command-line tools:
- `exiftool`: for reading and writing EXIF metadata
- `jq`: for parsing JSON files

Ensure these are installed on your system before running the script.

## Installation
1. Download the `update_exif_dir` script to your local machine.
2. Open Terminal and navigate to the directory containing the script.
3. Make the script executable: `chmod +x update_exif_dir`

## Usage
1. Open Terminal.
2. Navigate to the top-level directory containing your Google Takeout photos and JSON files: `cd path/to/your/google_takeout_folder`
3. Run the script: `./update_exif_dir`

The script will automatically process all photos and their corresponding JSON files in the current directory and all subdirectories.

## Note
Always make a backup of your photos before running any script that modifies metadata.

## Troubleshooting
If you encounter any issues, ensure that:
- `exiftool` and `jq` are correctly installed and accessible from the command line.
- You have the necessary permissions to read and write files in the target directories.
- Your JSON files follow the expected Google Takeout format.
