# Tutorial: Getting started with multi-module workspaces

https://go.dev/doc/tutorial/workspaces

## Command History

```sh
# Create a module
$ mkdir workspace
$ cd workspace
$ mkdir hello
$ cd hello
$ go mod init example.com/hello
$ go get golang.org/x/example/hello/reverse
# Write hello.go file
$ go run .

# Move to workspace directory
$ cd ..
$ go work init ./hello
$ go run ./hello
olleH

# Clone and modify `golang.org/x/example/hello`
$ git clone https://go.googlesource.com/example
$ go work use ./example/hello
$ touch example/hello/reverse/init.go
# Write init.go that reverse integer
# Modify hello/hello.go
$ go run ./hello
olleH 10642
```

## Workspace Reference

- https://go.dev/ref/mod#workspaces
