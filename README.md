# Azure Dev Container (Reusable Template)

Small, reusable VS Code Dev Container configured for Azure development.

Quick start
1. Open this folder in VS Code.
2. Choose "Reopen in Container" or run `Dev Containers: Reopen in Container`.

Included tools
- Azure CLI (with Bicep)
- Azure PowerShell (Az module)
- Terraform (with tflint)
- Python 3.12
- Git & GitHub CLI

Reusing this template
- Copy the `.devcontainer` folder into any new project.
- Or make this repository a GitHub Template for one-click project creation.

Credentials and security
- This template mounts your host `%USERPROFILE%\\.azure` into the container to persist Azure logins across rebuilds.
- Do not commit your host `.azure` folder; it's included in `.gitignore`.

Questions or changes
- If you want additional tools (Node, .NET SDK, Docker-in-Docker, etc.), tell me and I will add them.
