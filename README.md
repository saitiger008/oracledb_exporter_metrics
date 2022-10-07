# oracledb_exporter_metrics
default-metrics.toml for oracledb_exporter

公司的大佬级DBA做了个Grafana的监控图：
https://grafana.com/grafana/dashboards/17136-oracledb-new-202210/

这么炫酷的图俺就向大佬申请，大佬同意拿出来分享给大家，本项目就是给oracledb_exporter用的default-metrics.toml，使用方法参见：

https://github.com/iamseth/oracledb_exporter/blob/master/README.md

中的Custom metrics部分，使用docker配置监控的命令供参考：
```bash
docker pull iamseth/oracledb_exporter

docker run -dit iamseth/oracledb_exporter

docker cp ./default-metrics.toml [CONTAINER ID]:/

docker commit -m "202209 default-metrics.toml" -a "jiangyong" [CONTAINER ID] oracledb_exporter:jiangyong202209

docker run --restart=always -d -it -p 19001:9161 -e DATA_SOURCE_NAME=[dbusername]/"[YourPassword]"@//[YourDBip]:1521/[DBserviceName] oracledb_exporter:jiangyong202209

# 配置文件参考：
# more db_discovery_ehrdb.json
[
{"targets":["[YourDockerServerIP]:19001"],"labels":{"type":"db","group":"[YourGroupName]","oracle_ip":"[YourDBip]","oracle_instance":"[DBserviceName]"}}
]
```

