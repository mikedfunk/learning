# Safe file_put_contents

[file_put_contents](http://php.net/manual/en/function.file-put-contents.php) is cool, but if you have multiple processes writing to the same file, they could write at the same time and cause problems. You can get around this by using these flags:
```php
file_put_contents('filename.txt', $myData, FILE_APPEND|LOCK_EX);
```
This will lock the file and queue the file write until the lock is cleared.
