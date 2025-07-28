# GitHub SSH Setup #

## 1. SSH Key Generation & Naming Convention ##

- **[vm_name-random5chars]**: Name of your VM, e.g. `vmachineordering-abc12`
- **[repo_name]**: GitHub repo name, e.g. `ordering-core-api`
- **Example:** `vmachineordering-abc12-ordering-core-api`

**Generate SSH key:**
```
ssh-keygen -t ed25519 -C "[vm_name]-[random5chars]-[repo_name]" -f ~/.ssh/[vm_name]-[random5chars]-[repo_name]
```

**Example:**
```
ssh-keygen -t ed25519 -C "vmachineordering-abc12-ordering-core-api" -f ~/.ssh/vmachineordering-abc12-ordering-core-api
```

---

## 2. Add Public Key to GitHub

**Print the public key:**
```
cat ~/.ssh/vmachineordering-abc12-ordering-core-api.pub
```

- Copy the output (starts with `ssh-ed25519 ...`)
- Go to **GitHub Repository > Settings > Deploy keys > Add Deploy key**
- Paste the key  
- **Title example:** `vmachineordering-abc12-ordering-core-api`

---

## 3. SSH Config

**Edit your SSH config file:**
```
sudo vim ~/.ssh/config
```

**Add:**
```
Host vmachineordering-abc12-ordering-core-api
  HostName github.com
  User git
  IdentityFile ~/.ssh/vmachineordering-abc12-ordering-core-api
  IdentitiesOnly yes
```

**Set permissions:**
```
chmod 600 ~/.ssh/vmachineordering-abc12-ordering-core-api
```

---

## 4. Test SSH Connection

```
ssh -T git@vmachineordering-abc12-ordering-core-api
```

- You should see a welcome/auth message from GitHub.

---

## 5. Clone the Repo

**Use the config alias to clone:**
```
git clone git@vmachineordering-abc12-ordering-core-api:[user_or_org]/ordering-core-api.git
```

- Replace `[user_or_org]` with your GitHub username or org.

---

## 6. Common Git Commands

```
git pull
git status
git checkout <branch>
git fetch --all
```

---

## Notes

- Repeat steps for each VM or repo as needed (use unique `[random5chars]`).
- You can add more `Host` blocks in `~/.ssh/config` for multiple repos/VMs.
