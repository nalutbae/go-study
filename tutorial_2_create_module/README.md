# Tutorial: Create a Go module

https://go.dev/doc/tutorial/create-module

## Command History

```sh
$ mkdir greetings
$ cd greetings
$ go mod init example.com/greetings
$ cd ..
$ mkdir hello
$ cd hello
$ go mod init example.com/hello
$ go mod edit -replace example.com/greetings=../greetings
$ go mod tidy
$ go run hello.go
```

## Test

```sh
$ cd greetings
$ go test
$ go test -v
```
