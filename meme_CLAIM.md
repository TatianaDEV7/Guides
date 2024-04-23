```
cd
git clone https://github.com/0xStarLabs/Meme-Coin-Farm

tmux new -s meme_star_claim

cd /root/Meme-Coin-Farm
python3 --version
# should be 3.10

mkdir /root/Meme-Coin-Farm/venv
python3.10 -m venv /root/Meme-Coin-Farm/venv
source /root/Meme-Coin-Farm/venv/bin/activate

cd /root/Meme-Coin-Farm
sudo apt-get install gcc python-dev libgmp3-dev
pip install -r requirements.txt
pip install requests

#RUN
tmux attach -t meme_star_claim
python main.py
```
Activity is no longer actually.
