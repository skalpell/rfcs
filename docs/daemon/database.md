# Database & Storage

+ `DBMS` refers to a database management system.
+ `RDBMS` refers to a relational-DBMS.
+ `noSQL` refers to a non-SQL based DBMS, commonly a document or object based DBMS.

The index that is composed must be stored somehow, and efficiently, both in terms of space and in terms of speed.
Furthermore, `DBMS` can't be expected to be the same or even exist across various systems.
The `DBMS` that backs the indexer must therefore be shipped with the project and thus must be light-weight
enough to justify its existence. Just because modern computers have more and more RAM & disk space doesn't mean
that it should be needlessly wasted.

The `DBMS` of choice must therefore be/have:
 - lightweight
 - good indexing performance
 - good data locality
 - provide `API`s for the programming language being used for the indexer.

Some viable candidates are:
 - [x] [sqlite](http://www.sqlite.org/): `RDBMS`
   + Most widely used embedded self-contained `RDBMS`.
   + Can index & use memory.
   + `C/C++` `API`
   + Has 2 different `Rust` `API`s, both under active development:
     - https://github.com/dckc/rust-sqlite3
     - https://github.com/linuxfood/rustsqlite
   + Will be used for now.
 - [ ] [UnQLite](http://unqlite.org/features.html#kv_engine): `noSQL`
   + `C` `API`
   + no `Rust` `API`
   + Can index in memory
   + http://unqlite.org/forum/document-store-performance-indexes

More on `noSQL` databases: http://www.bigdata-madesimple.com/a-deep-dive-into-nosql-a-complete-list-of-nosql-databases/
