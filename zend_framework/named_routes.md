# Named Routes in Zend Framework 1

First of all, Zend Framework SUCKS. Ok, that's out of the way.

With php route definition, you define a route like this:

```php
// duplicate a collection
$route = new \Zend_Controller_Router_Route(
    'collections/duplicate/:user_id/:collection_id',
    [
        'controller' => 'collections',
        'action' => 'duplicate',
    ],
    // regex type constraints
    [
        'user_id' => '\d+',
        'collection_id' => '\d+',
    ]
);
// this is the route name
$router->addRoute('duplicate-collection', $route);
```

Then you can link to that route in the view like so:
```
// in views/collections/duplicate.phtml
<a href="<?= $this->url(['user_id' => 123, 'collection_id' => 456], 'duplicate-collection') ?>">Duplicate Collection</a>
```

You can use an empty array as the first param if there are no defined segments.
