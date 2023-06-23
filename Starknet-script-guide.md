Это гайд для использования скрипта по Starknet.

Как известно скрипт использует node js и мы сейчас пройдемся по установке скрипта на `Ubuntu`.
## Подготовка
- скачиваем скрипт с гита себе в комп
- настраиваем
- зипуем с именем, допустим `starknet-script`
- кидаем на серв (можно с помощью mobaX tern)
- на серве анзип
```
unzip /root/starknet-script.zip
```
- установим нужное
```
sudo apt update && sudo apt upgrade -y
sudo apt install npm git -y

curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -
sudo apt-get install -y nodejs
```
- заходим в папку скрипта
```
cd /root/starknet-script
```
- установим скрипт
```
npm i
```
- Запускаем 

Скрипт можно запустить просто в ком строке
```
npm start
```
Или фоном с помощью tmux. Установим tmux:
```
sudo apt update && sudo apt install tmux -y
```
Запускаем сессию тмукс (название сессии любое, я выбрал `stark-scr`):
```
tmux new -s stark-scr
```
Переходим в папку со скриптом (папка у вас может по другому называться):
```
cd /root/starknet-script
```
Теперь запускаем сам скрипт:
```
npm start
```

### tmux команды
[Шпаргался от Losst](https://losst.pro/shpargalka-po-tmux). 

Список частых команд:

Выходим из сессии `Ctrl+b d` (Но сессия ДАЛЬШЕ продолжит работать в фоне): 

Лист с сессиями:
```
tmux ls
```
Опять конектимся к сессии:
```
tmux attach -t stark-scr
```
> !Только не закрывайте скрипт с помощью CTRL+C

Создание новой сессии:
```
tmux new -s <name-of-session>
```
Закрыть все сессии:
```
tmux kill-server
```
закрыть определенную сессию:
```
tmux kill-session -t <name-of-session>
```
