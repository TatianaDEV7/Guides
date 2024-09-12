# Софт для слейма дропа [Pump scroll](https://scrollpump.xyz/airdrop) От [czbag](https://github.com/czbag)
Ссылка на софт: https://github.com/czbag/scroll
Ссылка на пост: https://t.me/sybilwave/454

```
git clone https://github.com/czbag/scroll.git
cd scroll

python3 --version
update-alternatives --list python3
update-alternatives --config python3
# need 3.11
tmux new -s scroll_pump
# tmux attach -t scroll_pump
python3.11 -m venv /root/scroll/venv
source /root/scroll/venv/bin/activate
cd /root/scroll
pip install -r requirements.txt

sed -i 's/rawTransaction/raw_transaction/g' /root/scroll/modules/account.py
```

Before you start, configure:
- the required modules in modules_settings.py
- setings.py
- accounts.py

```
python main.py
```
