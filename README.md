# Union-Ceremony-Tutorial
This tutorial provides a detailed guide to participate in a Union Ceremony using cryptographic protocols. The goal is to ensure a secure and verified process.

To create a **detailed and professional tutorial** for the **Union-Ceremony** on your GitHub, you want to ensure the instructions are precise, engaging, and easy to follow, with a focus on both clarity and professionalism. Here is a **structured, step-by-step breakdown** that includes more **in-depth explanations, illustrations**, and **best practices** for users looking to follow your guide.

---

## Union-Ceremony Participation Guide

### Introduction
In this guide, you’ll learn how to participate in the **Union Network Cryptographic Ceremony** using Docker. This ceremony is part of a decentralized effort to generate secure cryptographic parameters for Union's network, enabling secure and private transactions. By contributing, you help ensure the security and integrity of the system, and as a reward, you'll receive tokens.

---

### Prerequisites
Before starting, make sure the following requirements are met:

#### Software Requirements:
1. **Operating System**: Linux (preferably Ubuntu), macOS, or Windows with WSL2.
2. **Docker**: You should have Docker installed on your machine.
   - **[Install Docker](https://docs.docker.com/get-docker/)** if you don't already have it.
3. **Stable Internet Connection**: Your system must remain connected to the internet throughout the ceremony.

---

### Step 1: Set Up Your Environment
First, you'll need to prepare your local environment and download the necessary Docker image. The following steps will help you do this:

1. **Open a terminal** in your system.
   
2. **Run the following command**:
   ```bash
   mkdir -p ceremony && sudo docker pull ghcr.io/unionlabs/union/mpc-client:latest && \
   sudo docker run -v $(pwd)/ceremony:/ceremony -w /ceremony -p 4919:4919 --rm -it \
   ghcr.io/unionlabs/union/mpc-client:latest
   ```

#### Breakdown of this command:
- `mkdir -p ceremony`: Creates a new directory named `ceremony`.
- `sudo docker pull ghcr.io/unionlabs/union/mpc-client:latest`: Pulls the Docker image for the MPC client.
- `docker run ...`: Runs the Docker container while exposing port `4919`, mounting the current working directory (`$(pwd)`), and creating a volume for ceremony data.

#### Best Practice:
- Make sure that **Docker** is running with sufficient system resources (CPU and RAM), as running cryptographic processes can be resource-intensive.

---

### Step 2: Running the Ceremony
Once the Docker container is running, the ceremony process begins. Follow the instructions below carefully:

#### 1. **Generate a Secret Key**:
   - Visit the ceremony link provided in the terminal output, or directly visit:
     - **[Union Ceremony Link](https://ceremony.union.build/)**
   - On the website, **click** on the `Generate Secret` button.
   - **Download** the generated secret and store it securely. This file is critical for your participation in the ceremony.

   > ⚠️ **Important**: Keep this secret file private and do not share it with anyone.

#### 2. **Store Your Secret**:
   After downloading, the website will prompt you to confirm that you have securely stored your secret. Click on the **"I’ve stored my secret"** button to continue.

---

### Step 3: Configure Your Wallet for Rewards
You’ll need to provide your **Union Network** wallet address to receive rewards for participating in the ceremony.

#### Steps:
1. **Get a Wallet**: If you don’t already have a Union Network wallet, you can set one up using **Keplr**:
   - **[Add Union to Keplr](https://chains.keplr.app/)**.
   
2. **Enter Your Address**: After setting up the wallet, copy your Union address and enter it on the ceremony page to register for rewards.

---

### Step 4: Participate in the Ceremony
Once your secret is generated and your wallet address is provided, you are ready to participate:

1. **Contribution Process**:
   - Once the ceremony begins, your terminal will show various statuses:
     - `Awaiting orders`: Waiting for your system to be queued for contribution.
     - `Starting contribution`: Your system is contributing to the cryptographic parameters.
     - `Contributing`: Active contribution in progress.
     - `Verifying`: Final verification steps.

2. **Time Requirements**:
   - The ceremony can take anywhere from **5 to 60 minutes**, depending on network conditions and your system’s performance.
   - **Do not close the terminal or browser** during this process.

3. **Final Confirmation**: Once your contribution is complete, the browser and terminal will notify you.

#### Best Practice:
- Ensure your system does not enter sleep mode or lose internet connectivity while contributing.

---

### Step 5: Post-Ceremony Actions
Once you have completed your contribution:

- **Confirm Receipt of Rewards**: Check your Union wallet for the rewards. Depending on the network, this may take some time.
- **Verify Ceremony Participation**: Optionally, you can verify your participation by visiting the ceremony page or checking for any confirmation email.

---

### Troubleshooting
Here are some common issues you might encounter during the ceremony:

#### 1. **Docker Errors**:
   - Ensure that Docker is up-to-date. Use the following command to check your version:
     ```bash
     docker --version
     ```
   - If the container fails to start, check if the Docker daemon is running:
     ```bash
     sudo systemctl start docker
     ```

#### 2. **Network Issues**:
   - Ensure you have a stable internet connection. If your connection drops during the contribution phase, restart the process from the beginning.

---

### Conclusion
By following this guide, you’ve successfully participated in the **Union Network Cryptographic Ceremony**. Your contribution ensures the security and privacy of Union's network, and you’ve earned tokens as a reward.

---

### Bonus: Automating the Ceremony
For advanced users, consider automating the ceremony process using **cron jobs** or **shell scripts**. This way, you can automatically pull the Docker image and participate without manual intervention.

```bash
#!/bin/bash
# Script to automate Union Ceremony participation

mkdir -p ceremony
sudo docker pull ghcr.io/unionlabs/union/mpc-client:latest
sudo docker run -v $(pwd)/ceremony:/ceremony -w /ceremony -p 4919:4919 --rm -it \
ghcr.io/unionlabs/union/mpc-client:latest
```
You can schedule this script using cron:
```bash
crontab -e
# Add the following line to run the script daily at 2 AM
0 2 * * * /path/to/union_ceremony.sh
```
