# Whitelist

only include array items where the key is in the whitelist

```php
<?php
$whitelist = ['key1', 'key2'];
$filterme = ['key1' => 1, 'skipme' => 2];
$filtered = array_filter(array_intersect_key($filterme, array_flip($whitelist)));
```
