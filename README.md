> Apache Cassandra Orientations

Module-1 Cassandra Core [basics]

- difference in relation vs apache cassandra database
- cassandra tables
- CQL fundamentals
- understand partitions, primarykeys, clustering columns in cassandra tables
- replications and consistency concepts

> ## 1. relation vs apache cassandra database

> Relational

1. sample relational methodology
2. Data-Model-Application i.e we think about model first and then build application around it.
3. Entities are the driving factor
4. Primary keys is used for uniqness of tupple
5. often single point of failure
6. ACID compliant
7. joins and indexes
8. referential integrity is enforced

> Cassandra

1. Cassandra modelling methodology
2. Application-Model-Data i.e we think about application needs when building the models
3. Queries are the driving factor
4. Primary keys use case is much more i.e performance on large scale
5. distributed architecture
6. CAP theorem[consistency-availability-partition tolerance]
7. denormalization
8. referential integrity is not enforced

> Modelling approaches

Relational - data->model->application
Cassandra- application->modle->data

> ## Imp Notes

- Casssandra does not comply to ACID transactions
- Cassandra is by default an AP system i.e availablity and partition tolerance is accepted at the cost of consistency.
- however cassandra can make the DB more consistent by sacrificing availablity known as TUNABLE consistency which is adjusted by configuring the number of nodes performing read/write request on the DB

> Cassandra terminology

1. data model

- is an abstract model to organize elements/parts of data i.e schema.
- for cassandra data model depends upon the queries we want to perform.

2. keyspace

- the outermost logical container of cassandra tables
- it stores replications and tables i.e its a container for replication

3. table

- table are contained within the keyspace
- table is a combination of rows and columns
- cassandra stores data in partitions
- partitions is row or rows of data stored on a node in the partition strategy.
- each row in partition consist of key: value pairs
- cassandra retrieves and stores data on basis of partition.

4. primary key

- guarentees uniqness of the data
- it defines placement of the record in the cluster, for easy access from the data
- partition key is the first part of the primary key, it tells where the data is stored in the cluster and which node it will be stored

5. columns

- for each partitions their are rows and columns, columns are stored locally and reffered to as cell

6. row

- row is contained inside partition
- their can be more rows on 1 partition

7. clustering column

- define the ordering of data withing a given partition.
- the default sorting is in ascending order i.e [FIFO] queue based

> ## CQL cassandra query language is a nosql language aka not only sql

1. building blocks - keyspaces, tables, primary keys
2. basic cql commands- SELECT, TRUNCATE, ALTER TABLE, SOURCE

> Keyspace
