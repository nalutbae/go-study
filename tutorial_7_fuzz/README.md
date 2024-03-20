# Tutorial: Getting started with fuzzing

https://go.dev/doc/tutorial/fuzz

## Command History

```sh
# Create a module
$ mkdir fuzz
$ cd fuzz
$ go mod init example.com/fuzz

# Write main.go

# Run
$ go run .
original: "The quick brown fox jumped over the lazy dog"
reversed: "god yzal eht revo depmuj xof nworb kciuq ehT"
reversed again: "The quick brown fox jumped over the lazy dog"

# Write reverse_test.go

# Run test
$ go test
ok      example.com/fuzz        0.325s

$ go test -fuzz=Fuzz
fuzz: elapsed: 0s, gathering baseline coverage: 0/3 completed
fuzz: elapsed: 0s, gathering baseline coverage: 3/3 completed, now fuzzing with 12 workers
fuzz: minimizing 30-byte failing input file
fuzz: elapsed: 0s, minimizing
--- FAIL: FuzzReverse (0.04s)
    --- FAIL: FuzzReverse (0.00s)
        reverse_test.go:36: Reverse produced invalid UTF-8 string "\x80\xd1"

    Failing input written to testdata/fuzz/FuzzReverse/609d20aa1bccfb3e
    To re-run:
    go test -run=FuzzReverse/609d20aa1bccfb3e
FAIL
exit status 1
FAIL    example.com/fuzz        0.313s

$ go test
--- FAIL: FuzzReverse (0.00s)
    --- FAIL: FuzzReverse/609d20aa1bccfb3e (0.00s)
        reverse_test.go:36: Reverse produced invalid UTF-8 string "\x80\xd1"
FAIL
exit status 1
FAIL    example.com/fuzz        0.172s

# Debug and modify..

$ go test -fuzz=Fuzz
fuzz: elapsed: 0s, gathering baseline coverage: 0/15 completed
fuzz: elapsed: 0s, gathering baseline coverage: 15/15 completed, now fuzzing with 12 workers
fuzz: elapsed: 3s, execs: 628279 (209360/sec), new interesting: 25 (total: 40)
fuzz: elapsed: 6s, execs: 653961 (8561/sec), new interesting: 27 (total: 42)
fuzz: elapsed: 9s, execs: 653961 (0/sec), new interesting: 27 (total: 42)
fuzz: elapsed: 12s, execs: 653961 (0/sec), new interesting: 27 (total: 42)
fuzz: elapsed: 15s, execs: 653961 (0/sec), new interesting: 27 (total: 42)
fuzz: elapsed: 18s, execs: 653961 (0/sec), new interesting: 27 (total: 42)
fuzz: elapsed: 21s, execs: 2736898 (694326/sec), new interesting: 30 (total: 45)
fuzz: elapsed: 24s, execs: 6567900 (1277347/sec), new interesting: 33 (total: 48)
fuzz: elapsed: 27s, execs: 8552870 (661665/sec), new interesting: 38 (total: 53)
fuzz: elapsed: 30s, execs: 10005747 (484293/sec), new interesting: 40 (total: 55)
fuzz: elapsed: 33s, execs: 11451304 (481864/sec), new interesting: 40 (total: 55)
fuzz: elapsed: 36s, execs: 12918985 (489153/sec), new interesting: 41 (total: 56)
^Cfuzz: elapsed: 37s, execs: 13383065 (487914/sec), new interesting: 41 (total: 56)
PASS
ok      example.com/fuzz        37.222s

```

## vscode debugging

https://github.com/golang/vscode-go/blob/master/docs/debugging.md
