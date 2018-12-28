---
layout: default
---

## Protocol

| Name             |      Length         | Remork |
|------------------|:-------------------:|--------|
| Package Length   | 4 bytes             | header + body length   |
| Header Length    | 2 bytes             | protocol header length |
| Protocol Version | 2 bytes             | protocol version       |
| Operation        | 4 bytes             | operation for request  |
| Sequence id      | 4 bytes             | sequence number chosen by client |
| Body             | PackLen + HeaderLen | binary body bytes |

## Operation

| Name             | Remork |
|:-----------------|:-------|
| OpHandshake = 0 | handshake |
| OpHandshakeReply = 1 | handshake reply |
| OpHeartbeat = 2 | heartbeat |
| OpHeartbeatReply = 3 | heartbeat reply |
| OpSendMsg = 4 | send message |
| OpSendMsgReply = 5 | send message reply |
| OpDisconnectReply = 6 | connection disconnect reply |
| OpAuth = 7 | auth connnect |
| OpAuthReply = 8 | auth connect reply |
| OpRawBatch = 9 | batch message for websocket |

