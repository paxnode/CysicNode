```markdown
# CysicNode

This repository contains instructions and scripts for setting up the Cysic Phase II: Genesis Node Verifier.

---

## Requirements
1. A Linux-based system.
2. A valid reward address (starts with `0x`).
3. Basic knowledge of Linux terminal commands.

---

## Steps to Set Up the Cysic Node

### 1. Connect to the Testnet
- Go to: [Cysic Testnet Dashboard](https://testnet.cysic.xyz/m/)
- Connect your wallet.

### 2. Submit Code and Register
- Submit any of the following codes to the dashboard:
  `9e07c | 24171 | df202 | 5bc76 | 0d611 | bc8ea | 26236`
- Register your account and submit your details.

### 3. Run the Verifier Node

#### **Run the setup script**
- Replace `0x-Fill-in-your-reward-address-here` with your wallet's reward address.
- Run the following commands:
  ```bash
  curl -L https://github.com/cysic-labs/phase2_libs/releases/download/v1.0.0/setup_linux.sh > ~/setup_linux.sh && \
  bash ~/setup_linux.sh 0x-Fill-in-your-reward-address-here
  ```

#### **Start the Verifier**
- Navigate to the verifier directory:
  ```bash
  cd ~/cysic-verifier/
  bash start.sh
  ```

#### **Run in the Background**
- Use `screen` to keep the process running in the background:
  ```bash
  screen -S cysic
  ```
  - After starting, detach the session with `Ctrl + A + D`.

### 4. Check Logs and Status
- Reattach the screen session to check logs:
  ```bash
  screen -r cysic
  ```
- To stop the session, press `Ctrl + C` or kill the process.

---

## Additional Resources
- Official Guide: [Phase II Genesis Node Verifier Guide](https://medium.com/@cysic/phase-ii-genesis-node-verifier-guide-6a09720cba4e)
- Cysic Updates: [Twitter (@cysic_xyz)](https://x.com/cysic_xyz/status/1858879355969302982)

---

**Important:** Always keep your private keys and mnemonic files safe. They are stored at `~/.cysic/keys/`.

---

## License
MIT License.
```

---

### **Script Files**

1. **`setup_linux.sh`**
   If you need a placeholder for `setup_linux.sh`, here's an example:
   ```bash
   #!/bin/bash
   REWARD_ADDRESS=$1

   if [ -z "$REWARD_ADDRESS" ]; then
     echo "Error: No reward address provided!"
     echo "Usage: $0 <0x-reward-address>"
     exit 1
   fi

   echo "Setting up the Cysic Verifier for reward address: $REWARD_ADDRESS"

   # Install dependencies
   sudo apt update && sudo apt install -y curl wget git screen

   # Download verifier
   curl -L https://github.com/cysic-labs/phase2_libs/releases/download/v1.0.0/verifier.tar.gz -o verifier.tar.gz

   # Extract files
   tar -xzvf verifier.tar.gz -C ~/
   mv ~/verifier ~/cysic-verifier

   echo "Setup complete. Run 'cd ~/cysic-verifier && bash start.sh' to start the verifier."
   ```

2. **`start.sh`**
   Example for a `start.sh` file:
   ```bash
   #!/bin/bash

   echo "Starting Cysic Verifier Node..."
   EXECUTABLE="verifier"

   if [ ! -f "$EXECUTABLE" ]; then
       echo "Error: Verifier executable not found!"
       exit 1
   fi

   # Run the verifier
   ./verifier --config config.json
   ```

---

Setelah file-file ini ditambahkan ke repository Anda, gunakan perintah berikut untuk mengunggah ke GitHub:

```bash
git add .
git commit -m "Add README and setup/start scripts"
git push
```
