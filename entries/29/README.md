# Go - Generate self signed tls certs

Just found out that Go has a niffty way to create self signed certs for dev.

```
//cd into the folder to store the certs
//Run generate_cert.go from the go install location
//Can find install path from `which go`
go run /usr/local/go/src/crypto/tls/generate_cert.go --rsa-bits=2048 --host=localhost
```

This is handy to make certs on dev environment
