## Get one user

```shell
$ curl 'https://ci.example.com/go/api/users/jdoe' \
      -u 'username:password' \
      -H 'Accept: application/vnd.go.cd.v1+json'
```

> The above command returns JSON structured like this:

```http
HTTP/1.1 200 OK
Content-Type: application/vnd.go.cd.v1+json; charset=utf-8
```

```json
{
  "_links": {
    "doc": {
      "href": "http://api.go.cd/#users"
    },
    "self": {
      "href": "https://ci.example.com/go/api/users/jdoe"
    },
    "find": {
      "href": "https://ci.example.com/go/api/users/:login_name"
    }
  },
  "login_name": "jdoe",
  "display_name": "jdoe",
  "enabled": true,
  "email": null,
  "email_me": false,
  "checkin_aliases": [

  ]
}
```

Gets a user by its login name

### HTTP Request

`GET /go/api/user/:login_name`

### Returns

A [user object](#the-user-object).
