# Cycle Server Git & SSH Setup Guide

## 1. Connect to Cycle Server
```bash
ssh username@cycle3.eecs.ku.edu
```

---

## 2. Check Git Version
```bash
git --version
```

---

## 3. Configure Git
```bash
git config --global user.name "name"
git config --global user.email "email"
git config --global core.editor "nano"   # nano is easier for beginners
```

Check username:
```bash
git config --global user.name
```

---

## 4. Generate SSH Key
```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```
> Just press Enter through all prompts to save with default settings.

---

## 5. Start SSH Agent
```bash
eval "$(ssh-agent -s)"
```
Output will look like:
```
Agent pid 1234 (some number)
```

Add the SSH key:
```bash
ssh-add ~/.ssh/id_ed25519
```

---

## 6. Copy Public Key
```bash
cat ~/.ssh/id_ed25519.pub
```
Copy the output and paste it into **GitHub → Settings → SSH Keys**.

---

## 7. Test Connection
```bash
ssh -T git@github.com
```

---

## 8. If SSH Port 22 is Blocked
Edit the SSH config:
```bash
nano ~/.ssh/config
```

Add the following block:
```
Host github.com
  Hostname ssh.github.com
  Port 443
  User git
```

---

## 9. Create and Clone Repository
1. Create a new repo on GitHub named **lab-1**.  
2. Clone it:
```bash
git clone git@github.com:git-username/lab-1.git
```

---

## 10. Create a New File
```bash
nano lab1.c
```
(Paste your code here.)

---

## 11. Git Workflow
Check status:
```bash
git status
```

Stage file(s):
```bash
git add .         # or git add lab1.c
```

Commit changes:
```bash
git commit -m "This is my first commit"
```

Push to GitHub:
```bash
git push
```
# Cycle-server-setup
