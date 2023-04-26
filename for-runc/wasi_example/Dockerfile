FROM wasmedge/slim-runtime:0.10.1
ADD wasi_example_main.wasm /
CMD ["wasmedge", "--dir", ".:/", "/wasi_example_main.wasm"]
