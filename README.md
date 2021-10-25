# OCR-Bitmap-Cache
元のREADME: https://github.com/DFIR-Drew/OCR-Bitmap-Cache  
デモ利用環境: Windows 11 Subsystem for linux (Ubuntu)

## 環境構築
```
sudo add-apt-repository ppa:alex-p/tesseract-ocr
sudo apt update
sudo apt install tesseract-ocr libtesseract-dev
sudo apt install libqt5gui5 python3-pip tesseract-ocr-jpn
pip3 install Pillow
pip3 install pytesseract opencv-python tqdm
```

## 使い方

1. t476df-2021フォルダへ移動
2. bitmapを抽出
```
mkdir rdp_bmp
python3 tools/bmc-tools.py -s win2019/Users/admin/AppData/Local/Microsoft/Terminal\ Server\ Client/Cache/ -d rdp_bmp/ -v
```
3. OCR実行
```
git clone https://github.com/tiot07/OCR-Bitmap-Cache
cd OCR-Bitmap-Cache
mkdir ocr
python3 ocr.py -s ../rdp_bmp -d ocr -o ocr.csv -w wordlist.txt
```

4. 分析ツール起動
```
../tools/RdpCacheStitcher-linux64
```
