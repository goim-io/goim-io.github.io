---
layout: default
---

## goim push API

### error code
```
// ok
OK = 0

// request error
RequestErr = -400

// server error
ServerErr = -500
```

### push keys
[POST] /goim/push/keys

| Name            | Type     | Remork                 |
|:----------------|:--------:|:-----------------------|
| [url]:operation | int32    | operation for response |
| [url]:keys      | []string | multiple client keys   |
| [Body]          | []byte   | http request body      |

response:
```
{
    "code": 0
}
```

### push mids
[POST] /goim/push/mids

| Name            | Type     | Remork                 |
|:----------------|:--------:|:-----------------------|
| [url]:operation | int32    | operation for response |
| [url]:mids      | []int64  | multiple user mids     |
| [Body]          | []byte   | http request body      |

response:
```
{
    "code": 0
}
```

### push room
/goim/push/room

| Name            | Type     | Remork                 |
|:----------------|:--------:|:-----------------------|
| [url]:operation | int32    | operation for response |
| [url]:room      | string   | room id                |
| [Body]          | []byte   | http request body      |

response:
```
{
    "code": 0
}
```

### push all
/goim/push/all

| Name            | Type     | Remork                 |
|:----------------|:-------:|:-----------------------|
| [url]:operation | int32    | operation for response |
| [url]:spee      | int32    | push speed             |
| [Body]          | []byte   | http request body      |

response:
```
{
    "code": 0
}
```

### online top
/goim/online/top

### online room
/goim/online/room

### online total
/goim/online/total

### nodes weighted
/goim/nodes/weighted

### nodes instances
/nodes/instances
