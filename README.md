# openssl-boost-asio-test

Tested on macOS. 

## 1. Fetch Boost libraries: 

```bash=
buckaroo install 
```

## 2. Fetch OpenSSL submodule: 

```bash=
git pull --recurse-submodules
```

## 3. Re-point `.buckconfig` to external OpenSSL. 

Change `.buckconfig` like so: 

```ini=
  ; ...
  ; openssl.openssl = buckaroo/official/openssl/openssl
  openssl.openssl = external/openssl
```

Change `buckaroo/official/boost/asio/.buckconfig` like so: 

```ini=
  ; ...
  ; openssl.openssl = ../../openssl/openssl
  openssl.openssl = ../../../../external/openssl
```

## 4. Run the server example: 

```bash=
buck run //server:server#macosx-x86_64 0.0.0.0 3000 `pwd`
# Visit http://localhost:3000/README.md
```
