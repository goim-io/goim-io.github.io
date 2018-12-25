---
layout: default
---

| Name             |      Length         | Remork |
|------------------|:-------------------:|--------|
| Package Length   | 4 bytes             | header + body length   |
| Header Length    | 2 bytes             | protocol header length |
| Protocol Version | 2 bytes             | protocol version       |
| Operation        | 4 bytes             | operation for request  |
| Sequence id      | 4 bytes             | sequence number chosen by client |
| Body             | PackLen + HeaderLen | binary body bytes(json.RawMessage is []byte) |
