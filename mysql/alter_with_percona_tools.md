# Alter mysql schema with percona tools

Altering a table will lock it until all rows are altered. This can take a while and back up queries in a busy, large table. An alternative is to create a copy of the table, create temporary triggers to keep track of new changes coming in, copy all data over to the new table, swap table names, replay the changes from the triggers, and delete the triggers and old table. This is a lot to do manually!

[Percona Toolkit](https://www.percona.com/software/database-tools/percona-toolkit) handles this for you. just `brew install percona-toolkit` and you get the `pt-online-schema-change` command. `pt-online-schema-chenage --help` for info. You can dry run, chunk the transitition in batches, etc.

Took me a bit to get percona toolkit working on mac. Steps:
1. `brew install percona-toolkit`
1. `brew install plenv` (perl version manager)
2. add to ~/.bashrc: `[[ "$(builtin type -p plenv)" ]] && eval "$(plenv init -)"`
3. source your bashrc
4. `plenv install --list` to see available versions
5. `plenv install {latest version}` (version from --list in previous step)
6. `plev global {latest version}` to use that version as the global perl version
7. `sudo cpan` to start the perl dependency manager shell
8. `install DBI`
9. `install DBD::mysql`

now you should be able to run it, e.g. in dry run mode:
```
pt-online-schema-change --alter "ADD reset_password_hash VARCHAR(32) NULL DEFAULT NULL AFTER status" D=legacy,h=192.168.99.900,u=me,p=something,P=3306,t=users --alter-foreign-keys-method=auto --dry-run
pt-online-schema-change --alter "ADD reset_password_expires_at DATETIME NULL DEFAULT NULL AFTER reset_password_hash" D=legacy,h=192.168.99.900,u=me,p=something,P=3306,t=users --alter-foreign-keys-method=auto --dry-run
```
swap `--dry-run` with `--execute` to run it.
