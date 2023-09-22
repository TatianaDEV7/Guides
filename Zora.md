# Описание
Скрипт публичный, информация о работе выложена на оригинальной странице https://github.com/timfame-codespace/zora :
- Bridge from Ethereum to Zora
- Mint any NFT from your own list
- Earn mint.fun points
- Create collections
- Update collections

Здесь рассмотрим запуск скрипта на Ubuntu и какая будет комиссия.

Для скрипта можно приготовить:
- Создать новые кошельки https://cointool.app/createWallet/eth
- Пополнить с помощью [all-in-one](https://github.com/TatianaDEV7/all-in-one-v2/tree/main)
## Настройка и установка
```
git clone https://github.com/timfame-codespace/zora
```
Устанавливаем библиотеки :
```
pip3 install colorama==0.4.6
pip3 install eth_account==0.9.0
pip3 install pyTelegramBotAPI==4.12.0    # all-in-one 4.11.0
pip3 install Requests==2.28.2            # all-in-one 2.29.0
pip3 install requests_toolbelt==1.0.0
pip3 install retry==0.9.2
pip3 install termcolor==2.3.0
pip3 install ua_generator==0.1.8
pip3 install web3==6.0.0                 # all-in-one 6.2.0
```
Настраиваем:
- `files/wallets.txt` - кошельки с приватными ключами
- `files/proxies.txt` - соответствующие прокси для каждого кошелька
- `config.py` - Настройки
- `vars.py` - Вставляем данные контрактов для взаимодействия

Запуск с помошью tmux:
```
tmux new -s zora-session
dir
cd zora
python3 main.py

# tmux команды:
# tmux ls
# tmux attach -t zora-session
# tmux kill-server
# tmux kill-session -t zora-session
```
Запуск в фоне:
```
nohup python3 main.py > log.log 2>&1 &

Узнать процессы которые идут в фоновом режиме и ОТКЛЮЧИТЬ их:
# pgrep -a python
# kill 111111(номер)1111
```
