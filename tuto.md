# Min Specs
![image](https://github.com/user-attachments/assets/fa8c6bb7-292d-46df-9180-c48322065a62)
The node won't work on low specs devices, It can cause system crashing if you try on Low Specs Devices (Like a fool)
---

```
sudo apt update && sudo apt install -y python3 python3-venv python3-pip curl wget screen git lsof
```
Check Python Version
```
python3 --version
```
```
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash - && sudo apt update && sudo apt install -y nodejs
```


# 👨🏻‍💻 Start The Node

```
git clone https://github.com/gensyn-ai/rl-swarm.git
```
```
screen -S gensyn
````
```
cd rl-swarm
```
```
python3 -m venv .venv
source .venv/bin/activate
```
```
cd modal-login
```
```
cd modal-login
```
```
cd ..
```

```
./run_rl_swarm.sh
```
- After Running the Above command it will promt `Would you like to connect to the Testnet? [Y/n]` Enter `Y`


# 1️⃣ How to Login or access  http://localhost:3000/ in VPS? 📶


Allow Incoming connection on VPS
```
sudo apt install ufw -y
sudo ufw allow 3000/tcp
```

```
sudo ufw enable
```

Install cloudflared on the VPS
```
wget -q https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-amd64.deb
````

```
sudo dpkg -i cloudflared-linux-amd64.deb
```
```
cloudflared --version
```

Make sure your Node is running on port 3000 in Previous Screen

```
cloudflared tunnel --url http://localhost:3000
```

Access the Link from your local machine
![image](https://github.com/user-attachments/assets/d883fe1e-37ed-4c4e-a05c-2296cd3e9c6e)


- Now Login With Your Email Id, Enter OTP and back to your Terminal
- Now U can see A `ORG_ID` On ur Terminal..Save it!
SAVE IT!!!


- It will promt `Would you like to push models you train in the RL swarm to the Hugging Face Hub? [y/N]` Enter `N`


It will Generate Logs after a while


Detach from `screen session`
Use `Ctrl + A` and then press `D`
Attach to gensyn Screen to see Logs
```
screen -r gensyn
```
