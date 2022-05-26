# Mokuro2Pdf
Cli Ruby script to generate pdf files with selectable text from [Mokuro](https://github.com/kha-white/mokuro)'s html overlay

<img src="img/Mokuro2Pdf on Kindle.png" width=auto heigth=auto>

#### You can use [Memo2Anki](https://github.com/Kartoffel0/Memo2Anki) to mine from the pdfs created with this script

# Requirements
- Prawn `gem install prawn`
- MiniMagick `gem install mini_magick`

Also
- [Image Magick](https://imagemagick.org/script/download.php) as it is required by MiniMagick

# Usage
- Use [Mokuro](https://github.com/kha-white/mokuro) to generate a html overlay

## SIngle Volume
- Copy both the [`_ocr` and source images folders](https://github.com/Kartoffel0/Mokuro2Pdf/blob/master/img/folders.JPG) to the same folder as the script
- On your terminal run `ruby Mokuro2Pdf.rb -i "[1]" -n "[2]" -g [3] -f [4]` Replacing [n] with the following
  - **[1] - Folder with all the manga pages inside**

  - **[2] - Name to be given to the generated pdf, if ommited the script will use [1] as the pdf name**

  - **[3] (Optional) - Gamma value to be used on all pages, if ommited the script will use 0.8**

  - **[4] (Optional) - Font transparency to be used for the selectable text, if ommited the script will use 0.2**
  - Like this `ruby Mokuro2Pdf.rb -i "[ばらスィー] 苺ましまろ 第01巻" -n "苺ましまろ 第01巻"`
 
 This will generate a `[2] - MKR2PDF.pdf` pdf file

## Multiple Volumes
- Copy all the source images folders you want to convert to a separate folder
- On your terminal run `ruby Mokuro2Pdf.rb -p "[5]" -q "[6]" -g [3] -f [4]` Replacing [n] with the following
  - **[3] (Optional) - Gamma value to be used on all pages, if ommited the script will use 0.8**
  - **[4] (Optional) - Font transparency to be used for the selectable text, if ommited the script will use 0.2**
  - **[5] - Full path to the folder containing all the source images folders you want to convert**
  - **[6] - Full path to the containing all the ocr data(jsons) folders for all the volumes you want to convert**
  - Like this `ruby Mokuro2Pdf.rb -p "C:/Users/Ghabriel/Desktop/Manga" -q "C:/Users/Ghabriel/Documents/
Mokuro2Pdf/_ocr"`

This will generate a `[foldername] - MKR2PDF.pdf` pdf file for each folder on [4]

### Mining
- Copy both the, also generated, `[2] - MKR2PDF.json` json file and the folder with all the manga pages to [Memo2Anki](https://github.com/Kartoffel0/Memo2Anki)'s directory if you plan to mine from the pdfs

#### A [20 page demo](https://github.com/Kartoffel0/Mokuro2Pdf/blob/master/Mokuro2Pdf-Demo%20-%20MKR2PDF.pdf) is avaiable, to read it on your kindle simply drag and drop "Mokuro2Pdf-Demo - MKR2PDF.pdf" to your kindle's documents folder
