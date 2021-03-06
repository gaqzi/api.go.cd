## List all modifications

```shell
$ curl 'https://ci.example.com/go/api/config/revisions' \
      -u 'username:password' 
```

> The above command returns JSON structured like this:

```http
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8
```

```json
[
  {
    "md5": "893d30ab646489d882f2350b10f47d0e",
    "commitSHA": "d2f9091145e2e4b3b22d938c4819610467ae20c1",
    "username": "admin",
    "goEdition": "OpenSource",
    "time": 1436253610465,
    "schemaVersion": 75,
    "goVersion": "N/A"
  },
  {
    "md5": "a2285d3304a51508c88e5479e327553c",
    "commitSHA": "f27b48594645c9f15f55bb56d0100dd60e4cbacc",
    "username": "admin",
    "goEdition": "OpenSource",
    "time": 1436253595701,
    "schemaVersion": 75,
    "goVersion": "N/A"
  }
 ]
```

Lists the config repository modifications.

### HTTP Request

`GET /go/api/config/revisions`

### Returns

An array of repository modifications.
