# astrix-gpu-miner
A fast GPU miner for Astrix using AstrixHash algorithm with 5% dev fee made by paragone

You can modify the % devfund with --devfund-percent


# GPU mining tutorial (Only for nvidia)
```bash
wget https://github.com/astrix-network/astrix-gpu-miner-v0.2.1/releases/download/v0.2.1/astrix-gpu-miner-v0.2.1-linux.zip

unzip astrix-gpu-miner-v0.2.1-linux.zip

chmod +x astrix-miner

./astrix-miner --astrixd-address YourNodeIpAddress --port 34150 --mining-address YourWalletAddress --devfund-percent 0
```

⚠️  If missing lib
```bash
echo "deb http://archive.ubuntu.com/ubuntu jammy main" >> /etc/apt/sources.list
apt update
apt install libc6
```
