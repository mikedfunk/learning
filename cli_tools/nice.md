# Nice

Lower the priority of an expensive task to ensure it doesn't hog all cpu on a box.

```bash
nice -n 20 ./do-something.sh
```

> It directly maps to a kernel call of the same name. nice is used to invoke a utility or shell script with a particular priority, thus giving the process more or less CPU time than other processes. A niceness of −20 is the highest priority and 19 is the lowest priority. The default niceness for processes is inherited from its parent process and is usually 0.

https://en.wikipedia.org/wiki/Nice_(Unix)
