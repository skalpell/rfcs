# Indexer

The daemons main task is to index relevant parts of the file system for files and directories of interest.

This is done in these parts:

## File system watcher

The indexer has to run a file system watcher that is notified on changes to the file system in specified areas.
When this happens, the indexer starts a task for each notification to do needed work.

The needed work can for example be:

+ Removing an entry from the [database](database.md)
+ Fetching information about the file or directory by for example checking the [metadata](metadata.md) of the file.
  and then storing it to the database.

It is important that the watcher be able to cancel long running metadata-fetching operations in case
for example the user adds a directory and decides to remove the same directory before the fetching has concluded.

## Manual indexing

When the application is installed on a new system, no new changes will be fired for what has already happened in the past.
So the application will simply do an indexing of the watched folders from scratch and do the metadata-running tasks for everything.
This can also happen when the user requests a refresh manually.

## Concurrency & Paralellism

Paralellism should be used as much as possible here with worker threads.

When a fs-notification is received, a task can be spawned that handles that notification
and then returns the relevant information so that the database-modification can be done in one thread if need be.
