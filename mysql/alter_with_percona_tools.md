# Alter mysql schema with percona tools

Altering a table will lock it until all rows are altered. This can take a while and back up queries in a busy, large table. An alternative is to create a copy of the table, create temporary triggers to keep track of new changes coming in, copy all data over to the new table, swap table names, replay the changes from the triggers, and delete the triggers and old table. This is a lot to do manually!

[Percona Toolkit](https://www.percona.com/software/database-tools/percona-toolkit) handles this for you. just `brew install percona-toolkit` and you get the `pt-online-schema-change` command. `pt-online-schema-chenage --help` for info. You can dry run, chunk the transitition in batches, etc.
