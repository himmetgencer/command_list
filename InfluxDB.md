```sh
CREATE DATABASE mydb
```

```sh
SHOW DATABASES
```

```sh
USE mydb
```

```sh
<measurement>[,<tag-key>=<tag-value>...] <field-key>=<field-value>[,<field2-key>=<field2-value>...] [unix-nano-timestamp]
cpu,host=serverA,region=us_west value=1
#measurement: cpu
#tags: host,region
#fiels: value

temperature,machine=unit42,type=assembly external=25,internal=37 1434067467000000000
```

```sh
CREATE DATABASE "food_data"
CREATE RETENTION POLICY "two_hours" ON "food_data" DURATION 2h REPLICATION 1 DEFAULT
CREATE RETENTION POLICY "a_year" ON "food_data" DURATION 52w REPLICATION 1
```

