# RL Swarm Node Run Full Guide (PC and VPS for Both)

### Offical Docs Guide - https://github.com/gensyn-ai/rl-swarm?tab=readme-ov-file

1️⃣ Dependencies for WINDOWS & LINUX & VPS
```
sudo apt update && sudo apt upgrade -y
```
```
sudo apt install -y curl git wget nano tmux htop nvme-cli lz4 jq make gcc clang build-essential autoconf automake pkg-config libssl-dev libleveldb-dev libgbm1 bsdmainutils ncdu unzip tar
```

2️⃣ Install Python & Node Js & Yarn & NPM & Pip & Dev. tool
```
sudo apt-get install python3 python3-pip python3-venv python3-dev -y
```
```
sudo apt-get update && curl -fsSL https://deb.nodesource.com/setup_22.x | sudo -E bash - && sudo apt-get install -y nodejs && node -v && npm -v && sudo npm install -g yarn && yarn -v
```
```
sudo apt install -y python3 && sudo apt install -y python3-pip && python3 --version && pip3 --version
```
```
sudo apt install python3-dev python3-venv build-essential -y
```
```
sudo apt-get update && sudo apt-get install -y curl gnupg apt-transport-https && curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add - && echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list && sudo apt-get update && sudo apt-get install -y yarn && yarn --version
```

3️⃣ Hugging Face Access Token (Optional)
[Hugging Face Security Tokens](https://huggingface.co/docs/hub/en/security-tokens)
- Sign up , verify and create account
- Go to Menu, click the Access token 
- Create a Write access token and Done

4️⃣ Download Some Files
```
git clone https://github.com/gensyn-ai/rl-swarm/
cd rl-swarm
```

For VPS Only
```
apt install screen -y
```
```
screen -S rlswarm
```

5️⃣ Install and Run RL Swarm
```
python3 -m venv .venv
source .venv/bin/activate
./run_rl_swarm.sh
```
Put answer 'Y' (just press enter)

Wait till you see waiting for UserData.json to be created

Then open Browser and Input & Login by Google - http://localhost:3000/

#writing continue............


## Backup your Key
```
cat ~/rl-swarm/modal-login/temp-data/userApiKey.json
```
```
cat ~/rl-swarm/modal-login/temp-data/userData.json
```
