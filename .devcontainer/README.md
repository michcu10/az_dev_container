# Azure Development Container

This dev container includes everything you need for Azure development:

## Included Tools
- **Azure CLI** (with Bicep)
- **Azure PowerShell** (Az module)
- **Terraform** (with tflint)
- **Python 3.12** (with pip, venv)
- **Git** & GitHub CLI
- **PowerShell** (set as default terminal)

## VS Code Extensions
- Azure CLI Tools
- Azure Terraform
- Python
- PowerShell
- Terraform

## Usage

### First Time Setup
1. Open this folder in VS Code
2. Click "Reopen in Container" when prompted
   - Or: `Ctrl+Shift+P` → "Dev Containers: Reopen in Container"
3. Wait for container to build (~5 minutes first time)
4. Tools are ready to use!

### Verify Installation
```bash
# Check Azure CLI
az version

# Check Azure PowerShell
pwsh -Command "Get-Module -ListAvailable Az"

# Check Terraform
terraform version

# Check Python
python --version
```

### Azure Login
```bash
# CLI
az login

# PowerShell
pwsh -Command "Connect-AzAccount"
```

## Reusing This Container

To use this configuration in other projects:

1. Copy the `.devcontainer` folder to your new project
2. Open the project in VS Code
3. Reopen in container

All tools and settings will be available instantly!

## Credential Persistence (host `.azure` mount)

This dev container is configured to mount your host Azure credentials directory into the container so your interactive login persists across container rebuilds.

- **Host path mounted:** `~/.azure` on Windows this resolves to `%USERPROFILE%\\.azure` and is bound to `/home/vscode/.azure` inside the container.
- **How to use:**
   - Run `az login` (opens browser) or `az login --use-device-code` to authenticate.
   - For PowerShell run `pwsh -Command "Connect-AzAccount"`.
- **Persistence:** Your login state is stored on your host and will remain available after rebuilding the container because the host folder is mounted.
- **Security note:** Mounting your `.azure` folder grants the container access to your Azure credentials and tokens. Only use this on trusted machines and do not check the mounted host files into source control.

If you prefer not to mount your host credentials, remove the `mounts` entry from `devcontainer.json` and authenticate inside the container each session.
