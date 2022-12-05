# WASM Program Images

## Usage

### hello

```bash
# Create a "WASM in KinD" Cluster
$ kind create cluster --image ghcr.io/liquid-reply/kind-crun-wasm:v1.23.4

# Run the example
$ kubectl run -it --rm --restart=Never wasm-hello --image=leviyanx/wasm-hello-example:v1.0 --annotations="module.wasm.image/variant=compat" /hello.wasm 20000

hello
20000
pod "wasm-hello" deleted
```

### wasi

...

### for-runc

This image can be run with runc.

#### Prerequisite

Install [containerd](https://github.com/containerd/containerd) and its command line tool.

```bash
$ sudo ctr images pull docker.io/leviyanx/runc-wasm-example:v1.3

$ sudo ctr run --rm docker.io/leviyanx/runc-wasm-example:v1.3 runc-wasm-example
Random number: -1047867197
Random bytes: [62, 63, 20, 112, 88, 181, 238, 121, 157, 191, 142, 94, 20, 209, 125, 223, 155, 234, 77, 240, 87, 4, 119, 70, 102, 1, 153, 123, 154, 19, 144, 109, 65, 72, 252, 123, 209, 161, 228, 186, 165, 35, 35, 216, 194, 228, 255, 193, 205, 231, 211, 186, 124, 169, 174, 161, 59, 190, 198, 33, 121, 166, 25, 229, 232, 42, 140, 37, 243, 191, 4, 25, 86, 222, 37, 133, 35, 137, 37, 137, 29, 139, 188, 38, 134, 96, 250, 158, 2, 145, 220, 94, 119, 184, 162, 118, 40, 177, 48, 22, 156, 141, 115, 222, 143, 243, 124, 181, 58, 217, 215, 35, 221, 237, 160, 128, 196, 119, 133, 133, 227, 6, 145, 16, 28, 123, 101, 62]
Printed from wasi: This is from a main function
This is from a main function
The env vars are as follows.
The args are as follows.
wasi_example_main.wasm
File content is This is in a file
```

## Reference

1. https://github.com/Liquid-Reply/kind-crun-wasm
2. https://github.com/second-state/wasm-learning/tree/master/cli/wasi
3. [Use the slim Linux container](https://github.com/WasmEdge/WasmEdge/blob/2fbea38d0cbe7b7c29867a8a1bed7e9723e00a46/docs/book/en/src/use_cases/kubernetes/docker/lxc.md)