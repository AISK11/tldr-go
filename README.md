# Go

*- personal notes for the Go programming language.*

## Installation

### Linux

#### Arch Linux

1. Install [Go](https://go.dev/dl/):

```sh
go version || pacman -S --needed --noconfirm go
```

### Windows

#### Windows 11

1. Install [Chocolatey](https://chocolatey.org/install) package manager:

```powershell
choco -v ; if ("${LASTEXITCODE}" -ne 0) { Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1')) }
```

2. Install [Go](https://go.dev/dl/):

```powershell
go version ; if ("${LASTEXITCODE}" -ne 0) { choco install -fy golang }
```
