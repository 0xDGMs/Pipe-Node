# Pipe-Node-Devent

# INSTALL
```
curl -L -o pop "https://dl.pipecdn.app/v0.2.8/pop"
```
# Grant Permission
```
chmod +x pop
```
# Update system
```
sudo apt update && sudo apt upgrade -y
```
**Download Important Setups**
```
sudo apt install curl iptables build-essential git wget lz4 jq make gcc nano automake autoconf tmux htop nvme-cli libgbm1 pkg-config libssl-dev libleveldb-dev tar clang bsdmainutils ncdu unzip libleveldb-dev screen ufw -y
```
**Install nano editor**
```
sudo apt install nano -y
```
# Make Directory
```
mkdir download_cache
```
# Sign-up With Command
```
./pop --signup-by-referral-route 8ec0f60493002bb
```
**Save your node.json file**
```
nano ~/node_info.json
```
Just copy everything on the file and save just as it in your google drive as a doc

#Create a Systemd Process
```
sudo nano /etc/systemd/system/pop-node.service
```
Paste in this configuration but you have to edit the following
```
[Unit]
Description=POP Node Service
After=network.target

[Service]
Type=simple
User="your_username"
WorkingDirectory=/home/"your_username"
ExecStart=/usr/bin/sudo /home/"your_username"/pop \
  --ram "your_ram" \
  --max-disk "your_disk_space" \
  --cache-dir /data \
  --pubKey "your_solana_address" \
  --enable-80-443
Restart=always
RestartSec=30
StandardOutput=journal
StandardError=journal
Environment="PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"

[Install]
WantedBy=multi-user.target
```
**NOTE**

Edit the following 

"your_username" - To your computer username

"your_ram" - To the ram of ur computer

"your_disk_space" - To the storage of your computer

"your_solana_address" - To your solana address

**Save and exit**

Press Ctrl+O to save, then Enter

Press Ctrl+X to exit

**Load file**
```
sudo systemctl daemon-reload
sudo systemctl enable pop-node.service
```

# Manage your node
Start
```
sudo systemctl start pop-node.service
```
Check Status
```
sudo systemctl status pop-node.service
```
![pipe node 2](https://github.com/user-attachments/assets/477755b0-ede1-4826-9cfd-c6fd262a200e)

View Logs
```
journalctl -u pop-node.service -f --since "60 minutes ago"
```
![pipe node 1](https://github.com/user-attachments/assets/7d30b841-1714-4cb2-b66f-6254bd90ba91)

Stop
```
sudo systemctl stop pop-node.service
```
Restart
```
sudo systemctl restart pop-node.service
```
# Pipe Node
Node Status
```
./pop --status
```
![pipe node 3](https://github.com/user-attachments/assets/f6dd006c-91d3-4319-8312-1b251998f616)

Check points
```
./pop --points
```
Generate referral
```
./pop --gen-referral-route
```
**To Start Next Day**

Run 'Manage your node' COMMAND

Docs- https://docs.pipe.network/devnet-2

Join TG for more Updates: https://t.me/JBondUpdate
