# Daemon

The daemon is responsible for all the interactions with the operating system, file system
and should be able to work almost entierly standalone.

The data that the daemon processes is persistently stored in some form of [database](daemon/database.md).
The database is not to be accessed by anything other than the daemon directly.

The main part of the daemon deals with [indexing](daemon/indexer.md) - which mainly involves indexing the file system.

This part is ment to be implemented entierly in the rust systems programming language.
For now, to get the application to proof of concept level, some parts might be written in `C` or `C++`.
