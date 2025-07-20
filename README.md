🛍️ Google Product Feed Generator
This Python GUI application generates a Google-compatible XML product feed (google_product_feed.xml) by reading product data from CSV, TXT, or XLSX files within structured folders. The feed can then be zipped and optionally uploaded to an SFTP server.

🚀 Features
✅ Reads product data from CSV, TXT, or XLSX files

✅ Extracts image URLs from .jpg files in product folders

✅ Generates an XML feed compatible with Google Merchant Center

✅ Optional ZIP compression of the XML feed

✅ Optional SFTP upload for easy deployment

✅ User-friendly GUI interface with log output

📁 Folder Structure
Each subfolder inside the main products directory should represent one product and contain:

A data file (.csv, .txt, or .xlsx) with product information

One or more JPG images

Example:
kotlin
Kopiuj
Edytuj
products/
├── product1/
│   ├── data.csv
│   └── image1.jpg
├── product2/
│   ├── data.xlsx
│   ├── front.jpg
│   └── side.jpg
...
📊 Required Product Fields
Your product data files must include at least these columns:

sku

name

price

quantity

shipping

Optional fields:

brand, gtin, mpn, condition

🖥️ How to Run
Prerequisites
Python 3.x

Install required libraries:

bash
Kopiuj
Edytuj
pip install openpyxl paramiko
Launch the GUI
bash
Kopiuj
Edytuj
python your_script_name.py
🧩 GUI Overview
Field	Description
Products Folder	Selects the directory containing all product subfolders
SFTP Host/Port/User/Pass	Connection details for remote upload
Remote Path	Target directory on the SFTP server

Buttons
Run Feed Only: Generate XML feed only

Run Feed + ZIP: Generate XML feed and ZIP it

Run All: Full pipeline – Generate, ZIP, and upload to SFTP

📝 Output
google_product_feed.xml – Google feed file

product_feed.zip – Zipped feed file (optional)

log.txt – Log of errors, warnings, and actions

GUI also displays logs in real-time

🔐 SFTP Upload
If you choose to upload via SFTP, make sure:

The remote path exists on the server

The provided credentials have write access

Your firewall or network allows SFTP connections

🔧 Customization
You can change the following variables in the script:

python
Kopiuj
Edytuj
OUTPUT_XML = 'google_product_feed.xml'
ZIP_NAME = 'product_feed.zip'
IMAGE_URL_PREFIX = 'https://yourdomain.com/images/'
Update these to match your domain or naming conventions.

🧑‍💻 Author
Developed by Marcin Stolarz. Feel free to fork or extend.

🛡️ License
This project is open-source and provided under the MIT License.
