# Nice

nice is a bsd/gnu cli tool to set the cpu priority of a task. It's helpful if you want to set something to run as low or high priority against other cron jobs. Priority ranges from -20 (highest) to 20 (lowest) strangely.

Usage:

```bash
/usr/bin/nice -n 20 /usr/bin/php /my/task.php
man nice
```
