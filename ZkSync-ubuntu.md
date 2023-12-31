# Гайд по установке и использованию ZkSync скрипта
Для начала установим все необходимое

Требуется:
- [Pycharm](https://www.jetbrains.com/pycharm/) community version
- Python <= 3.10
- Git
## Установка Pycharm
Оф гайды:
- [Jetbrains](https://www.jetbrains.com/help/pycharm/installation-guide.html)
- [Digitalocean](https://www.digitalocean.com/community/tutorials/install-pycharm-on-linux)
### Установка Pycharm as a snap package on Linux
Для начала нужна установка Snap [гайд1](https://www.linuxfordevices.com/tutorials/linux/snaps-in-linux) [гайд2](https://snapcraft.io/docs/installing-snapd)
```
sudo apt update && sudo apt upgrade -y
sudo apt install snapd 
sudo apt install core 
```
Установка PyCharm by Snap
```bash
sudo snap install pycharm-community --classic
# The --classic option is required because the PyCharm snap requires full access to the system, like a traditionally packaged application.
```
### Установка Pycharm через загрузку архива tar
Загрузите [PyCharm](https://www.jetbrains.com/pycharm/download/?section=linux#section=linux) и перекиньте с помощью sftp на сервер. Далее

```sh
# Если вы закачали архив в root
cd
sudo tar xzf pycharm-*.tar.gz -C /opt/
# Почему мы распаковываем именно в /opt/ написано тут https://www.jetbrains.com/help/pycharm/installation-guide.html#snap-install-tar
# Go to the /opt/ directory
cd /opt/pycharm-2022.2.4/bin
# Run pycharm.sh
sh pycharm.sh
```
## Установка python
```sh
sudo apt update
sudo apt install build-essential zlib1g-dev \
libncurses5-dev libgdbm-dev libnss3-dev \
libssl-dev libreadline-dev libffi-dev curl
# pip install python3-pip
python3 --version
# Should be less than 3.10
```
## Установка Git на Debian-based distribution, such as Ubuntu
[Оф гайд](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
```sh
sudo apt install git-all -y
# sudo apt install npm git -y
git --version
```
## Установка самого софта
1. Закачиваем по SFTP `zip` архив скрипта. Далее
```sh
unzip /root/ZkSync-aio.zip
cd /root/ZkSync-aio-master

python3 --version
# узнаем версию и вставляем вместо 3.8 свою версию (3.8.10 это тоже считается как 3.8)
apt install python3.8-venv
python3.8 -m venv venv
source venv/bin/activate

pip install -r requirements.txt

# не нужно если используйте версию без лайта
pip install git+https://github.com/zksync-sdk/zksync-python.git
```
### исправление файлов для варианта с *zksync lite*
```
find / -name "site-packages"
find / -name "v01.py"
find / -name "responses.py"


cd /root/venv/lib/python3.8/site-packages/zksync_sdk/types # вот тут и находятся нужные нам файлы
# cd /root/ZkSync-aio-master/venv/lib/python3.8/site-packages
# cd /usr/local/lib/python2.7/site-packages


nano /root/venv/lib/python3.8/site-packages/zksync_sdk/types/responses.py
nano /usr/local/lib/python3.8/dist-packages/zksync_sdk/types/responses.py

nano /root/venv/lib/python3.8/site-packages/zksync_sdk/zksync_provider/v01.py
nano /usr/local/lib/python3.8/dist-packages/zksync_sdk/zksync_provider/v01.py

/root/ZkSync-aio-master/site-packages/




sudo apt install unrar
unrar unrar t ZkSync-aio-without-lite-3.rar
unrar x ZkSync-aio-without-lite-3.rar

```

## Найстройка софта
Настройка проходит в файле `config.py`
```
nano /root/ZkSync-aio-master/config.py
```

## Запуск софта
Работа в Tmux
```
tmux new -s <name-of-session> # Новая сессия
tmux ls
tmux attach -t <name-of-session> # Зайти в сессию
tmux kill-session -t <name-of-session> # Завершить сессию
```

С выводом stdout
```
cd /root/ZkSync-aio-master
cd /root/ZkSync-aio-without-lite
python3 main.py
```
В фоновом режиме
```
nohup python3 main.py > log.log 2>&1 &

pgrep -a python # Узнать номер процесса
kill <number> # Отменить выполнение процесса 
```

# Ошибка
![image](https://github.com/TatianaDEV7/Guides/assets/98289003/ea1ce3d6-d191-4c98-8185-2851a3f10ab9)

