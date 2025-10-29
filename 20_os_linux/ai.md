```
 █████╗ ██╗
██╔══██╗██║
███████║██║
██╔══██║██║
██║  ██║██║
╚═╝  ╚═╝╚═╝
```

## 📦 Node Version Manager (NVM) Installation

[NVM](https://github.com/nvm-sh/nvm) is a version manager for Node.js, designed to be installed per-user and invoked per-shell.

### 1. Install NVM

Run the official installer script. It is recommended to check the [official NVM GitHub page](https://github.com/nvm-sh/nvm) for the latest version of the install script.

```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/master/install.sh | bash
```

This script clones the NVM repository to `~/.nvm` and adds the source line to the profile (`~/.zshrc`).

### 2. Activate NVM

The installation script should automatically add the necessary lines to the `.zshrc` file. To apply the changes, restart the shell or run:

```
source ~/.zshrc
```

### 3. Verify Installation

To verify that NVM has been installed correctly, run:

```
nvm --version
```

### 4. Install Node.js

Install the latest LTS version of Node.js:

```
nvm install --lts
```

A specific version can also be installed:

```
nvm install 20.10.0
```

### 5. Set a Default Node Version

To set a default Node.js version to be used in any new shell, run:

```
nvm alias default lts/*
```
