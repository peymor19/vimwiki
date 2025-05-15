# Benchmarking MySQL
Disable query cache in your database to test
```
[mysqld]
innodb_buffer_pool_size=1M
key_buffer_size=8
query_cache_type=0
```

# How to fix error 1236
# Usually caused by primary shutting down unexpectedly

Example error:
```
Got fatal error 1236 from master when reading data from binary log:
'Client requested master to start replication from impossible position;
the first event 'primary_1-bin.000001' at 557606231,
the last event read from 'primary_1-bin.000001' at 4,
the last byte read from 'primary_1-bin.000001' at 4.'
```

Extra info:
https://www.percona.com/blog/mysql-replication-got-fatal-error-1236-causes-and-cures/

To fix the issue you need to move to the next binlog because the last one finished unexpectedly
`STOP SLAVE;`
`CHANGE MASTER TO MASTER_LOG_FILE='master1-bin.000002', MASTER_LOG_POS=4;`
`START SLAVE;`
