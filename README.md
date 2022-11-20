## Usage

### wasm-hello

```bash
# Create a "WASM in KinD" Cluster
kind create cluster --image ghcr.io/liquid-reply/kind-crun-wasm:v1.23.4

# Run the example
kubectl run -it --rm --restart=Never wasm-hello --image=leviyanx/wasm-hello-example:v1.0 --annotations="module.wasm.image/variant=compat" /hello.wasm 20000

hello
20000
pod "wasm-hello" deleted
```

## Reference

1. https://github.com/Liquid-Reply/kind-crun-wasm