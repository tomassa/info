
  - Apache Iceberg - opensource analytical table format for big data analytics (Hive, Spark, Snowflake, Google, Apple..)
- history snapshots, partitioning, geometry datatypes, geoparquet support
  - MinIO - object storage , with the same cluster like API like Amazon S3, stores unstructured data/files, good for AI/ML workflows
  - vector DBs - Milvus code example, optimise by batch processing, or using hw acceleration GPU/TPU/CPU, monitor, optimise search parameteres, cache https://thenewstack.io/how-to-master-vector-databases/
- Snowflake - redo the training with cert
- nighttime - read North Korea paper - MHofer #read
  - Moscow much darker - https://www.businessinsider.com/satellite-photos-expose-faltering-russian-economy-sweden-2025-1
    Wiley access tomassako@gmail.com/p..6!
  - GEE As of June 2024, you do not have an option to use Earth Engine without a cloud project. If you do not link your existing account with a Cloud Project, your GEE account will stop functioning at some point in the future.  Earth Engine remains free for Noncommercial and Research Use. You do not need to setup a billing account or pay if you qualify for this category.
  - GEE project "fastai-226712" registration: Data engineer, Kinit, Can poverty be estimated from space?, regional -Russia
  - RAPIDS 25.04 - cuDF can read parquet footers in parallel, polars GPU engine, cuML and Polars integrated to Colab NBs  https://developer.nvidia.com/blog/rapids-brings-zero-code-change-acceleration-io-performance-gains-and-out-of-core-xgboost/?mkt_tok=MTU2LU9GTi03NDIAAAGav2zkiElYPFxiJRdt3g4xfN_2xV-vxi3qNKBbsTJmLQosDCFZjem9ccwYyHBOzeo_p0CC9HD1ELYyY3i1WvSHr4iznEL1bb08SWfeOFqYWwlVMuGxQ0un
- Apache Spark - build ML pipelines https://www.kdnuggets.com/implementing-machine-learning-pipelines-with-apache-spark
- HF AI Sheets - can have separate prompt for each column, size and speed are higher than in competitors, integrated web search, it needs to drag down columns because at first it generates only 5 sample rows
- vector DB:
	- data split into chunks, chunks converted into vectors, RAG performs search of ANN for most relevant results, optionally blend with BM25 (hybrid search)
	- vectors go into your database alongside **rich metadata** (source, owner, date, region, access level, product, version, precedence)
	- good systems show sources and **refuse** when evidence is weak
- best vector DBs for RAG comparison 2025 https://digitaloneagency.com.au/best-vector-database-for-rag-in-2025-pinecone-vs-weaviate-vs-qdrant-vs-milvus-vs-chroma/