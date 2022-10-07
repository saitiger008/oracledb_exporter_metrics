# oracledb_exporter_metrics
default-metrics.toml for oracledb_exporter

公司的大佬级DBA做了个Grafana的监控图，拿出来分享给大家，这是给oracledb_exporter用的default-metrics.toml，使用方法参见：
https://github.com/iamseth/oracledb_exporter/blob/master/README.md
中的Custom metrics部分，我使用的命令供参考：
```bash
docker cp ./default-metrics.toml e968ffd2a229:/

docker commit -m "202209 default-metrics.toml" -a "jiangyong" e968ffd2a229 oracledb_exporter:jiangyong202209
```

