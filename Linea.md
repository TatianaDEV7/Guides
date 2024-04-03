```
unzip /root/LineaPark-free.zip
# Проверим список версий  и выбор 3.11:
python3 --version
update-alternatives --list python3
update-alternatives --config python3


tmux new -s lineapark
tmux attach -t lineapark

cd /root/LineaPark-free
python3.11 -m venv /root/LineaPark-free/venv
source /root/LineaPark-free/venv/bin/activate
cd /root/LineaPark-free
pip install -r requirements.txt
pip install requests

python main.py
```
