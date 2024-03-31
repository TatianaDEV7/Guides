### Settings
 - `files/evm_wallets.txt` - Wallets with EVM private keys
 - `files/proxies.txt` - Corresponding proxies for wallets
 - `files/twitters.txt` - Corresponding twitters for wallets
 - `files/emails.txt` - Corresponding emails for wallets
 - `files/discords.txt` - Corresponding discords for wallets. Can be empty if not needed
 - `config.toml` - Custom settings

### Config
 - `FAKE_TWITTER` - Verify Twitter tasks without real Twitter actions
 - `GALXE_CAMPAIGN_IDS` - Campaigns to complete, parent campaigns are supported
 - `HIDE_UNSUPPORTED` - Don't log unsuccessful completing of unsupported tasks

```
git clone https://github.com/the-laziest-coder/galxe-aio

# Проверим список версий  и выбор 3.11:
python3 --version
update-alternatives --list python3
update-alternatives --config python3

tmux new -s galxe-aio-laziest
tmux attach -t galxe-aio-laziest

python3.11 -m venv /root/galxe-aio/venv
source /root/galxe-aio/venv/bin/activate
cd /root/galxe-aio
pip install -r requirements.txt
pip install requests
playwright install

python main.py
python checker.py
```
