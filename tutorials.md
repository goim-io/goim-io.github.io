---
layout: default
---

# Tutorials

- [Quick Start](#Quick Start)
- [Environment](#Environment)
- [Configuration](#Configuration)
- [Dependencies](#Dependencies)
- [Deployments](#Deployments)
- [Documents](#Documents)
- [Examples](#Examples)

## Quick Start

### Build
```
    make build
```

### Run
```
    make run
    make stop

    // or
    nohup target/logic -conf=target/logic.toml -region=sh -zone=sh001 deploy.env=dev weight=10 2>&1 > target/logic.log &
    nohup target/comet -conf=target/comet.toml -region=sh -zone=sh001 deploy.env=dev weight=10 addrs=127.0.0.1 2>&1 > target/logic.log &
    nohup target/job -conf=target/job.toml -region=sh -zone=sh001 deploy.env=dev 2>&1 > target/logic.log &
```

## Environment

    env:
    export REGION=sh
    export ZONE=sh001
    export DEPLOY_ENV=dev

    supervisor:
    environment=REGION=sh,ZONE=sh001,DEPLOY_ENV=dev

    go flag:
    -region=sh -zone=sh001 deploy.env=dev

## Configuration
### Log(github.com/golang/glog)

    -logtostderr=false
	    Logs are written to standard error instead of to files.
    -alsologtostderr=false
	    Logs are written to standard error as well as to files.
    -stderrthreshold=ERROR
	    Log events at or above this severity are logged to standard
	    error as well as to files.
    -log_dir=""
	    Log files will be written to this directory instead of the
	    default temporary directory.

## Dependencies
[Discovery](https://github.com/Bilibili/discovery)

[Kafka](https://kafka.apache.org/quickstart)

## Deployments

### supervisor

```
    apt-get install supervisor
    mkdir -p /etc/supervisor/conf.d
    cd /etc/supervisor/conf.d
    # add supervisor config(comet.conf,logic.conf,job.conf)
    supervisorctl update
```

### comet.conf

```
[program:comet]
name = comet
command= /data/app/goim/comet -conf /data/app/goim/comet.toml
autostart = true
autorestart = true
priority = 2
startsecs = 1
startretries = 3
exitcodes = 0,2
stopsignal = QUIT
stopwaitsecs = 10
user = root
stdout_logfile = /data/log/goim/comet_stdout.log
stdout_logfile_backups = 10
stderr_logfile = /data/log/goim/comet_stderr.log
stderr_logfile_backups = 10
```
### logic.conf
```
[program:logic]
name = logic
command= /data/app/goim/logic -conf /data/app/goim/logic.toml
autostart = true
autorestart = true
priority = 1
startsecs = 1
startretries = 3
exitcodes = 0,2
stopsignal = QUIT
stopwaitsecs = 10
user = root
stdout_logfile = /data/log/goim/logic_stdout.log
stdout_logfile_backups = 10
stderr_logfile = /data/log/goim/logic_stderr.log
stderr_logfile_backups = 10
```
### job.conf
```
[program:job]
name = job
command= /data/app/goim/job -conf /data/app/goim/job.toml
autostart = true
autorestart = true
priority = 2
startsecs = 1
startretries = 3
exitcodes = 0,2
stopsignal = QUIT
stopwaitsecs = 10
user = root
stdout_logfile = /data/log/goim/job_stdout.log
stdout_logfile_backups = 10
stderr_logfile = /data/log/goim/job_stderr.log
stderr_logfile_backups = 10
```

## Documents
[Protocol](https://github.com/Terry-Mao/goim/tree/v2.0/docs/protocol.png)

[English](https://github.com/Terry-Mao/goim/tree/v2.0/README_en.md)

[中文](https://github.com/Terry-Mao/goim/tree/v2.0/README_cn.md)

## Examples
Online Demo: [Online Demo](/demo)

Websocket: [Websocket Client](https://github.com/Terry-Mao/goim/tree/master/examples/javascript)

Android: [Android Client](https://github.com/roamdy/goim-sdk)

iOS: [iOS Client](https://github.com/roamdy/goim-oc-sdk)