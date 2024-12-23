```markdown
CysicNode

This repository contains instructions and scripts for setting up the Cysic Phase II: Genesis Node Verifier.

---

Requirements
1. A Linux-based system.
2. A valid reward address (starts with `0x`).
3. Basic knowledge of Linux terminal commands.

---

Steps to Set Up the Cysic Node

1. Connect to the Testnet
- Go to: [Cysic Testnet Dashboard](https://testnet.cysic.xyz/m/)
- Connect your wallet.

2. Submit Code and Register
- Submit any of the following codes to the dashboard:
  `N/A | N/A | N/A | N/A | N/A | N/A | N/A`
- Register your account and submit your details.

3. Run the Verifier Node

Run the setup script
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
