# Guides
Общая страница на которой я опишу как устанавливать тот или иной скрипт на Ubuntu

### Для начала уствновим все нужные нам в будущем версии python
Python 3.9.18
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
```
Python 3.10.13
```
cd /opt
sudo wget https://www.python.org/ftp/python/3.10.13/Python-3.10.13.tgz
sudo tar xzf Python-3.10.13.tgz
cd Python-3.10.13
sudo ./configure -enable-optimizations
sudo make altinstall
```
Python 3.11.6
```
cd /opt
sudo wget https://www.python.org/ftp/python/3.11.6/Python-3.11.6.tgz
sudo tar xzf Python-3.11.6.tgz
cd Python-3.11.6
sudo ./configure -enable-optimizations
sudo make altinstall
```

Добавим альтернативные версии для возможности выбора
```
cd /usr/local/bin/
ls
update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.8 1
update-alternatives --install /usr/bin/python3 python3 /usr/local/bin/python3.9 2
update-alternatives --install /usr/bin/python3 python3 /usr/local/bin/python3.10 3
update-alternatives --install /usr/bin/python3 python3 /usr/local/bin/python3.11 4
```
Проверка списка версий и выбор нужной:
```
update-alternatives --list python3
update-alternatives --config python3
```

## all-in-one-v2 by zaivanza
- Github zaivanza 
- Link https://github.com/zaivanza/all-in-one-v2
- Guide https://teletype.in/@hodlmod.eth/how-to-run-scripts
- Python 3.10

Сразу же выбираем нужную версию Python.
```
update-alternatives --config python3
python3 --version
# Нужна Python 3.10
```
Загружаем скрипт
```
sudo apt update && sudo apt upgrade -y
git clone https://github.com/zaivanza/all-in-one-v2
dir
cd all-in-one-v2
apt install python3-pip
```
Создаем виртуальное окружение в котором будем работать
```
apt install -y python3.10-venv -y
mkdir /root/all-in-one-v2/aio_venv && cd /root/all-in-one-v2/aio_venv
python3.10 -m venv /root/all-in-one-v2/aio_venv
source /root/all-in-one-v2/aio_venv/bin/activate
# для выхода из виртуального окружения используем `deactivate`
```
Производим конфигурацию виртуального окружения
```
cd /root/all-in-one-v2
pip install -r requirements.txt
pip install requests
```
[Настраиваем скрипт](https://github.com/zaivanza/all-in-one-v2) и запускаем
```
tmux new -s all-1
# tmux ls
# tmux attach -t all-1
# tmux kill-session -t all-1
python main.py
```

## zkSync-aio by 1liochka
- Github 1liochka 
- Guide https://teletype.in/@1liochka/S-bzaoADAAz
- Python 3.9

Сразу же выбираем нужную версию Python.
```
update-alternatives --config python3
python3 --version
# Нужна Python 3.9
```
Устанавливаем
```
unzip /root/ZkSync-aio-without-lite.zip
cd /root/ZkSync-aio-without-lite
apt install python3-pip
```
Создаем виртуальное окружение в котором будем работать
```
apt install -y python3.9-venv -y
mkdir /root/zksync-venv && cd /root/zksync-venv
python3.10 -m venv /root/zksync-venv
source /root/zksync-venv/bin/activate
# для выхода из виртуального окружения используем `deactivate`
```
Производим конфигурацию виртуального окружения
```
cd /root/ZkSync-aio-without-lite
pip install -r requirements.txt
pip install requests
python main.py
```
[Настраиваем скрипт](https://teletype.in/@1liochka/S-bzaoADAAz) и запускаем
```
tmux new -s zksync
# tmux ls
# tmux attach -t zksync
# tmux kill-session -t zksync
python main.py
```
