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
## Найстройка софта
Настройка проходит в файле `config.py`
```
nano /root/zksync-aio/config.py
```

## Запуск софта
```
python3 main.py
# nohup python3 MAIN.py > log.log 2>&1 &
```
# Ошибка
![image](https://github.com/TatianaDEV7/Guides/assets/98289003/ea1ce3d6-d191-4c98-8185-2851a3f10ab9)

