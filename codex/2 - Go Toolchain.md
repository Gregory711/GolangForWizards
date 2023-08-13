# 2 - Go Toolchain

## Installing Go Toolchain

Later the same day I discovered the Golang for Wizards tome I began studying its first chapter titled Go Toolchain. It described a series of runes that must be inscribed on my staff to helper master the language including the standard spell compiler gc.

The tome said the toolchain runes must download their source energy from the realm https://go.dev/doc/install. Upon downloading and installing the magic from this realm I needed to configure my staff commands to use it. Since my staff was crafted using wood from a Macintosh tree and thus was running zsh commands I edited its ~/.zshrc file. Linux staffs would have to be configured using bashrc or profile files. In this configuration file I added to its PATH variable /usr/local/go/bin/ (if you don't have a PATH variable yet then add that after export PATH=${PATH}: otherwise just add a : to your existing one followed by it). Next I cast source ~/.zshrc. Finally, I was able to test my staff with this new magic my casting go version!

## Simplest Go Program

Thrilled by my successful installation of the Go language I set about to compile the simplest Go spell (found in spells/2-Toolchain/simple.go). Here is the incantation:
```go
package main

func main() {
}
```
package and func are both key runes while main is just an identifier. func main is the entry point of the spell.

## Running Go Programs

Now that I had prepared a spell I was eager to cast it. I brandished my staff and said the magic command:
```bash
go run simple.go
```
The gemstone embedded in my staff grew briefly as the magic flowed through it but not red which would indicate an error. I had done it. I had cast my first Go spell!

Golang for Wizards described other ways for casting spells including the following when there are multiple spell files:
```bash
go run .
```
but it cautioned against using it for larger spells instead recommending to use one of the following commands to build binary executables which can be run:
```bash
go build
go install
```

## Module Dependency Management

Now that I knew how to compile and cast Go spells I needed to know how to manage dependencies so I could build upon existing spells. This is done using Go modules which are specified in each projects go.mod file in its root directory. The go.mod file is created using the following command:
```bash
go mod init github.com/Gregory711/repo
```
where the github.com/Gregory711 is just a unique personal (or oganization) identifier (I used my github username) and repo is the name for the repository.

The command
```bash
go mod tidy
```
helpfully analyzes your source code and adds missing dependencies and removes unused ones.

## Other Useful Toolchain Commands

There are a few other useful commands in the toolchain. The first of which is
```bash
go vet
```
which checks for and reports code warnings including possible logic mistakes.

The next one is
```bash
go fmt
```
which nicely and consistently formats your code.

Finally,
```bash
go test
```
is used to run tests and benchmarks.