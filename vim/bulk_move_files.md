# Bulk Move Files

Simple way from [vim wikia](http://vim.wikia.com/wiki/Bulk_rename_files_with_Vim):

* ls a directory into vim:
```sh
\ls | vim -
```
* add `mv -i ` in front of each line (visual block)
* assuming there's a formula to the renaming - create and run a macro or function to call on each line to append the renamed file
* `:%!bash` to run each line
