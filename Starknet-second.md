Нам понадобится именно Python3.9 так что давайте доуставовим эту версию на сервере. Далее мы сможем просто менять версии питонов. Таким образом можно ставить сколько угодно версий 3.7/3.8/3.9/3.10/3.11
м
- Как [изменить версию python3](https://habr.com/ru/articles/686186/) на Ubuntu
- [Версии python и виртуальное окружение](https://firstvds.ru/technology/ustanovka-python-39-i-virtualnogo-okruzheniya-venv) для python проектов 
```
sudo apt update && sudo apt upgrade -y
sudo apt-get install build-essential checkinstall
sudo apt-get install libreadline-gplv2-dev libncursesw5-dev libssl-dev \
    libsqlite3-dev tk-dev libgdbm-dev libc6-dev libbz2-dev libffi-dev zlib1g-dev
cd /opt
sudo wget https://www.python.org/ftp/python/3.9.18/Python-3.9.18.tgz
sudo tar xzf Python-3.9.18.tgz

# теперь установим альтернативную версию python
cd Python-3.9.18
sudo ./configure -enable-optimizations
sudo make altinstall


sudo ./configure -enable-optimizations
sudo make altinstall

# sudo apt-get install cmake build-essential git libmicrohttpd-dev \
# libssl-dev libhwloc-dev

# Проверка
cd /usr/local/bin/
ls

update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.8 1
update-alternatives --install /usr/bin/python3 python3 /usr/local/bin/python3.9 2

# Проверим список версий  и выбор нужной:
update-alternatives --list python3
update-alternatives --config python3

# установка pip
apt install python3-pip
python3.11 -m pip install --upgrade pip

# Скажем что python3 это python
apt-get install python-is-python3
python --version
```

Создадим виртуальное окружение и установим нужные пакеты. 
```
deactivate
# if before we used another venv
unzip /root/Starknet-aio-master_v.1.4.zip
cd /root/Starknet-aio-master
python3 --version
#we need Python 3.9

apt install -y python3.9-venv -y
mkdir starknet_venv && cd starknet_venv
python3.9 -m venv /root/starknet_venv
source /root/starknet_venv/bin/activate

cd /root/Starknet-aio-master
sudo apt-get install gcc python-dev libgmp3-dev
pip install pyproject.toml
pip install coincurve~=15.0.1 \
green~=3.3.0 \
protobuf~=3.19.1 \
pycryptodome~=3.12.0
pip install -r requirements.txt
pip install requests
```
Теперь запустим скрипт. Предпологается что вы уже [сделали все настройки](https://teletype.in/@1liochka/mhc9OtVux0P) файла config.py а так же файлы проксей и кошельков.
```
tmux new -s starknet_aio
python main.py
```
tmux команды:
```
tmux new -s <name-of-session> # Новая сессия
tmux ls
tmux attach -t <name-of-session> # Зайти в сессию
tmux kill-session -t <name-of-session> # Завершить сессию
```

