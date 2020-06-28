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

#INSERT DEFAULT RETENTION POLICY
INSERT treasures,captain_id=pirate_king value=2
#INSERT EXISTING RETENTION POLICY
INSERT INTO oneday treasures,captain_id=pirate_king value=2
```

INFLUX CLI
```sh
influx
influx --help

influx -execute 'SELECT * FROM "h2o_feet" LIMIT 3' -database="NOAA_water_database" -precision=rfc3339

influx -format=json
influx -format=json-pretty
```

```sh
curl -i -XPOST http://localhost:8086/query --data-urlencode "q=CREATE DATABASE mydb"

# write to a database using the InfluxDB 1.8 API
curl -i -XPOST 'http://localhost:8086/write?db=mydb'
--data-binary 'cpu_load_short,host=server01,region=us-west value=0.64 1434055562000000000'

# write to a database using the InfluxDB 2.0 API (compatible with InfluxDB 1.8+)
curl -i -XPOST 'http://localhost:8086/api/v2/write?bucket=db/rp&precision=ns' \
  --header 'Authorization: Token username:password' \
  --data-raw 'cpu_load_short,host=server01,region=us-west value=0.64 1434055562000000000'

curl -i -XPOST 'http://localhost:8086/write?db=mydb' --data-binary @cpu_data.txt

#Query data with Flux
curl -XPOST localhost:8086/api/v2/query -sS \
  -H 'Accept:application/csv' \
  -H 'Content-type:application/vnd.flux' \
  -d 'from(bucket:"telegraf")
        |> range(start:-5m)
        |> filter(fn:(r) => r._measurement == "cpu")' 

# Query data with InfluxQL
curl -G 'http://localhost:8086/query?pretty=true' --data-urlencode "db=mydb" --data-urlencode "q=SELECT \"value\" FROM \"cpu_load_short\" WHERE \"region\"='us-west'"
```

## Authors
[Himmet  GENCER](https://www.linkedin.com/in/himmet-gencer-214b7020/)

