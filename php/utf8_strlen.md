UTF-8 characters are multibyte so `strlen` will be inaccurate. Use `mb_strlen`:

```
var_dump(mb_strlen("水墨建筑",'UTF-8'), strlen("水墨建筑"));
Output: int(4) int(12)
```
