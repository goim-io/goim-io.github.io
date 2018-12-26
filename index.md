---
layout: default
---

## Introduction
GOIM is a IM and push notification server cluster.

## Features
 * Light weight
 * High performance
 * Pure Golang
 * Supports single push, multiple push and broadcasting
 * Supports one key to multiple subscribers (Configurable maximum subscribers count)
 * Supports heartbeats (Application heartbeats, TCP, KeepAlive, HTTP long pulling)
 * Supports authentication (Unauthenticated user can't subscribe)
 * Supports multiple protocols (WebSocket，TCP，HTTP）
 * Scalable architecture (Unlimited dynamic job and logic modules)
 * Asynchronous push notification based on Kafka

## Architecture
![arch](docs/arch.png)

## Benchmark
![benchmark](benchmarks/benchmark.jpg)

### Benchmark Server

| CPU | Memory | OS | Instance |
|:----|:-------|:---|:---------|
| Intel(R) Xeon(R) CPU E5-2630 v2 @ 2.60GHz  | DDR3 32GB | Debian GNU/Linux 8 | 1 |

### Benchmark Case
* Online: 1,000,000
* Duration: 15min
* Push Speed: 40/s (broadcast room)
* Push Message: {"test":1}
* Received calc mode: 1s per times, total 30 times

### Benchmark Resource
* CPU: 2000%~2300%
* Memory: 14GB
* GC Pause: 504ms
* Network: Incoming(450MBit/s), Outgoing(4.39GBit/s)

### Benchmark Result
* Received: 35,900,000/s
* [English](benchmarks/index.html)
* [中文](benchmarks/index_cn.html)

### Documents
* [Protocol](docs/protocol.html)
* [Push API](docs/push.html)

### Examples
* Online Example: [Online Example](examples/)
* Websocket: [Websocket Client](https://github.com/Terry-Mao/goim/tree/master/examples/javascript)
* Android: [Android Client](https://github.com/roamdy/goim-sdk)
* iOS: [iOS Client](https://github.com/roamdy/goim-oc-sdk)

## LICENSE
goim is is distributed under the terms of the MIT License.
