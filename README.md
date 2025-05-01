Put all of these commands in your VPS terminal one by one
```
sudo apt update && sudo apt upgrade -y
```

## Essenstials 
```
sudo apt install -y \
  curl \
  git \
  wget \
  nano \
  tmux \
  htop \
  nvme-cli \
  lz4 \
  jq \
  make \
  gcc \
  clang \
  build-essential \
  autoconf \
  automake \
  pkg-config \
  libssl-dev \
  libleveldb-dev \
  libgbm1 \
  bsdmainutils \
  ncdu \
  unzip \
  tar

```

## Installing python 
```
sudo apt-get install -y \
  python3 \
  python3-pip \
  python3-venv \
  python3-dev
```

## Node and Yarn 
```
sudo apt-get update && curl -fsSL https://deb.nodesource.com/setup_22.x | sudo -E bash - && sudo apt-get install -y nodejs && node -v && sudo npm install -g yarn
```


## Install Docker 
```
for pkg in docker.io docker-doc docker-compose podman-docker containerd runc; do
  sudo apt-get remove $pkg
done

sudo apt-get update
sudo apt-get install -y ca-certificates curl gnupg

sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt-get update
sudo apt-get install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

```





---
## Install Python & PIP 
```
sudo apt install python3 -y && sudo apt install python3-pip -y
```
![image](https://github.com/user-attachments/assets/9608067a-c0a1-4572-87cc-d606c239c72a)


## Install Dev. tool 
```
sudo apt install python3-dev python3-venv build-essential -y
```
![image](https://github.com/user-attachments/assets/5a138859-9483-4028-b676-c942a3b5c034)


## Install Yarn
```
sudo apt-get update && sudo apt-get install -y curl gnupg apt-transport-https && curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add - && echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list && sudo apt-get update && sudo apt-get install -y yarn
```



# Clone RL-Swarm Repo 
### RL Swarm is an open source system for peer-to-peer reinforcement learning over the internet. Running a swarm node allows you to train your personal model against the swarm intelligence. 

```
git clone https://github.com/gensyn-ai/rl-swarm
```

### Navigate in 
```
cd rl-swarm
```

![image](https://github.com/user-attachments/assets/d033e5ce-ff44-49d8-97c6-c0268061aeb3)


### Install screen 
```
sudo apt install screen -y
```

### Create screen for process  
```
screen -S rlswarm
```
and navigate in rl-swarm again
```
cd rl-swarm
```

### Install and Run Swarm 
```
python3 -m venv .venv
source .venv/bin/activate
./run_rl_swarm.sh
```
---

- After Running the Above command it will promt `Would you like to connect to the Testnet? [Y/n]` Enter `Y`

- After than it will promt `>> Which swarm would you like to join (Math (A) or Math Hard (B))? [A/b]`  Enter   `a`

- After than it will promt `>> How many parameters (in billions)? [0.5, 1.5, 7, 32, 72]`    

👇See below and Choose the model Depends on Your System! 

<pre>
- Qwen 2.5 0.5B                - Recommended 4GB RAM, (1GB DOWNLOAD)
- Qwen 2.5 1.5B                - Recommended 8GB RAM, (4GB DOWNLOAD)
- Qwen 2.5 7B                  - Recommended 16GB RAM, (15GB DOWNLOAD)
- Qwen 2.5 32B (4 bit)         - Recommended 50GB RAM, (35GB DOWNLOAD)
- Qwen 2.5 72B (4 bit)         - Recommended 100GB RAM, (70GB DOWNLOAD)
</pre>
    
- After that A web Pop-Up will appear, It will ask u to Login ( if no web pop-up then u have to paste this on ur brower `http://localhost:3000/` 


- Now Login With Your Email Id, Enter OTP and back to ur Terminal/Wsl? **( VPS users check FAQ1 )**

![image](https://github.com/user-attachments/assets/1fed4b08-4ec4-44de-868c-b2d314cd2a02)


- Now U can see A `ORG_ID` On ur Terminal..Save it!

* Now It will promt `Would you like to push models you train in the RL swarm to the Hugging Face Hub? [y/N]` Enter `N`

![2025-04-01_22h30_09](https://github.com/user-attachments/assets/a48558bd-9f88-4ac9-8c26-2b437ac2e5ac)

## Search your Node ID
### in @gensyntrackbot from Telegram to see if your Node ID is binded with a EVM CA, if not delete your userdata from rl-swarm/modal-login/temdata/ and delete both files in there -> rerun the swarm and login with different email.
![image](https://github.com/user-attachments/assets/7edd4203-c2b4-45ca-ae30-61720a1a1282)
### You can find your node name in your terminal, its a animal name with your node id behind it (starts with QM) after it starts training rounds (can take an hour or less)
![image](https://github.com/user-attachments/assets/0d2511a2-b69f-4680-b0bc-f0659e135a42)

---

# 1️⃣ How to Login or access  http://localhost:3000/ in VPS? 📶

* Open a new Terminal and login ur vps 

* Allow Incoming connection on VPS

```
sudo apt install ufw -y
sudo ufw allow 22
sudo ufw allow 3000/tcp
```

* Enable ufw

```
sudo ufw enable
```

* Install cloudflared on the VPS

```
wget -q https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-amd64.deb
````

```
sudo dpkg -i cloudflared-linux-amd64.deb
```

* Check version

```
cloudflared --version
```

* Make sure your Node is running on port 3000 in Previous Screen

* Run the tunnel command

```
cloudflared tunnel --url http://localhost:3000
```

* Access the Link from your local machine

    
    ![image](https://github.com/user-attachments/assets/c5bdfec5-123d-4625-8da8-f46269700950)

* Now follow Login!
 
* Done!✅
