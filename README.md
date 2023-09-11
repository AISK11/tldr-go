# Go

*- personal notes for the Go programming language.*

## Installation

### Arch Linux

1. Install Go:

```console
# go version || pacman -S --needed --noconfirm go
```

### Windows

1. Install Chocolatey package manager:

```console
PS #> choco -v ; if ("${LASTEXITCODE}" -ne 0) { Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1')) }
```

2. Install Go:

```console
PS #> go version ; if ("${LASTEXITCODE}" -ne 0) { choco install -fy golang }
```
