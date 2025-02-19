# **Distributed and Decentralised Systems** Course Project
[![Go Report Card](https://goreportcard.com/badge/github.com/dds-project-f19/dds-backend)](https://goreportcard.com/report/github.com/dds-project-f19/dds-backend)
[![MIT](https://img.shields.io/github/license/dds-project-f19/dds-backend)](https://raw.githubusercontent.com/dds-project-f19/dds-backend/master/LICENSE)
![SIZE](https://img.shields.io/github/repo-size/dds-project-f19/dds-backend)

### Build and Run:

1 Configure database link (mysql) /config/config.yaml:

2 Get dependencies

```shell script
go get -u github.com/go-sql-driver/mysql
go get -u github.com/jinzhu/gorm
go get -u github.com/gin-gonic/gin
go get -u github.com/gin-contrib/cors

```
3 Get server

INSIDE $GOPATH/src
```shell script
git clone github.com/dds-project-f19/dds-backend
```

4 Build

```shell script
go install your/go/path/src/dds-backend
```

5 Run

now you can launch with executable located at `$GOPATH/bin/` called `dds-backend` (.exe for Windows)


### API Descri~~~~ption (to be moved to wiki later):
TODO:
* Add auth tokens
* Decide on auth model



#### Ping
> GET /ping

Expected:
```
PONG
```

#### Register User
> POST /users/register

Request:
```json
{
	"username": "username",
	"name": "name",
    "surname": "surname",
    "phone": "phone",
    "address": "address",
	"password": "password"
}
```
Expected:
```
{
    "message": "User created successfully",
    "status": "success"
}
```

#### User Login
> POST /users/login

Request:
```json
{
  "username": "username",
  "password": "password"
}
```

Expected:
```json
{
    "status": "success"
}
```

#### Get Users list
> POST /users/list

Request:
```json
{
  "username": "admin",
  "password": "admin"
}
```

Expected:
```json
{
    "data": [
        {
            "id": 1,
            "created_at": "2019-09-24T20:49:00+03:00",
            "updated_at": "2019-09-24T20:49:00+03:00",
            "username": "myusername",
            "name": "myname"
        },
        {
            "id": 2,
            "created_at": "2019-09-24T20:55:01+03:00",
            "updated_at": "2019-09-24T20:56:35+03:00",
            "username": "myusername2",
            "name": "myname2"
        }
    ],
    "status": "success"
}
```
