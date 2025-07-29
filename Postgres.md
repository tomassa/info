
  - pgxman install pg_duckdb pgvector pg_cron pgrouting pgvectorscale pg_quack pg_partman pg_graphql postgis pgsql-http pg_stat_statements parquet_s3_fdw
  - pgai vectorizer tutorial - syncs embeddings, only data(title, text) insert is needed : https://github.com/timescale/pgai
  - pgvectorscale with pgvector - costeffective storage and vector search (better than Pinecone) https://github.com/timescale/pgvectorscale
  - document db from Microsoft - pg_documentdb_core, pg_documentdb_api + FerretDB which uses the same commands, drivers and tools as MongoDB
  - debugging - inheritance dan table oid https://www.cybertec-postgresql.com/en/debugging-postgresql-more-easily/
  - more than 1M vectors -> sharding pgvector with pgdog https://pgdog.dev/blog/sharding-pgvector
  - try postgres in matlab, export and import data for automated prediction for all models #try
  - try postgREST #try
  - try Azure Postgre adds DiskANN with up to 16000 dimensions vectors (compared to 2000 in pgvector) + adding GraphRAG, check https://techcommunity.microsoft.com/blog/adforpostgresql/new-generative-ai-features-in-azure-database-for-postgresql/4414858 #try
  - try for RDS and Bedrock - AWS project idea generator https://dev.to/aws-builders/how-i-built-an-aws-project-idea-generator-using-ai-oif #try
  - cheatsheet https://gist.github.com/Kartones/dd3ff5ec5ea238d4c546
  - OpenAI - "ORM can easily lead to inefficient queries and should be used cautiously"  https://www.pixelstech.net/article/1747708863-openai%3a-scaling-postgresql-to-the-next-level
    - suggest optimizing PostgreSQL’s default parameters, noting that the current default values are overly conservative.. using pgbouncer as connection pooler
    - managed postgresql on Azure - today's toptier HW allows using single PostgreSQL cluster—without sharding or partitioning—to serve their entire business - millions QPS - one primary for writes, then dozens of replicas for reads - “distributed databases are a false need”
  - try pigsty.io and with jupyter https://pigsty.io/docs/pro/jupyter/ #try
- when migrating huge table to partitioned table, prewarm new one, use foreign data wrapper to read from other host and reduce IOPS, script the tasks, monitor system, dont create many empty future partitions
- Multigress - Vitess for Postgres (sharding, connection pooling, query routing, resiliency and failover) https://supabase.com/blog/multigres-vitess-for-postgres
- partitioning, compression, archiving https://dataegret.com/2025/05/data-archiving-and-retention-in-postgresql-best-practices-for-large-datasets/
- Rocketadmin - free tool for admin to navigate many databases, with AI querying support
- query large graph db with sql and GraphBLAS and LAGraph(algorithm) libraries matrix algebra (optimally requires  PG18, however could run on lower PGs) https://onesparse.com/blog/2025/07/01/billions-of-edges-per-second-with-postgres.html 
	- create the next-generation of data-rich AI and ML applications
- listen/notify before commit causes global db lock!
- ParadeDB is an Elasticsearch alternative built as Postgres extension for PG14+
- book https://www.amazon.com/Mastering-PostgreSQL-deployment-optimization-strategies/dp/183620597X#averageCustomerReviewsAnchor
- data storage options 
	1. row based (heap) - best for OLTP, big sizes of tables however option to index them and fastest querying of specific rows
	2. column based - OLAP - much smaller tables, can be indexed, the downside is that a column store is really bad at OLTP operations such as UPDATE, DELETE and so on, however, if you are running an (ideally) append-only analytical workload you are fine, e.g. citus extension
	3. csv - similar size to row based tables, can be compressed
	4. parquet - smallest size, long term storage (polars python package or pg_duckdb(has also Iceberg extension, cloud storages integration))
- import OSM dump to PG https://www.cybertec-postgresql.com/en/openstreetmap-service-by-cybertec/ #try
- extension postgis_sfcgal - full 3D geometry with exact computations, applications in smart city urban planning, BIM, 3D geology
- starting PG16+ use "EXPLAIN (GENERIC_PLAN)" for execution plan of a parameterized statement
- atlas - database schema-as-code at any scale atlasgo.io #paid