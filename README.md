# Rust grpc demo
## prequire 
```bah
cargo update
cargo build //for generate the grpc rust code 
```
## how to run 
```bash
cd src/bin

cargo run --bin server

cargo run --bin client

```

## run with docker

- first build with local rust compiler
- with docker-compose build
```bash
docker-compose build
docker-compose up -d
```