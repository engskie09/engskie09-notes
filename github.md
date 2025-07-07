# GitHub SSH Setup #

## 1. SSH Key Generation & Naming Convention ##

- **[vm_name]**: Name of your VM, e.g. `VMachineOrdering`
- **[random5chars]**: 5 random chars, e.g. `ABC12`
- **[repo_name]**: GitHub repo name, e.g. `ordering-core-api`
- **Example:** `VMachineOrdering-ABC12-ordering-core-api`

**Generate SSH key:**
```
ssh-keygen -t ed25519 -C "[vm_name]-[random5chars]-[repo_name]" -f ~/.ssh/[vm_name]-[random5chars]-[repo_name]
```
