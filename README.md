# astrix gpu miner
A fast GPU miner for Astrix using AstrixHash algorithm

```bash
USAGE:
    astrix-miner [OPTIONS] --mining-address <MINING_ADDRESS>

OPTIONS:
    -a, --mining-address <MINING_ADDRESS>
            The Astrix address for the miner reward

        --cuda-device <CUDA_DEVICE>
            Which CUDA GPUs to use [default: all]

        --cuda-disable
            Disable cuda workers

        --cuda-no-blocking-sync
            Actively wait for GPU result. Increases CPU usage, but removes delays that might result in red blocks. Can have lower workload.

        --cuda-nonce-gen <CUDA_NONCE_GEN>
            The random method used to generate nonces. Options: (i) xoshiro - each thread in GPU will have its own random state, creating a (pseudo-)independent xoshiro sequence (ii) lean - each GPU will have a single random nonce, and each GPU thread will work on nonce + thread id.
            
            [default: lean]

        --cuda-workload <CUDA_WORKLOAD>
            Ratio of nonces to GPU possible parrallel run [default: 64]

        --cuda-workload-absolute
            The values given by workload are not ratio, but absolute number of nonces [default: false]

    -d, --debug
            Enable debug logging level

        --devfund-percent <DEVFUND_PERCENT>
            The percentage of blocks to send to the devfund (minimum 2%)
            
            [default: 2]

    -h, --help
            Print help information

        --mine-when-not-synced
            Mine even when astrixd says it is not synced, only useful when passing `--allow-submit-block-when-not-synced` to astrixd  [default: false]

    -p, --port <PORT>
            Astrixd port [default: Mainnet = 34150]

    -s, --astrixd-address <ASTRIXD_ADDRESS>
            The IP of the astrixd instance
            
            [default: 127.0.0.1]

    -t, --threads <NUM_THREADS>
            Amount of CPU miner threads to launch [default: 0]

        --testnet
            Use testnet instead of mainnet [default: false]

    -V, --version
            Print version information
```

# GPU mining tutorial (Only for nvidia)
```bash
wget https://github.com/astrix-network/astrix-gpu-miner/releases/download/v0.2.3/astrix-gpu-miner-v0.2.3-linux.zip

unzip astrix-gpu-miner-v0.2.3-linux.zip

chmod +x astrix-miner

./astrix-miner --mining-address YourWalletAddress --astrixd-address YourNodeIpAddress --port 34150
```

⚠️  If missing lib
```bash
echo "deb http://archive.ubuntu.com/ubuntu jammy main" >> /etc/apt/sources.list
apt update
apt install libc6
```
