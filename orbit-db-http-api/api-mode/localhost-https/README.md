### This demonstration requires SSL/TLS localhost using [mkcert](https://github.com/FiloSottile/mkcert#installation)(development purposes only) 
   
1. Install mkcert [pre-built binaries](https://github.com/FiloSottile/mkcert/releases) or commands:
```shell
brew install mkcert
brew install nss    # If using Firefox
```
   
2. Run `mkcert` in the `/certs` directory:
```shell
cd $PWD/../../certs/
mkcert localhost "*.localhost" localhost 127.0.0.1 ::1
```
**example output:**  
```console
Note: the local CA is not installed in the system trust store.
Run "mkcert -install" for certificates to be trusted automatically â ī¸
   
Created a new certificate valid for the following names đ
 - "localhost"
 - "*.localhost"
   Warning: many browsers don't support second-level wildcards like "*.localhost" â ī¸
 - "localhost"
 - "127.0.0.1"
 - "::1"

Reminder: X.509 wildcards only go one level deep, so this won't match a.b.localhost âšī¸

The certificate is at "./localhost+4.pem" and the key at "./localhost+4-key.pem" â

It will expire on 5 November 2023 đ
```
   
3. Run the container
```shell
cd $PWD/../orbit-db-http-api/localhost-https/
docker-compose up -d
```


