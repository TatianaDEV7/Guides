Оригинал https://github.com/zaivanza/okx-whitelist

### Установка на Убунту
```
git clone https://github.com/zaivanza/okx-whitelist


tmux new -s okx-white
tmux attach -t okx-white
cd okx-white
python3 --version
update-alternatives --config python3
# Проверено на 3.11

mkdir /root/okx-whitelist/venv
python3.11 -m venv /root/okx-whitelist/venv
source /root/okx-whitelist/venv/bin/activate

cd /root/okx-whitelist
sudo apt-get install gcc python-dev libgmp3-dev
pip install -r requirements.txt
pip install requests
```
### Установка на Mac
```
git clone https://github.com/zaivanza/okx-whitelist

cd okx-whitelist
python3 --version
# https://www.python.org/downloads/macos/
# Проверено на 3.11.7

mkdir venv
python3.9 -m venv /your-path/okx-whitelist/venv
# или
python3.9 -m venv venv
source venv/bin/activate

pip install -r requirements.txt
pip install requests

python3 main.py



mkdir 311_venv
python3.11 -m venv /your-path/okx-whitelist/311_venv
# или
python3.11 -m venv 311_venv
source 311_venv/bin/activate

pip install -r requirements.txt
pip install requests

python3.11 main.py





mkdir 310venv
python3.10 -m venv /your-path/okx-whitelist/310venv
# или
python3.10 -m venv 310venv
source 310venv/bin/activate

pip install -r requirements.txt
pip install requests

python3 main.py
```
