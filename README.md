# Awesome Data Engineering TIL [![Awesome](https://awesome.re/badge-flat2.svg)](https://github.com/sindresorhus/awesome)

> A short curated list of awesome 'TIL-today-I-learned' resources related to Data Engineering. See this new video on [Claude Code for Data Engineering](https://www.ginobaltazar.com/downloads/claude_for_data_engineering.mp4)! Among these, I can vouch for and have experiences in [Kafka](https://kafka.apache.org/), [Thrift](https://thrift.apache.org/), [Ent](https://entgo.io/docs/getting-started), [MySql](https://www.mysql.com/), [Presto](https://prestodb.github.io/docs/current/index.html), [Spark](https://spark.apache.org/), [Postgres](https://www.postgresql.org/), [Mongo](https://www.mongodb.comhttps://www.mongodb.com), [Prometheus](https://github.com/prometheus/prometheus), [Grafana](https://github.com/grafana/grafana), [Elastic](https://www.elastic.co/) and last but not least, the humble [MS Excel](https://github.com/ginobaltazar7/66daysofdata?tab=readme-ov-file#excel) now supported by MS365 Copilot.

Last updated: [August 12, 2026](https://github.com/ginobaltazar7/awesome-data-engineering-til/commits/main/?since=2026-08-12).

## Contents

- [Playbooks](#playbooks)
- [Databases](#databases)
- [Data Comparison](#data-comparison)
- [Data Ingestion](#data-ingestion)
- [Storage Layers & Distributed File Systems](#storage-layers)
- [Serialization format](#serialization-format)
- [Stream Processing](#stream-processing)
- [Batch Processing](#batch-processing)
- [Dataviz Charts and Dashboards](#charts-and-dashboards)
- [Pipeline Orchestration](#pipeline-orchestration)
- [Data Lake Management](#data-lake-management)
- [ELK Elastic Logstash Kibana](#elk-elastic-logstash-kibana)
- [Docker](#docker)
- [Datasets](#datasets)
  - [Realtime](#realtime)
  - [Data Dumps](#data-dumps)
- [Monitoring](#monitoring)
  - [Prometheus](#prometheus)
- [Data Profiler](#data-profiler)
- [Testing](#testing)
- [Org-specific](#org-specific)
- [Community](#community)
  - [Forums](#forums)
  - [Conferences](#conferences)
  - [Podcasts](#podcasts)
  - [Books](#books)
  - [Videos](#videos)

# Playbooks

- [Claude Code for Staff Data Architecture](../main/playbooks/claude-data-engineering-framework.md) — See my sample comprehensive design guide and baseline configurations implementing machine-readable **Data Contracts**, shift-left CI/CD validation, and automated **Amundsen** catalog tracking.
- [Astronomer Agents](https://github.com/astronomer/agents) - AI agent tooling for building, debugging, and triaging Airflow DAGs. Built by the team at [Astronomer](https://www.astronomer.io/).
- [Data Engineering Agent Skills by Vaquar Khan](vaquarkhan/data-engineering-agent-skills) -  A specialized and comprehensive repository hosting data engineering skill. Via [Vaquar Khan](https://github.com/vaquarkhan)
- [dbt Agent Skills](https://github.com/dbt-labs/dbt-agent-skills) - curated collection of Agent Skills for dbt platform.
- [Data Analytics and DE skills by borghei](https://github.com/borghei/Claude-Skills/blob/main/data-analytics/CLAUDE.md) Look under the data-analytics/ folder! Via [Amin Borghei](https://github.com/borghei)
- [Data Pipeline Expert by Claude Skills](https://claudeskills.info/skills/rightnow-ai/openfang/data-pipeline/) - standalone production playbook hosted via the Claude Skills Hub directory.  I like the focus on common engineering pitfalls, such as running full table scans when incremental loads are feasible, avoiding hardcoding credentials, or skipping vital post-ingestion freshness checks. This data-pipeline skill is one of many in the official agent playbook bundled with RightNow-AI/openfang, an open-source autonomous agent framework built in Rust that currently has over [18,000 stars on GitHub](https://github.com/rightnow-ai/openfang).
- [Claude Skills for Engineering](https://github.com/alirezarezvani/claude-skills/tree/main/engineering-team) - automate creation and maintenance of CLAUDE.md files with Forge and Claude Skills for Engineering. Comprehensive with many other skills! Via [Ali Rezvani](https://github.com/alirezarezvani)

# Databases

- Relational
  - [RQLite](https://github.com/rqlite/rqlite) - distributed relational database built on SQLite.
  - [MySQL](https://www.mysql.com/) - Said to be the 'worlds most popular open source database' - Big tech like Facebook is built on MySQL.
    - [TiDB](https://github.com/pingcap/tidb) - "Ti" stands for Titanium is an open-source, cloud-native, distributed SQL database designed for high availability, horizontal and vertical scalability.
    - [Percona XtraBackup](https://www.percona.com/software/mysql-database/percona-xtrabackup) - Percona XtraBackup is a free, open source, complete online backup solution for all versions of Percona Server, MySQL® and MariaDB®.
    - [Percona Orchestrator](https://github.com/percona/orchestrator) - MySQL high availability and replication management too but not currently maintained however.
  - [MariaDB](https://mariadb.org/) - An enhanced, drop-in replacement for MySQL.
  - [PostgreSQL](https://www.postgresql.org/) - Versatile open source database. Data engineering SQL interview loops often utilize Postgres.
  - [Amazon RDS](https://aws.amazon.com/rds/) - Amazon RDS makes it easy to set up, operate, and scale a relational database in the cloud.

- Key-Value
  - [Redis](https://redis.io/) - An open source, BSD licensed, advanced key-value cache and store.
  - [AWS DynamoDB](https://aws.amazon.com/dynamodb/) - A fast and flexible NoSQL database service for all applications that need consistent, single-digit millisecond latency at any scale.
  - [EmbedDB](https://github.com/ubco-db/EmbedDB) - efficient time series, key-value, and relational data engine for Arduinos and embedded devices.
  - [Valkey](https://github.com/valkey-io/valkey) The definitive, Linux Foundation-backed open-source fork of Redis created after the 2024 Redis license change.
  - [Dragonfly](https://github.com/dragonflydb/dragonfly) A modern, highly concurrent, multi-threaded in-memory key-value store built as a drop-in Redis replacement.
  - [TiKV](https://github.com/tikv/tikv) A highly distributed, transactional key-value store designed to support massive scale (and the engine backing TiDB).

- Wide-Column Stores
  - [Cassandra](https://github.com/apache/cassandra) - Distributed high-availability storage.
  - [ScyllaDB](https://scylladb.com) - High-performance C++ Cassandra alternative.
  - [HBase](https://github.com/apache/hbase) - Hadoop-based real-time big data storage.
  - [CCM](https://github.com/apache/cassandra-ccm) - Tool for local Cassandra testing.
  - [Cassandra Reaper](https://github.com/thelastpickle/cassandra-reaper) - Automated Cassandra repair tool.

- Columnar Databases
  - [ClickHouse](https://clickhouse.com) - Fast, open-source columnar analytics.
  - [AWS Redshift](https://amazon.com) - Managed cloud data warehouse.
  - [Apache Pinot](https://github.com/apache/pinot) - A distributed, real-time OLAP data store designed to deliver low-latency analytical queries on massive streaming datasets.


- Document
  - [MongoDB](https://www.mongodb.com) - An open-source, document database designed for ease of development and scaling.
    - [Percona Server for MongoDB](https://www.percona.com/software/mongo-database/percona-server-for-mongodb) - Percona Server for MongoDB® is a free, enhanced, fully compatible, open source, drop-in replacement for the MongoDB® Community Edition that includes enterprise-grade features and functionality.
    - [MongoDB In-Memory Server](https://github.com/typegoose/mongodb-memory-server) - Distributed In Memory Server for Mongo.
  - [Couchbase](https://www.couchbase.com/) - The highest performing NoSQL distributed database.
  - [PocketBase](https://github.com/pocketbase/pocketbase) - open-source realtime Go backend.
  - [RavenDB](https://ravendb.net/) - Fully Transactional NoSQL Document Database.

- Graph
  - [Neo4j](https://neo4j.com/) - The world's leading graph database.
  - [ArangoDB](https://www.arangodb.com/) - A distributed free and open-source database with a flexible data model for documents, graphs, and key-values.
  - [JanusGraph](https://github.com/JanusGraph/janusgraph) - active, scalable distributed graph database.
  - [Gaffer](https://github.com/gchq/Gaffer) - A large-scale graph database.

- Distributed Transactional / NewSQL
  - [Datomic](https://www.datomic.com) - Clojure world, Cognitect made Datomic Pro completely free to use.
  - [Apache Geode](https://github.com/apache/geode) - Minimally maintained and still has minor security updates.
  - [VoltDB](https://voltdb.com/) - VoltDb is an ACID-compliant RDBMS which uses a [shared nothing architecture](https://en.wikipedia.org/wiki/Shared-nothing_architecture).

- Timeseries
  - [VictoriaMetrics](https://github.com/victoriametrics/VictoriaMetrics) - for monitoring and managing time series data. A number of case studies in its git like by Grammarly or Roblox.
  - [InfluxDB](https://github.com/influxdata/influxdb) - Scalable datastore for metrics, events, and real-time analytics.
  - [QuestDB](https://github.com/questdb/questdb) - Open-source time-series database offering fast ingestion and low-latency SQL queries.
  - [Heroic](https://github.com/spotify/heroic) - A scalable time series database based on Cassandra and Elasticsearch, by Spotify.
  - [TimescaleDB](https://github.com/timescale/timescaledb) - An open-source time-series SQL database built as an extension on top of PostgreSQL.
  - [Druid](https://github.com/apache/incubator-druid) - Column oriented distributed data store ideal for powering interactive applications.
  - [Riak-TS](https://basho.com/products/riak-ts/) - Riak TS is the only enterprise-grade NoSQL time series database optimized specifically for IoT and Time Series data.
  - [Akumuli](https://github.com/akumuli/Akumuli) - Akumuli is a numeric time-series database. It can be used to capture, store and process time-series data in real-time. The word "akumuli" can be translated from esperanto as "accumulate".
  - [Rhombus](https://github.com/Pardot/Rhombus) - A time-series object store for Cassandra that handles all the complexity of building wide row indexes.
  - [Dalmatiner DB](https://github.com/dalmatinerdb/dalmatinerdb) - Fast distributed metrics database.
  - [Blueflood](https://github.com/rackerlabs/blueflood) - A distributed system designed to ingest and process time series data.
  - [Timely](https://github.com/NationalSecurityAgency/timely) - Timely is a time series database application that provides secure access to time series data based on Accumulo and Grafana.

- Other
  - [Tarantool](https://github.com/tarantool/tarantool/) - Tarantool is an in-memory database and application server.
  - [GreenPlum](https://github.com/greenplum-db/gpdb) - The Greenplum Database (GPDB) - An advanced, fully featured, open source data warehouse. It provides powerful and rapid analytics on petabyte scale data volumes.
  - [cayley](https://github.com/cayleygraph/cayley) - An open-source graph database. Google.
  - [Snappydata](https://github.com/SnappyDataInc/snappydata) - SnappyData: OLTP + OLAP Database built on Apache Spark.
  - [TimescaleDB](https://www.timescale.com/) - Built as an extension on top of PostgreSQL, TimescaleDB is a time-series SQL database providing fast analytics, scalability, with automated data management on a proven storage engine.
  - [DuckDB](https://duckdb.org/) - DuckDB is a fast in-process analytical database that has zero external dependencies, runs on Linux/macOS/Windows, offers a rich SQL dialect, and is free and extensible.

# Data Ingestion

* [Kafka](https://kafka.apache.org/) Publish-subscribe messaging rethought as a distributed commit log.
	* [Bottled Water](https://github.com/confluentinc/bottledwater-pg) Change data capture from PostgreSQL into Kafka. Deprecated.
	* [Confluent Kafka](https://docs.confluent.io/platform/current/clients/confluent-kafka-python/html/index.html) Confluent Python client. 
	* [kafkat](https://github.com/airbnb/kafkat) Simplified command-line administration for Kafka brokers
	* [kafkacat](https://github.com/edenhill/kafkacat) Generic command line non-JVM Apache Kafka producer and consumer
	* [pg-kafka](https://github.com/xstevens/pg_kafka) A PostgreSQL extension to produce messages to Apache Kafka
	* [librdkafka](https://github.com/edenhill/librdkafka) The Apache Kafka C/C++ library
	* [kafka-docker](https://github.com/wurstmeister/kafka-docker) Kafka in Docker
	* [kafka-manager](https://github.com/yahoo/kafka-manager) A tool for managing Apache Kafka
	* [kafka-node](https://github.com/SOHU-Co/kafka-node) Node.js client for Apache Kafka 0.8
	* [kafka-python](https://github.com/dpkp/kafka-python) Kafka Python client
	* [Secor](https://github.com/pinterest/secor) Pinterest's Kafka to S3 distributed consumer
	* [Kafka-logger](https://github.com/uber/kafka-logger) Kafka-winston logger for nodejs from uber
* [AWS Kinesis](https://aws.amazon.com/kinesis/) A fully managed, cloud-based service for real-time data processing over large, distributed data streams.
* [RabbitMQ](https://www.rabbitmq.com/) Robust messaging for applications.
* [FluentD](https://www.fluentd.org) An open source data collector for unified logging layer.
* [Embulk](https://www.embulk.org) An open source bulk data loader that helps data transfer between various databases, storages, file formats, and cloud services.
* [Apache Sqoop](https://sqoop.apache.org) A tool designed for efficiently transferring bulk data between Apache Hadoop and structured datastores such as relational databases.
* [Nakadi](https://nakadi.io) Nakadi is an open source event messaging platform that provides a REST API on top of Kafka-like queues.
* [Pravega](http://www.pravega.io) Pravega provides a new storage abstraction - a stream - for continuous and unbounded data.
* [Apache Pulsar](https://pulsar.apache.org/) Apache Pulsar is an open-source distributed pub-sub messaging system.
* [AWS Data Wrangler](https://github.com/awslabs/aws-data-wrangler) Utility belt to handle data on AWS.
- [Airbyte](https://airbyte.io/) - Open-source data integration for modern data teams.
- [Artie](https://www.artie.com/) - Real-time data ingestion tool leveraging change data capture.
- [Sling](https://slingdata.io/) - Sling is CLI data integration tool specialized in moving data between databases, as well as storage systems.
- [Meltano](https://meltano.com/) - CLI & code-first ELT.
  - [Singer SDK](https://sdk.meltano.com) - The fastest way to build custom data extractors and loaders compliant with the Singer Spec.
- [Google Sheets ETL](https://github.com/fulldecent/google-sheets-etl) - Live import all your Google Sheets to your data warehouse.
- [CsvPath Framework](https://www.csvpath.org/) - A delimited data preboarding framework that fills the gap between MFT and the data lake.
- [Estuary Flow](https://estuary.dev) - No/low-code data pipeline platform that handles both batch and real-time data ingestion.

# Data Comparison

- [datacompy](https://github.com/capitalone/datacompy) - DataComPy is a Python library that facilitates the comparison of two DataFrames in pandas, Polars, Spark and more. The library goes beyond basic equality checks by providing detailed insights into discrepancies at both row and column levels.

# Serialization format

* [Apache Thrift](https://thrift.apache.org/) Apache Thrift inspired by creation of Thrift project in early Facebook. Allows you to define data types and service interfaces in a simple definition file with a codegen engine. Consider another favorite companion [Ent](https://entgo.io/docs/getting-started), also another once internal Facebook project but now open-sourced, to model database schema as a graph structure.
* [Apache Avro](https://avro.apache.org) Apache Avro™ is a data serialization system
* [Apache Arrow](https://arrow.apache.org/) Apache Arrow is columnar memory format for flat and hierarchical data.
* [Apache Parquet](https://parquet.apache.org) Apache Parquet is a columnar storage format available to any project in the Hadoop ecosystem, regardless of the choice of data processing framework, data model or programming language.
	* [Snappy](https://github.com/google/snappy) A fast compressor/decompressor. Used with Parquet
multi-processor, multi-core machines
* [Apache ORC](https://orc.apache.org/) The smallest, fastest columnar storage for Hadoop workloads 
* [ProtoBuf](https://github.com/protocolbuffers/protobuf) Protocol Buffers - Google's data interchange format
* [Kryo](https://github.com/EsotericSoftware/kryo) Kryo is a fast and efficient object graph serialization framework for Java

# Storage Layers

- [HDFS](https://hadoop.apache.org/docs/current/hadoop-project-dist/hadoop-hdfs/HdfsDesign.html) - A distributed file system designed to run on commodity hardware.
- [AWS S3](https://aws.amazon.com/s3/) - Object storage built to retrieve any amount of data from anywhere.
  - [smart_open](https://github.com/RaRe-Technologies/smart_open) - Utils for streaming large files (S3, HDFS, gzip, bz2).
- [Alluxio](https://www.alluxio.org/) - Alluxio is a memory-centric distributed storage system enabling reliable data sharing at memory-speed across cluster frameworks, such as Spark and MapReduce.
- [CEPH](https://ceph.com/) - Ceph is a unified, distributed storage system designed for excellent performance, reliability, and scalability.
- [JuiceFS](https://github.com/juicedata/juicefs) - JuiceFS is a high-performance Cloud-Native file system driven by object storage for large-scale data storage.
- [SeaweedFS](https://github.com/chrislusf/seaweedfs) - Seaweed-FS is a simple and highly scalable distributed file system. There are two objectives: to store billions of files! to serve the files fast! Instead of supporting full POSIX file system semantics, Seaweed-FS choose to implement only a key~file mapping. Similar to the word "NoSQL", you can call it as "NoFS".

# Stream Processing

- [Apache Beam](https://beam.apache.org/) - Apache Beam is a unified programming model that implements both batch and streaming data processing jobs that run on many execution engines.
- [Spark Streaming](https://spark.apache.org/streaming/) - Spark Streaming makes it easy to build scalable fault-tolerant streaming applications.
- [Apache Flink](https://flink.apache.org/) - Apache Flink is a streaming dataflow engine that provides data distribution, communication, and fault tolerance for distributed computations over data streams.
- [Apache NiFi](https://nifi.apache.org/) - An easy to use, powerful, and reliable system to process and distribute data.
- [Spring Cloud Dataflow](https://cloud.spring.io/spring-cloud-dataflow/) - Streaming and tasks execution between Spring Boot apps.
- [HStreamDB](https://github.com/hstreamdb/hstream) - The streaming database built for IoT data storage and real-time processing.
- [Kuiper](https://github.com/emqx/kuiper) - An edge lightweight IoT data analytics/streaming software implemented by Golang, and it can be run at all kinds of resource-constrained edge devices.
- [Zilla](https://github.com/aklivity/zilla) - - An API gateway built for event-driven architectures and streaming that supports standard protocols such as HTTP, SSE, gRPC, MQTT, and the native Kafka protocol.
- [SwimOS](https://github.com/swimos/swim-rust) - A framework for building real-time streaming data processing applications that supports a wide range of ingestion sources.

# Batch Processing

- [Hadoop MapReduce](https://hadoop.apache.org/docs/current/hadoop-mapreduce-client/hadoop-mapreduce-client-core/MapReduceTutorial.html) - Hadoop MapReduce is a software framework for easily writing applications which process vast amounts of data (multi-terabyte data-sets) - in-parallel on large clusters (thousands of nodes) - of commodity hardware in a reliable, fault-tolerant manner.
- [Spark](https://spark.apache.org/) - A multi-language engine for executing data engineering, data science, and machine learning on single-node machines or clusters.
  - [Spark Packages](https://spark-packages.org) - A community index of packages for Apache Spark.
  - [Spark RDD API Examples](https://homepage.cs.latrobe.edu.au/zhe/ZhenHeSparkRDDAPIExamples.html) - Examples by Zhen He.
  - [Livy](https://livy.incubator.apache.org) - The REST Spark Server.
  
  - Spark Profilers for performance engineering of Spark
    - [Sparklens](https://github.com/qubole/sparklens )
    - [sparkMeasure](https://github.com/LucaCanali/sparkMeasure)
    - [Sparklint](https://github.com/groupon/sparklint )
    - [Dr. Elephant](https://github.com/linkedin/dr-elephant )
    - [SparkOscope](https://github.com/ibm-research-ireland/sparkoscope)

- [AWS EMR](https://aws.amazon.com/emr/) - A web service that makes it easy to quickly and cost-effectively process vast amounts of data.

- MLOps
  - [H2O](https://www.h2o.ai/) - Fast scalable machine learning API for smarter applications.
  - [Spark MLlib](https://spark.apache.org/docs/latest/ml-guide.html) - Spark's scalable machine learning library consisting of common learning algorithms and utilities, including classification, regression, clustering, collaborative filtering, dimensionality reduction, as well as underlying optimization primitives.

- Batch Graph
  - [Spark GraphX](https://spark.apache.org/graphx/) - Apache Spark's API for graphs and graph-parallel computation.

- Batch SQL
  - [Presto](https://github.com/prestodb/presto) - A distributed SQL query engine designed to query massive datasets across heterogeneous data sources, maintained by the Linux Foundation and Meta.
  - [Trino](https://github.com/trinodb/trino) - The fast, distributed SQL query engine formerly known as PrestoSQL; it represents the primary community-driven standard for data lakehouse analytics.
    - [PyHive](https://github.com/dropbox/PyHive) - A collection of Python DB-API and SQLAlchemy interfaces for both Hive and Presto/Trino.
  - [Drill](https://drill.apache.org/) - Schema-free SQL Query Engine for Hadoop, NoSQL and Cloud Storage.

- Vectorized Execution
  - [Velox](https://github.com/facebookincubator/velox) - Meta's modular, composable C++ vectorized execution engine library designed to optimize analytical, batch, and AI/ML system runtimes.
  - [Apache Gluten](https://github.com/apache/gluten) - An injection middle-layer that offloads JVM-based Apache Spark execution paths to high-performance native engines like Velox using Substrait plans.


# Databricks

* [Databricks](https://github.com/databricks) Big data processing platform founded by the creators of Apache Spark.
	* [Databricks Notebook Gallery](https://www.databricks.com/discover/notebook-gallery) Sample gallery of databricks notebooks.
	* [Awesome Databricks by jrlasak](https://github.com/jrlasak/awesome-databricks) Updated list of resources around Databricks, including links to learning and certifications!

# Charts and Dashboards

- [Streamlit](https://github.com/streamlit/streamlit) - Makes it easy to share Python scripts into data viz.
- [Highcharts](https://www.highcharts.com/) A charting library written in pure JavaScript, offering an easy way of adding interactive charts to your web site or web application.
- [ThoughtSpot](https://github.com/thoughtspot/ts_rest_api_and_tml_tools) Business intelligence analytics search, alternative to Tableau
- [ZingChart](https://www.zingchart.com/) Fast JavaScript charts for any data set.
- [C3.js](https://c3js.org) D3-based reusable chart library.
- [D3.js](https://d3js.org/) A JavaScript library for manipulating documents based on data.
	- [D3Plus](https://d3plus.org) D3's simplier, easier to use cousin. Mostly predefined templates that you can just plug data in.
- [Plotly](https://github.com/plotly/dash) Flask, JS, and CSS boilerplate for interactive, web-based visualization apps in Python
- [Apache Superset](https://github.com/apache/incubator-superset) Apache Superset (incubating) is a modern, enterprise-ready business intelligence web application
- [Redash](https://redash.io/) Make Your Company Data Driven. Connect to any data source, easily visualize and share your data.
- [Metabase](https://github.com/metabase/metabase) Metabase is the easy, open source way for everyone in your company to ask questions and learn from data.
- [PyQtGraph](http://www.pyqtgraph.org/) PyQtGraph is a pure-python graphics and GUI library built on PyQt4 / PySide and numpy. It is intended for use in mathematics / scientific / engineering applications.
- [Seaborn](https://seaborn.pydata.org) - A Python visualization library based on matplotlib. It provides a high-level interface for drawing attractive statistical graphics.
- [Grafana](https://github.com/grafana/grafana) Grafana allows you to query, visualize, alert on and understand your metrics no matter where they are stored.
- [Recharts](https://recharts.github.io/) - composable charting library for React environments.
- [Apache Echarts](https://echarts.apache.org/en/index.html) - as with Recharts, also for React.

# Pipeline Orchestration

- [Luigi](https://github.com/spotify/luigi) - Luigi is a Python module that helps you build complex pipelines of batch jobs.
- [CronQ](https://github.com/seatgeek/cronq) - An application cron-like system. [Used](https://chairnerd.seatgeek.com/building-out-the-seatgeek-data-pipeline/) w/Luige. Deprecated.
- [Cascading](https://www.cascading.org/) - Java based application development platform.
- [Airflow](https://github.com/apache/airflow) - Airflow is a system to programmatically author, schedule, and monitor data pipelines.
- [Azkaban](https://azkaban.github.io/) - Azkaban is a batch workflow job scheduler created at LinkedIn to run Hadoop jobs. Azkaban resolves the ordering through job dependencies and provides an easy-to-use web user interface to maintain and track your workflows.
- [Dagster](https://github.com/dagster-io/dagster) - Dagster is an open-source Python library for building data applications.
- [Hamilton](https://github.com/dagworks-inc/hamilton) - Hamilton is a lightweight library to define data transformations as a directed-acyclic graph (DAG). If you like dbt for SQL transforms, you will like Hamilton for Python processing.
- [Kedro](https://kedro.readthedocs.io/en/latest/) - Kedro is a framework that makes it easy to build robust and scalable data pipelines by providing uniform project templates, data abstraction, configuration and pipeline assembly.
- [Dataform](https://dataform.co/) - An open-source framework and web based IDE to manage datasets and their dependencies. SQLX extends your existing SQL warehouse dialect to add features that support dependency management, testing, documentation and more.
- [Census](https://getcensus.com/) - A reverse-ETL tool that let you sync data from your cloud data warehouse to SaaS applications like Salesforce, Marketo, HubSpot, Zendesk, etc. No engineering favors required—just SQL.
- [dbt](https://github.com/dbt-labs/dbt-core) - Dbt helps transforms data using SQL. The 'T' in ETL. I've use dbt heavily for metadata abstractions like data contracts.
- [Kestra](https://kestra.io/) - Scalable, event-driven, language-agnostic orchestration and scheduling platform to manage millions of workflows declaratively in code.
- [RudderStack](https://github.com/rudderlabs/rudder-server) - A warehouse-first Customer Data Platform that enables you to collect data from every application, website and SaaS platform, and then activate it in your warehouse and business tools.
- [PACE](https://github.com/getstrm/pace) - An open source framework that allows you to enforce agreements on how data should be accessed, used, and transformed, regardless of the data platform (Snowflake, BigQuery, DataBricks, etc.)
- [Prefect](https://prefect.io/) - Prefect is an orchestration and observability platform. With it, developers can rapidly build and scale resilient code, and triage disruptions effortlessly.
- [Multiwoven](https://github.com/Multiwoven/multiwoven) - The open-source reverse ETL, data activation platform for modern data teams.
- [SuprSend](https://www.suprsend.com/products/workflows) - Create automated workflows and logic using API's for your notification service. Add templates, batching, preferences, inapp inbox with workflows to trigger notifications directly from your data warehouse.
- [Kestra](https://github.com/kestra-io/kestra) - A versatile open source orchestrator and scheduler built on Java, designed to handle a broad range of workflows with a language-agnostic, API-first architecture.
- [Mage](https://www.mage.ai) - Open-source data pipeline tool for transforming and integrating data.

# Data Lake Management

- [Apache Iceberg](https://github.com/apache/iceberg) - open-source community favorite backed by Snowflake, Tabular, and AWS.
- [Amundsen](https://github.com/amundsen-io/amundsen) - data discovery and metadata engine, like Google search for data, Lyfts' open source product for data catalog.
- [Apache Hudi](https://hudi.apache.org/) - An open source streaming data lakehouse platform with interesting take on upsert for cloud.
- [lakeFS](https://github.com/treeverse/lakeFS) - lakeFS is an open source platform that delivers resilience and manageability to object-storage based data lakes.
- [Project Nessie](https://github.com/projectnessie/nessie) - Project Nessie is a Transactional Catalog for Data Lakes with Git-like semantics. Works with Apache Iceberg tables.
- [Ilum](https://ilum.cloud/) - Ilum is a modular Data Lakehouse platform that simplifies the management and monitoring of Apache Spark clusters across Kubernetes and Hadoop environments.
- [Gravitino](https://github.com/apache/gravitino) - Gravitino is an open-source, unified metadata management for data lakes, data warehouses, and external catalogs. 

# ELK Elastic Logstash Kibana

- [Elasticsearch](https://www.elastic.co/) - Search & Analyze Data in Real Time.
- [docker-logstash](https://github.com/pblittle/docker-logstash) - A highly configurable Logstash (1.4.4) - Docker image running Elasticsearch (1.7.0) - and Kibana (3.1.2).
- [elasticsearch-jdbc](https://github.com/jprante/elasticsearch-jdbc) - JDBC importer for Elasticsearch.
- [ZomboDB](https://github.com/zombodb/zombodb) - Postgres Extension that allows creating an index backed by Elasticsearch.
- [Vector](https://github.com/vectordotdev/vector) - high performance tooling for building observability data pipelines. Atlassian, CVS and Visa are said to be enterprise users.

# Docker

- [Gockerize](https://github.com/redbooth/gockerize) - Package golang service into minimal Docker containers.
- [Flocker](https://github.com/ClusterHQ/flocker) - Easily manage Docker containers & their data.
- [Rancher](https://rancher.com/rancher-os/) - RancherOS is a 20mb Linux distro that runs the entire OS as Docker containers.
- [Kontena](https://www.kontena.io/) - Application Containers for Masses.
- [Weave](https://github.com/weaveworks/weave) - Weaving Docker containers into applications.
- [Zodiac](https://github.com/CenturyLinkLabs/zodiac) - A lightweight tool for easy deployment and rollback of dockerized applications.
- [cAdvisor](https://github.com/google/cadvisor) - Analyzes resource usage and performance characteristics of running containers.
- [Micro S3 persistence](https://github.com/figadore/micro-s3-persistence) - Docker microservice for saving/restoring volume data to S3.
- [Rocker-compose](https://github.com/grammarly/rocker-compose) - Docker composition tool with idempotency features for deploying apps composed of multiple containers. Deprecated.
- [Nomad](https://github.com/hashicorp/nomad) - Nomad is a cluster manager, designed for both long-lived services and short-lived batch processing workloads.
- [ImageLayers](https://imagelayers.io/) - Visualize Docker images and the layers that compose them.
- Alternatives to Docker
  - [Podman](https://www.redhat.com/en/topics/containers/what-is-podman) - A daemonless, open-source Linux native container engine for deploying and managing OCI containers.
  - [Finch](https://github.com/runfinch/finch) - An open-source command-line tool for local container development, providing an easy-to-use alternative client backed by AWS.
# Datasets

### Realtime

- [Eventsim](https://github.com/Interana/eventsim) - Event data simulator. Generates a stream of pseudo-random events from a set of users, designed to simulate web traffic.
- [Bytewax Public Real-Time Datasets](https://github.com/bytewax/awesome-public-real-time-datasets)- A highly curated community repository documenting free and public streaming webhooks, WebSockets, and SSE feeds for real-world integration testing.
- [ADS-B Exchange API](https://streaming-docs.adsbexchange.com/quickstart/docker) - High-throughput aviation data engine delivering live, unfiltered global aircraft position coordinates and transponder telemetry via streaming endpoints.
- [PurpleAir API](https://www.purpleair.com/api) - RESTful and real-time sensor array endpoints feeding live particulate matter numbers and environmental air quality indices from citizen-science IoT monitors worldwide.
- [fake-web-events](https://github.com/andresionek91/fake-web-events) - A Python generator utility engineered to continuously stream simulation events (page views, clicks, shopping carts) to message queues to mimic live consumer e-commerce activity.


### Data Dumps

- [GitHub Archive](https://www.gharchive.org/) - GitHub's public timeline since 2011, updated every hour.
- [Common Crawl](https://commoncrawl.org/) - Open source repository of web crawl data.
- [Wikipedia](https://dumps.wikimedia.org/enwiki/latest/) - Wikipedia's complete copy of all wikis, in the form of Wikitext source and metadata embedded in XML. A number of raw database tables in SQL form are also available.

# Monitoring

### Prometheus

- [Prometheus](https://github.com/prometheus/prometheus) - An open-source service monitoring system and time series database.
- [HAProxy Exporter](https://github.com/prometheus/haproxy_exporter) - Simple server that scrapes HAProxy stats and exports them via HTTP for Prometheus consumption.

### MSSQL Server Monitoring Scripts
* [CPU Usage](https://github.com/ginobaltazar7/awesome-data-engineering/blob/master/tsql-scripts/CPUmonitor.sql)  
* [Memory Usage](https://github.com/ginobaltazar7/awesome-data-engineering/blob/master/tsql-scripts/Memorymonitor.sql)    
* [Disk Usage](https://github.com/ginobaltazar7/awesome-data-engineering/blob/master/tsql-scripts/Diskspacemonitor.sql)    
* [Sessions](https://github.com/ginobaltazar7/awesome-data-engineering/blob/master/tsql-scripts/Sessionmonitor.sql)    
* [Blocking and Deadlock](https://github.com/ginobaltazar7/awesome-data-engineering/blob/master/tsql-scripts/Blockingmonitor.sql)    
* [IO](https://github.com/ginobaltazar7/awesome-data-engineering/tsql-scripts/blob/master/IOmonitor.sql)    
* [Wait Stat](https://github.com/ginobaltazar7/awesome-data-engineering/blob/master/tsql-scripts/Waitstatmonitor.sql)   
* [sp_whoisactive](https://github.com/ginobaltazar7/awesome-data-engineering/blob/master/tsql-scripts/sp_whoisactive.sql) and more here via [Adam Machanic](http://dataeducation.com/sp_whoisactive-for-azure-sql-database-attempt-2/)  


### Data Profiler

- [Data Profiler](https://github.com/capitalone/dataprofiler) - load data like from a CSV with a single command, into an automatically formatted DataFrame.


### Testing

* [lakeFS](https://github.com/treeverse/lakeFS) lakeFS is an open source platform that delivers resilience and manageability to object-storage based data lakes.
- [Grai](https://github.com/grai-io/grai-core/) - A data catalog tool that integrates into your CI system exposing downstream impact testing of data changes. These tests prevent data changes which might break data pipelines or BI dashboards from making it to production.
- [DQOps](https://github.com/dqops/dqo) - An open-source data quality platform for the whole data platform lifecycle from profiling new data sources to applying full automation of data quality monitoring.
- [DataKitchen](https://datakitchen.io/) -  Open Source Data Observability for end-to-end Data Journey Observability, data profiling, anomaly detection, and auto-created data quality validation tests.
- [RunSQL](https://runsql.com/) - Free online SQL playground for MySQL, PostgreSQL, and SQL Server. Create database structures, run queries, and share results instantly.
- [Spark Playground](https://www.sparkplayground.com/) - Write, run, and test PySpark code on Spark Playground's online compiler. Access real-world sample datasets & solve interview questions to enhance your PySpark skills for data engineering roles.

# BigTech Company Repos

* [Amazon](https://github.com/aws) and [AWS blog](https://aws.amazon.com/blogs/big-data/)
* [Capital One](https://github.com/orgs/capitalone/repositories?type=all) 
* [Databricks](https://github.com/databricks) and [blog](https://www.databricks.com/blog/category/engineering/data-engineering)
* [Google](https://github.com/orgs/google/repositories?q=sort%3Astars&page=2) and [blog](https://tinyurl.com/573fymeh)
* [Meta](https://github.com/orgs/facebook/repositories) - PyTorch, React, RocksDB, Thrift, Ent and [blog](https://engineering.fb.com/category/data-infrastructure/)
* [Microsoft](https://github.com/microsoft) and [blog](https://techcommunity.microsoft.com/t5/data-architecture-blog/bg-p/DataArchitectureBlog)
* [Netflix](https://github.com/orgs/Netflix/repositories) and [blog](https://netflixtechblog.com/tagged/big-data)
* [Uber](https://github.com/orgs/uber/repositories?type=all&q=sort%3Astars+machine-learning) and [blog](https://www.uber.com/blog/houston/data/?uclick_id=b2f43229-f3f4-4bae-bd5d-10a05db2f70c)


# Community

### Newsletters & Curated Reads

* [Ananth Packkildurai's Data Engineering Weeklies](https://substack.com/profile/3520227-ananth-packkildurai)
* [Amplify Partner's Building Data Driven Orgs](https://amplifypartners.com/moderndatateamshub/)
* [Joe Reis Substack](https://joereis.substack.com/)
* [Zach Wilson's DE Handbook](https://github.com/DataExpert-io/data-engineer-handbook/) and [bootcamps](https://bootcamp.techcreator.io/)

### Forums

- [/r/dataengineering](https://www.reddit.com/r/dataengineering/) - Subreddit news, tips, and background on Data Engineering.
- [/r/etl](https://www.reddit.com/r/ETL/) - Subreddit focused on ETL.
* [/r/sql](https://www.reddit.com/r/SQL/) Subreddit focused on SQL
* [/r/apachekafka](https://www.reddit.com/r/apachekafka/) Subreddit focused on Apache Kafka

### Conferences

- [Data Council](https://www.datacouncil.ai/about) - Data Council is the first technical conference that bridges the gap between data scientists, data engineers and data analysts.

### Podcasts

- [Data Engineering Podcast](https://www.dataengineeringpodcast.com/) - discussions on modern data stack and infrastructure.
- [The Data Stack Show](https://datastackshow.com/) - engineers share their experiences around building and maintaining data infrastructure, data products, and partnering with business.

### Books

- [Snowflake Data Engineering](https://www.manning.com/books/snowflake-data-engineering) - A practical introduction to data engineering on the Snowflake cloud data platform.

- [Best Data Science Books](https://www.appliedaicourse.com/blog/data-science-books/) - This blog offers a curated list of top data science books, categorized by topics and learning stages, to aid readers in building foundational knowledge and staying updated with industry trends.

- [Architecting an Apache Iceberg Lakehouse](https://www.manning.com/books/architecting-an-apache-iceberg-lakehouse) - A guide to designing an Apache Iceberg lakehouse from scratch.

### Videos

- [Anthropic Claude for Data Engineering](https://www.ginobaltazar.com/downloads/claude_for_data_engineering.mp4) - You can offload time-intensive, reactive work to Claude Code. That way, you can focus on higher leverage work like data modeling and pipeline design and use Claude as a more contextualized partner for data engineering.

### Trivia

* [MySql founder Monty's blog](http://monty-says.blogspot.com/2020/) 

### Conferences

* [Data Council](https://www.datacouncil.ai/about) Data Council is the first technical conference that bridges the gap between data scientists, data engineers and data analysts.

## Credit

Cheers to [The Data Engineering Ecosystem: An Interactive Map](https://blog.insightdatascience.com/the-data-engineering-ecosystem-an-interactive-map-b682627c2534)

Inspired by the [awesome](https://github.com/sindresorhus/awesome) list. Created by [Insight Data Engineering](https://insightdataengineering.com) fellows.

Nod to [Igor Barinov](https://github.com/igorbarinov/) for inspiration and links. 

### Support Me

If you like my work consider supporting me!

[!["Buy Me A Coffee"](https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png)](https://www.buymeacoffee.com/ginobaltazar)

## License

[![CC0](https://i.creativecommons.org/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/) Feel free to use and share, waiving all copyright and related or neighboring rights to this work. 