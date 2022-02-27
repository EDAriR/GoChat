# GoChat
Learn build JWT with go 

ref : https://www.bacancytechnology.com/blog/golang-jwt


```shell
go get github.com/gorilla/mux
go get github.com/jinzhu/gorm
go get github.com/lib/pq
go get golang.org/x/crypto/bcrypt


go get github.com/dgrijalva/jwt-go
```

## GRPC

ref : https://pjchender.dev/golang/grpc-golang/

#### Install 
```Shell
go get -u google.golang.org/grpc
go get -u github.com/golang/protobuf/{proto,protoc-gen-go}
go get -u google.golang.org/grpc
```
##### Gen *.go
```Shell
# 進入到 proto 檔案的資料夾中，輸入
protoc *.proto  --go_out=plugins=grpc:. --go_opt=paths=source_relative
```