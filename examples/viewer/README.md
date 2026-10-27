# Web viewer example

Build the web application from the repository root:

```sh
rustup target add wasm32-unknown-unknown
cargo install trunk --locked
(cd apps/wordcraft-web && trunk build --release)
python3 -m http.server 8765 --bind 127.0.0.1
```

Open http://127.0.0.1:8765/examples/viewer/ and choose a DOCX. The page uses the same-origin `?host=parent&view-only` bridge, and the download button returns the original selected file. It requires a browser with WebGPU or WebGL2. The view-only setting is an interface restriction, not an authorization mechanism. The build uses the full web application.
