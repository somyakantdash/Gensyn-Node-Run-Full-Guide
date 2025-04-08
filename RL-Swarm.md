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

## Open Another Window for VPS to Login ur LocalHost

Download Some Dependencies 
```
sudo apt install ufw -y
sudo ufw allow 3000/tcp
```

Enable ufw
```
sudo ufw enable
```

Install Cloudflared
```
wget -q https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-amd64.deb
````
```
sudo dpkg -i cloudflared-linux-amd64.deb
```
```
cloudflared --version
```
- Make sure your Node is running on port 3000 in Previous Screen
- Run the tunnel command
```
cloudflared tunnel --url http://localhost:3000
```
Access the Link from your local machine

![image](https://github.com/user-attachments/assets/c5bdfec5-123d-4625-8da8-f46269700950)

Then Login > Then Go to the Previous Screen to Check ur Logs

```
PRESS CTRL+A+D (to run ur node continuously)
```
- To check ur Node Again
```
screen -r rlswarm
```
Save your `swarm.pem` file to your Local Device from VPS
```
scp USERNAME@YOUR_IP:~/rl-swarm/swarm.pem ~/swarm.pem
```
```
scp USERNAME@YOUR_VPS_IP:~/rl-swarm/swarm.pem C:\Users\YourUsername\Desktop\
```
- Replace ur "USERNAME" & "YOUR_IP" with your actual VPS Username & IP u got already. Replace YourUsername with your actual Windows username

Save your `swarm.pem` file to your Desktop screen on your PC from WSL
```
cp ~/rl-swarm/swarm.pem /mnt/c/Users/YourUsername/Desktop/
```
- Replace YourUsername with your actual Windows username

To check your Windows username
```
echo $USER
```

## 🔶For Next Day Run This Command (Windows)

#1 Open WSL and Put this Command 
```
cd rl-swarm
```
```
python3 -m venv .venv
source .venv/bin/activate
./run_rl_swarm.sh
```

## Delete Node File
```
rm -rf ~/rl-swarm
```

## Backup your Key
```
cat ~/rl-swarm/modal-login/temp-data/userApiKey.json
```
```
cat ~/rl-swarm/modal-login/temp-data/userData.json
```
