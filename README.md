# TL;DR - Go

*- personal notes for the Go programming language.*

## Installation

### Linux

#### Arch Linux

1. Install build tools, Go compilers and packers:
    ```sh
    pacman -S --needed --noconfirm binutils make go tinygo upx
    ```

## Compilation

### Linux

- Compile to Linux AMD64 platform:
    ```sh
    EXE='program'
    go fmt main.go
    GOOS=linux GOARCH=amd64 tinygo build -o "${EXE}" main.go 2> /dev/null \
        || GOOS=linux GOARCH=amd64 go build -o "${EXE}" main.go
    strip -s "${EXE}"
    upx --ultra-brute "${EXE}"
    ```

### Windows

- Compile to Windows AMD64 platform:
    ```sh
    EXE='program.exe'
    go fmt main.go
    GOOS=windows GOARCH=amd64 tinygo build -o "${EXE}" main.go 2> /dev/null \
        || GOOS=windows GOARCH=386 go build -o "${EXE}" main.go
    strip -s "${EXE}"
    upx --ultra-brute "${EXE}"
    ```

## Resources

- Build tools:
    - [GNU Binutils](https://www.gnu.org/software/binutils/)
    - [GNU Make](https://www.gnu.org/software/make/)
- Go compilers:
    - [Go](https://go.dev)
    - [TinyGo](https://tinygo.org)
- Packers:
    - [UPX](https://github.com/upx/upx/)
