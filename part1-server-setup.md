# 🧱 Part 1: Server Initial Configuration

Before you deploy anything, you need a secure and stable server environment. This part walks you through preparing a fresh Linux-based virtual machine (VPS or VDS) for deployment.

---

## ✅ What You'll Do

- Create a non-root user
- Set up SSH key authentication
- Update system packages
- Configure basic firewall
- Optional: Set timezone and hostname

---

## 🖥️ Step 1: Connect to Your Server

Use the credentials your provider gave you. Usually, you’ll SSH in as `root`:

```bash
ssh root@your-server-ip
```

---

## 👤 Step 2: Create a New User

Create a new user to avoid using `root` for everything.

```bash
adduser deployer
```

Give it a secure password when prompted.

Add the user to the `sudo` group:

```bash
usermod -aG sudo deployer
```

---

## 🔐 Step 3: Set Up SSH Key Authentication

On your **local machine**, generate an SSH key if you don’t already have one:

```bash
ssh-keygen -t ed25519
```

Copy the public key to your server:

```bash
ssh-copy-id deployer@your-server-ip
```

Now try logging in as your new user:

```bash
ssh deployer@your-server-ip
```

✅ If this works, you can disable password-based SSH login for more security (optional, see Step 6).

---

## 🔄 Step 4: Update & Upgrade System Packages

```bash
sudo apt update && sudo apt upgrade -y
```

Install some common tools:

```bash
sudo apt install -y curl git ufw
```

---

## 🌍 Step 5: (Optional) Set Timezone and Hostname

Set the timezone:

```bash
sudo timedatectl set-timezone YOUR_TIMEZONE
```

Example:

```bash
sudo timedatectl set-timezone Europe/Paris
```

Set a hostname:

```bash
sudo hostnamectl set-hostname myapp-server
```

---

## 🔥 Step 6: Set Up a Basic Firewall

Enable UFW and allow essential ports:

```bash
sudo ufw allow OpenSSH
sudo ufw allow http
sudo ufw allow https
sudo ufw enable
```

Check the status:

```bash
sudo ufw status
```

---

## 🔒 Step 7: (Optional) Disable Root SSH Login

Edit the SSH config:

```bash
sudo nano /etc/ssh/sshd_config
```

Find these lines and change them:

```
PermitRootLogin no
PasswordAuthentication no
```

Then restart SSH:

```bash
sudo systemctl restart ssh
```

⚠️ Warning: Make sure your new user can log in with SSH **before** doing this.

---

## ✅ You're Done!

Your server is now:
- Using a secure user instead of root
- Accepting only SSH keys
- Protected by a basic firewall
- Up to date with system packages

➡️ Next step: [Part 2: Deploying the App with Docker](./part2-docker-app.md)
```

---

Want me to move on to **Part 2: Docker & Compose Setup**?
