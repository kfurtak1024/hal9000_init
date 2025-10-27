```
██████╗ ███████╗██╗   ██╗███████╗██╗      ██████╗ ██████╗ 
██╔══██╗██╔════╝██║   ██║██╔════╝██║     ██╔═══██╗██╔══██╗
██║  ██║█████╗  ██║   ██║█████╗  ██║     ██║   ██║██████╔╝
██║  ██║██╔══╝  ╚██╗ ██╔╝██╔══╝  ██║     ██║   ██║██╔═══╝ 
██████╔╝███████╗ ╚████╔╝ ███████╗███████╗╚██████╔╝██║     
╚═════╝ ╚══════╝  ╚═══╝  ╚══════╝╚══════╝ ╚═════╝ ╚═╝     
```

## 🐍 Python Development Setup

The goal of this setup is to keep the **system Python** completely untouched.  
Treat it as if it doesn’t exist — no interaction, no modification.

To achieve full isolation and manage multiple Python versions efficiently, I use **pyenv**.  
`pyenv` provides isolated Python installations, and on top of that, I use **pipenv** to manage project-specific environments.

The overall structure looks like this:

- **System Python** → ignored
- **pyenv** → manages isolated Python versions  
- **pipenv / venv** → manages per-project environments

> [!Note]
> For some lightweight projects, I might use `python -m venv` instead of `pipenv`.  
> In that case, the environment still uses the **Python interpreter installed via pyenv**.

### 1 Install pyenv

First, install required build dependencies:

```
sudo apt install libssl-dev libbz2-dev libreadline-dev libsqlite3-dev \
libncursesw5-dev tk-dev libxmlsec1-dev liblzma-dev
```

Then, install pyenv:
```
curl -fsSL https://pyenv.run | bash
```

### 2. Shell Integration (ZSH)

Add the following lines to `~/.zshrc` to enable **pyenv**:
```
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.zshrc
echo '[[ -d $PYENV_ROOT/bin ]] && export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.zshrc
echo 'eval "$(pyenv init - zsh)"' >> ~/.zshrc
```
Restart your shell to apply the changes:
```
exec "$SHELL"
```

### 3. Verify Installation

Check that pyenv is installed correctly:
```
pyenv --version
```
List available Python versions:
```
pyenv install --list
```
Install a specific version (for example, Python 3.13.0):
```
pyenv install 3.13.0
```
Set it as the global default:
```
pyenv global 3.13.0
```

Once **pyenv** is ready, install minimal global tools (like **pipenv**) and then create isolated virtual environments per project without ever touching the system Python.
