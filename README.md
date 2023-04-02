# Go WebAssembly Example

Here you will find a simple Go WebAssembly Example. Showing you how to use Go to compile a `.wasm` file and run Go functions in the browser. Do you want more detail [read my Blog here](https://tiborhercz.com/golang-webassembly/)

In this example a SHA512 hash is created with WebAssembly using the value from the input field found in the HTML.

## How to run it

Compile the `.wasm` file

```shell
GOOS=js GOARCH=wasm go build -o static/main.wasm cmd/wasm/main.go
```

Copy the supporting JavaScript file

```shell
cp "$(go env GOROOT)/misc/wasm/wasm_exec.js" ./static
```

Start the webserver

```shell
go run ./cmd/webserver/main.go
```

Navigate to: [http://localhost:3000/index.html](http://localhost:3000/index.html)

Here you will find an input field, which hashes the text with a SHA512 hash using the Go WebAssembly code. Found in `cmd/wasm/main.go`
