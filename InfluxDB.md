```sh
CREATE DATABASE mydb
```

```sh
SHOW DATABASES
```

```sh
USE mydb
```
MEASUREMENT & TAG & FIELD
```sh
<measurement>[,<tag-key>=<tag-value>...] <field-key>=<field-value>[,<field2-key>=<field2-value>...] [unix-nano-timestamp]
cpu,host=serverA,region=us_west value=1
#measurement: cpu
#tags: host,region
#fiels: value

temperature,machine=unit42,type=assembly external=25,internal=37 1434067467000000000
```
RETENTION POLICY & CONTINUOUS QUERY 
```sh
CREATE DATABASE "food_data"
CREATE RETENTION POLICY "two_hours" ON "food_data" DURATION 2h REPLICATION 1 DEFAULT
CREATE RETENTION POLICY "a_year" ON "food_data" DURATION 52w REPLICATION 1
CREATE CONTINUOUS QUERY "cq_30m" ON "food_data" BEGIN
SELECT mean("website") AS "mean_website",mean("phone") AS "mean_phone"
INTO "a_year"."downsampled_orders"
FROM "orders"
GROUP BY time(30m)
END

CREATE database mydb with duration 7d REPLICATION 1 SHARD DURATION 1h name myRP
```
