# Tutorial: Developing a RESTful API with Go and Gin

https://go.dev/doc/tutorial/web-service-gin

## Command History

```sh
# Create a module
$ mkdir web-service-gin
$ cd web-service-gin
$ go mod init example.com/web-service-gin

# Write code

# Get dependencies
$ go get .
go: downloading github.com/gin-gonic/gin v1.9.1
go: downloading github.com/gin-contrib/sse v0.1.0
go: downloading github.com/mattn/go-isatty v0.0.19
go: downloading golang.org/x/net v0.10.0
go: downloading github.com/go-playground/validator/v10 v10.14.0
go: downloading github.com/pelletier/go-toml/v2 v2.0.8
go: downloading github.com/bytedance/sonic v1.9.1
go: downloading github.com/ugorji/go/codec v1.2.11
go: downloading github.com/goccy/go-json v0.10.2
go: downloading github.com/json-iterator/go v1.1.12
go: downloading google.golang.org/protobuf v1.30.0
go: downloading gopkg.in/yaml.v3 v3.0.1
go: downloading github.com/modern-go/concurrent v0.0.0-20180306012644-bacd9c7ef1dd
go: downloading golang.org/x/sys v0.8.0
go: downloading github.com/modern-go/reflect2 v1.0.2
go: downloading github.com/go-playground/universal-translator v0.18.1
go: downloading github.com/leodido/go-urn v1.2.4
go: downloading golang.org/x/text v0.9.0
go: downloading github.com/gabriel-vasile/mimetype v1.4.2
go: downloading golang.org/x/crypto v0.9.0
go: downloading github.com/chenzhuoyu/base64x v0.0.0-20221115062448-fe3a3abad311
go: downloading golang.org/x/arch v0.3.0
go: downloading github.com/twitchyliquid64/golang-asm v0.15.1
go: downloading github.com/klauspost/cpuid/v2 v2.2.4
go: downloading github.com/go-playground/locales v0.14.1
go: added github.com/bytedance/sonic v1.9.1
go: added github.com/chenzhuoyu/base64x v0.0.0-20221115062448-fe3a3abad311
go: added github.com/gabriel-vasile/mimetype v1.4.2
go: added github.com/gin-contrib/sse v0.1.0
go: added github.com/gin-gonic/gin v1.9.1
go: added github.com/go-playground/locales v0.14.1
go: added github.com/go-playground/universal-translator v0.18.1
go: added github.com/go-playground/validator/v10 v10.14.0
go: added github.com/goccy/go-json v0.10.2
go: added github.com/json-iterator/go v1.1.12
go: added github.com/klauspost/cpuid/v2 v2.2.4
go: added github.com/leodido/go-urn v1.2.4
go: added github.com/mattn/go-isatty v0.0.19
go: added github.com/modern-go/concurrent v0.0.0-20180306012644-bacd9c7ef1dd
go: added github.com/modern-go/reflect2 v1.0.2
go: added github.com/pelletier/go-toml/v2 v2.0.8
go: added github.com/twitchyliquid64/golang-asm v0.15.1
go: added github.com/ugorji/go/codec v1.2.11
go: added golang.org/x/arch v0.3.0
go: added golang.org/x/crypto v0.9.0
go: added golang.org/x/net v0.10.0
go: added golang.org/x/sys v0.8.0
go: added golang.org/x/text v0.9.0
go: added google.golang.org/protobuf v1.30.0
go: added gopkg.in/yaml.v3 v3.0.1

# Run
$ go run .
```

## REST API

```sh
# GET albums
$ curl http://localhost:8080/albums \
    --header "Content-Type: application/json" \
    --request "GET"

# GET album by id
$ curl http://localhost:8080/albums/1

# POST add album
$ curl http://localhost:8080/albums \
    --include \
    --header "Content-Type: application/json" \
    --request "POST" \
    --data '{"id": "4","title": "The Modern Sound of Betty Carter","artist": "Betty Carter","price": 49.99}'
```
