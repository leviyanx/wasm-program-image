FROM wasmedge/slim-runtime:0.10.1
ADD wasi-demo-app.wasm / 
CMD ["wasmedge", "--dir", ".:/", "/wasi-demo-app.wasm"]
