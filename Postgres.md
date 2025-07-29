EXTENSIONS

- pg_strom - gpu - need from source https://heterodb.github.io/pg-strom/install/
- pgTAP - unit testing
- graphs 
	1. age - need to install from source https://github.com/apache/age, docker 
	2. onesparse - query large graph db with sql and GraphBLAS and LAGraph(algorithm) libraries matrix algebra (optimally requires PG18, however could run on lower PGs), docker demo https://onesparse.com/docker.html
	3. pgrouting - spatial routing and network analysis for postgis, osm2pgrouting is cli tool to import osm data to routing db
	4. sql/pgq [link](https://www.enterprisedb.com/blog/representing-graphs-postgresql-sqlpgq#:~:text=SQL%2FPGQ%20provides%20a%20neat,working%20with%20graphs%20in%20Postgres)
- Timescaledb (need custom installation https://docs.timescale.com/self-hosted/latest/install/installation-linux/) docker
- pg_vector 
- pgvectorscale with pgvector - costeffective storage and vector search (better than Pinecone) https://github.com/timescale/pgvectorscale
- pg_stats 
- fdw
- pgcrypto
- pg_partman - manage partitioning
- ParadeDB is an Elasticsearch alternative built as Postgres extension for PG14+
- pg_duckdb - parquet, columnar, Iceberg extension, cloud storage integration 
- pg_cron - schedule jobs 
- postgis - spatial db
- postgis_sfcgal - full 3D geometry with exact computations, applications in smart city urban planning, BIM, 3D geology
- pgai (need to install from source :( https://github.com/timescale/pgai/blob/main/docs/install_from_source.md) docker
- hydra_columnar - columnar storage extension
- http - call a webservice
- pg_incremental - for append-only streams of data, such as IoT / time series / event data workloads
- pg_parquet - reads and writes parquet files to local disk or to S3 natively from Postgre
- pg_documentdb_Core, pg_documentdb_api - maintained by MS, with frontend FerretDB is equiv to mongodb, uses the same commands, drivers and tools as MongoDB
- OrioleDB - storage extension, replacement for PG's heaps, better garbage collection, faster reads, lower cpu and mem, takes advantage of modern hardware and cloud infrastructure
- pgdog - load balancer that evenly distributes transactions between replicated dbs
- pgNow - GUI diagnostic tool 
- pgMustard- free trial, visualizing explain plan and suggests improvements
- Vectorchord - high performance big scale vector search https://blog.vectorchord.ai/vector-search-at-10000-qps-in-postgresql-with-vectorchord
- Monitoring : pgwatch, pg_activity
- Postgrest - restful API from PG, works well with Nginx
- pg_graphql - adds GraphQL support to your PostgreSQL database
- pgai - https://github.com/timescale/pgai
		- Python library, transforms PG into production-ready RAG
		- automaticall create and sync embeddings, search with pgvectorscale
		- support for embeddings - Ollama, HF, OpenAI etc

NOTES

  - debugging - inheritance and table oid https://www.cybertec-postgresql.com/en/debugging-postgresql-more-easily/
  - more than 1M vectors -> sharding pgvector with pgdog https://pgdog.dev/blog/sharding-pgvector
  - try postgres in matlab, export and import data for automated prediction for all models #try
  - try Azure Postgre adds DiskANN with up to 16000 dimensions vectors (compared to 2000 in pgvector) + adding GraphRAG, check https://techcommunity.microsoft.com/blog/adforpostgresql/new-generative-ai-features-in-azure-database-for-postgresql/4414858 #try
  - try for RDS and Bedrock - AWS project idea generator https://dev.to/aws-builders/how-i-built-an-aws-project-idea-generator-using-ai-oif #try
  - cheatsheet https://gist.github.com/Kartones/dd3ff5ec5ea238d4c546
  - OpenAI - "ORM can easily lead to inefficient queries and should be used cautiously"  https://www.pixelstech.net/article/1747708863-openai%3a-scaling-postgresql-to-the-next-level
    - suggest optimizing PostgreSQL’s default parameters, noting that the current default values are overly conservative.. using pgbouncer as connection pooler
    - managed postgresql on Azure - today's toptier HW allows using single PostgreSQL cluster—without sharding or partitioning - to serve their entire business - millions QPS - one primary for writes, then dozens of replicas for reads - “distributed databases are a false need”
  - try pigsty.io and with jupyter https://pigsty.io/docs/pro/jupyter/ #try
	  - allows installation of roughly 400 extensions in conf file https://pigsty.io/ext/usage/install/ #try
- when migrating huge table to partitioned table, prewarm new one, use foreign data wrapper to read from other host and reduce IOPS, script the tasks, monitor system, do not create many empty future partitions
- Multigress - Vitess for Postgres (sharding, connection pooling, query routing, resiliency and failover) https://supabase.com/blog/multigres-vitess-for-postgres
- partitioning, compression, archiving https://dataegret.com/2025/05/data-archiving-and-retention-in-postgresql-best-practices-for-large-datasets/
- Rocketadmin - free tool for admin to navigate many databases, with AI querying support
- listen/notify before commit causes global db lock!
- book https://www.amazon.com/Mastering-PostgreSQL-deployment-optimization-strategies/dp/183620597X#averageCustomerReviewsAnchor
- data storage options 
	1. row based (heap) - best for OLTP, big sizes of tables however option to index them and fastest querying of specific rows
	2. column based - OLAP - much smaller tables, can be indexed, the downside is that a column store is really bad at OLTP operations such as UPDATE, DELETE and so on, however, if you are running an (ideally) append-only analytical workload you are fine, e.g. citus extension
	3. csv - similar size to row based tables, can be compressed
	4. parquet - smallest size, long term storage (polars python package or pg_duckdb)
- import OSM dump to PG https://www.cybertec-postgresql.com/en/openstreetmap-service-by-cybertec/ #try
- starting PG16+ use "EXPLAIN (GENERIC_PLAN)" for execution plan of a parameterized statement
- atlas - database schema-as-code at any scale atlasgo.io #paid