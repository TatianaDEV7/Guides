 Распаковка
```
unzip /root/dfk-farmer-master.zip
```
Установим необходимое
```
apt install python3-pip
python3 -V
pip install --upgrade pip
cd /root/dfk-farmer-master
pip install telebot fake_useragent
pip3 install -r requirements.txt
# pip install web3==6.4
```
Предупреждение чисто для заметки:
```
WARNING: Running pip as the 'root' user can result in broken permissions and conflicting behaviour with the system package manager. It is recommended to use a virtual environment instead: https://pip.pypa.io/warnings/venv
```
Настройка:
```
# Настройка идет в файле config.py
shuffle = 1 # это рандом

min_balance_jewel = 10

from_amount = 2  # не менять!
to_amount = 2.3 # ставим 2-3

part_jewel_to_klaytn = 40 # ставим 35-40
part_for_buy_items = 8 # ставим 7-10
# RPC брать тут https://nodereal.io/ и настраивать polygon и klaytn
# RPC dfk можно оставить

# задержку ставим побольше, допустим:
delay_between_swaps = (100, 130)
delay_between_bridges = (130, 170)
```
Запускаем
```
python3 main.py
```
