https://github.com/nazavod777/memeland_claimer
```
sudo apt update && sudo apt upgrade -y
sudo apt-get install gcc git nano mc htop python-dev libgmp3-dev -y
sudo apt-get install build-essential checkinstall
sudo apt-get install libreadline-gplv2-dev libncursesw5-dev libssl-dev \
    libsqlite3-dev tk-dev libgdbm-dev libc6-dev libbz2-dev libffi-dev zlib1g-dev
apt-get install python-is-python3
python --version

cd /opt
sudo wget https://www.python.org/ftp/python/3.9.18/Python-3.9.18.tgz
sudo tar xzf Python-3.9.18.tgz
cd Python-3.9.18
sudo ./configure -enable-optimizations
sudo make altinstall

cd /opt
sudo wget https://www.python.org/ftp/python/3.11.6/Python-3.11.6.tgz
sudo tar xzf Python-3.11.6.tgz
cd Python-3.11.6
sudo ./configure -enable-optimizations
sudo make altinstall

cd /usr/local/bin/
ls
update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.8 1
update-alternatives --install /usr/bin/python3 python3 /usr/local/bin/python3.9 2
update-alternatives --install /usr/bin/python3 python3 /usr/local/bin/python3.11 3

update-alternatives --list python3
update-alternatives --config python3
```
Скачаем
```
git clone https://github.com/nazavod777/memeland_claimer
dir
cd memeland_claimer
apt install python3-pip
```
Сосдадим виртуальную среду
```
update-alternatives --config python3 
# Выберим 3.11
#apt install -y python3.11-venv -y
mkdir /root/memeland_claimer/venv && cd /root/memeland_claimer/venv
python3.11 -m venv /root/memeland_claimer/venv
```
Настроим и запустим
```
tmux new -s meme
source /root/memeland_claimer/venv/bin/activate
# для выхода из виртуального окружения используем `deactivate`
cd /root/memeland_claimer
pip install -r requirements.txt
pip install requests

python3 main.py
```
