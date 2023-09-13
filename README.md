# TL;DR - Go

*- personal notes for the Go programming language.*

## Installation

### Linux

#### Arch Linux

1. Install build tools, Go compilers and packers:
    ```sh
    paru -S --needed --noconfirm binutils go tinygo go-garble upx
    ```

## Usage

1. Beautify source code:
    ```sh
    go fmt main.go
    ```
2. Set program name and platform target:
    - Windows (amd64):
        ```sh
        export EXE='program.exe'
        export GOOS='windows'
        export GOARCH='amd64'
        ```
3. Compile executable:
    - Go compiler (best compatibility):
        ```sh
        go build -ldflags='-w -s' -o "${EXE}" main.go
        ```
    - TinyGo compiler (small size):
        ```sh
        tinygo build -no-debug -o "${EXE}" main.go
        ```
    - Garble compiler (code obfuscation):
        ```sh
        garble -literals -seed=random -tiny build -o "${EXE}" main.go
        ```
3. Strip symbols:
    ```sh
    strip -s "${EXE}"
    ```
4. Pack executable and corrupt the packer:
    ```sh
    upx --ultra-brute "${EXE}"
    RAND="$(tr -dc ' _0-9a-zA-Z' < /dev/urandom | head -c 4)" \
        ; sed -i "s/UPX[\!0-9]/${RAND}/g" "${EXE}"
    RAND="$(tr -dc ' _0-9a-zA-Z' < /dev/urandom | head -c "$(strings "${EXE}" \
        | grep '\$Info: .*http.*\$' | tr -d '\n' | wc -c)")" \
        ; sed -i "s/\$Info: .*http.*\$/${RAND}/g" "${EXE}"
    RAND="$(tr -dc ' _0-9a-zA-Z' < /dev/urandom | head -c "$(strings "${EXE}" \
        | grep '\$Id: .*All Rights Reserved.*\$' | tr -d '\n' | wc -c)")" \
        ; sed -i "s/\$Id: .*All Rights Reserved.*\$/${RAND}/g" "${EXE}"
    ```

## Resources

- Build tools:
    - [GNU Binutils](https://www.gnu.org/software/binutils/)
- Go compilers:
    - [Go](https://go.dev)
    - [TinyGo](https://tinygo.org)
    - [Garble](https://github.com/burrowers/garble)
- Packers:
    - [UPX](https://github.com/upx/upx/)
