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
- Запускаем его
```
npm start
```
