# madobe

madobe（窓辺） is dotfiles for windows.  

## Before Setup

### enable running `.ps1` scripts

```pwsh
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser -Force
```

- Gitでクローンしたファイルはローカルスクリプトとして認識されるので、RemoteSignedで実行可能

### Install depends

```pwsh
.\path\to\madobe\scripts\depends.ps1
```

### SSH setting of GitHub

```sh
mkdir -p ~/.ssh/keys/github
ssh-keygen -t ed25519 -f ~/.ssh/keys/github/id_ed25519
cat ~/.ssh/keys/github/id_ed25519.pub
# paste pub-key to GitHub -> Settings -> SSH and GPG keys -> SSH keys
```

### Clone this repo

```pwsh
cd $HOME
git clone git@github.com:guricerin/madobe.git
```

## Setup

### dry-run

```pwsh
.\path\to\madobe\setup.ps1
```

### apply

- enable developer mode (`System` -> `For developers` -> `Developer Mode` toggle on)

```pwsh
.\path\to\madobe\setup.ps1 -apply
```

## After Setup

### Install tools

```pwsh
.\path\to\madobe\scripts\tools.ps1
```

### disable running `.ps1` scripts (except `$profile`)

```pwsh
Set-ExecutionPolicy Restricted -Scope CurrentUser -Force
```

## References

- [PowerShell実践ガイドブック クロスプラットフォーム対応の次世代シェルを徹底解説](https://book.mynavi.jp/ec/products/detail/id=90597)
