# Google Photos Metadata Düzeltici

## Açıklama
Google Takeout üzerinden resimlerinizi dışa aktardığınızda, Google tüm metaverilerinizi resim dosyanıza uygulamıyor. Bu kod betiği tüm klasör ve alt klasörlerde bulunan `.json` meta verilerini ve eşgelen resimleri arıyor. Daha sonra JSON dosyasından aldığı doğru çekim, oluşturma tarihleri ve konumları ile EXIF verilerini güncelliyor.

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

## Not
Always make a backup of your photos before running any script that modifies metadata.
Her hangi bir kod çalıştırmadan önce muhakkak tüm verilerinizin bir yedeğini alarak hareket edin.

##Kredi ve Teşekkür
Bu kod @ziegenhagel kullanıcısı tarafından oluşturulmuştu. Ben onu alıp, kendim için gerekli güncellemeleri yaparak Türkçe yorumlar ekledim. Kendisine teşekkür ederim.
##Credits und Danksagungen
Dieser Code wurde vom Benutzer @ziegenhagel erstellt. Ich nahm es und nahm selbst die notwendigen Aktualisierungen vor und fügte türkische Kommentare hinzu. Ich danke ihm.

## Troubleshooting
If you encounter any issues, ensure that:
- `exiftool` and `jq` are correctly installed and accessible from the command line.
- You have the necessary permissions to read and write files in the target directories.
- Your JSON files follow the expected Google Takeout format.
