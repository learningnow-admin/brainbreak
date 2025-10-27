
# Brainbreak Infrastructure


## Running this site locally
git clone https://github.com/learningnow-admin/brainbreak 
mkdir themes
cd themes
git clone https://github.com/lukesmithxyz/lugo.git
hugo server --noHTTPCache


## Local Development
```bash
cd infrastructure/
vagrant up          # Creates VM and runs Ansible
vagrant ssh         # Access the VM
# Visit http://localhost:8080
vagrant destroy     # Clean up when done
```

## Production Deployment
Deploy to production server:
```bash
cd infrastructure/
./deploy prod
```

## Manual Post-Setup Tasks
### 1. Generate SSH Deploy Keys
SSH into the server as root:
```bash
ssh root@170.64.201.246
```

Create SSH keys for GitHub Actions deployment:
```bash
# Generate key pair for GitHub Actions
ssh-keygen -t ed25519 -C "github-deploy-bb" -f ~/.ssh/github_deploy_bb

# Create .ssh directory for bb user if it doesn't exist
mkdir -p /home/bb/.ssh
touch /home/bb/.ssh/authorized_keys

# Add public key to bb user's authorized_keys (since GitHub Actions will SSH as bb)
cat ~/.ssh/github_deploy_bb.pub >> /home/bb/.ssh/authorized_keys

# Ensure proper permissions
chmod 700 /home/bb/.ssh
chmod 600 /home/bb/.ssh/authorized_keys
chown -R bb:bb /home/bb/.ssh

# Display private key to copy for GitHub secrets
cat ~/.ssh/github_deploy_bb
```

### 2. Configure GitHub Secrets
Go to your brainbreak repo: Settings → Secrets and variables → Actions

1. Click "Repository secrets"
2. Click "New repository secret" 
3. Add these three secrets:

bb_ssh
- Copy the private key from: cat ~/.ssh/github_deploy_bb

bb_ssh_pass  
- Leave empty (unless you set a passphrase)

bb_port
- Enter: 22

4. Click "Add secret" for each one

### 3. Test the Setup
Your GitHub Actions workflow should now work correctly with the `bb` user that Ansible creates.