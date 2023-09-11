# TL;DR - Go

*- personal notes for the Go programming language.*

## Installation

### Linux

#### Arch Linux

1. Install [Go](https://go.dev/dl/) programming language compiler:

    - [Go compiler](https://archlinux.org/packages/extra/x86_64/go/):

    ```sh
    go version || pacman -S --needed --noconfirm go
    ```

    - [TinyGo compiler](https://archlinux.org/packages/extra/x86_64/tinygo/):

    ```sh
    tinygo version || pacman -S --needed --noconfirm tinygo
    ```
