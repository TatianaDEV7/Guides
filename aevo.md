## Настройка
#### 1. **Прокси**:
- Строка 43 `USE_PROXY = True` в файле `/root/aevo/config.py`
- Прокси пишем в файл `/root/aevo/proxies.txt` в формате `http://username:password@ip:port`
- ❗️Должно быть количество_строк_с_приватниками = количество_строк_с_прокси

#### 2. **Автоматический вывод USDC и ETH c биржи OKEX на мульты**:
- Вбиваем данные от Okex API KEY в файл `/root/aevo/assets/okx_data/okx_data.py` 
- Строка 51 `okx_withdraw = True` в файле `/root/aevo/config.py`
- Строки 60 61 в файле `/root/aevo/config.py`
```
    usdc_amount = [400, 500]
    eth_amount = [0.00091, 0.00151]
```
- ❗️Скрипт умножает заданное количество эфира на 2 и выводит с ОКХ, поэтому вписываем меньше чем надо в 2 раза (usdc выводит правильно).
- Комиссия за открытие+закрытие LONG на площадке AEVO в сети OP ~ 0.0005 eth при газе в 25 gwei

#### 3. Сколько раз открывать+закрывать Long позиции
- Строка 9 `POSITIONS_COUNT = [2, 3]` в файле `/root/aevo/config.py`

#### 4. Вывод с мультов обратно на OKEX
- Строка 52 `okx_deposit = True` в файле `/root/aevo/config.py`
- Вбиваем с красной строки Окекс кошельки для пополнения Окекс аккаунта в файл `/root/aevo/assets/okx_data/okx_wallets.txt`

## Запуск на Ubuntu
Требуется Python 3.9
```
unzip /root/aevo-master-short.zip -d /root/aevo

tmux new -s aevo
tmux attach -t aevo
cd /root/aevo
python3 --version
# should be 3.9

mkdir /root/aevo/venv && cd /root/aevo/venv
python3.9 -m venv /root/aevo/venv
source /root/aevo/venv/bin/activate

cd /root/aevo
sudo apt-get install gcc python-dev libgmp3-dev
pip install -r requirements.txt
pip install requests

#RUN
tmux attach -t aevo
python main.py
```
