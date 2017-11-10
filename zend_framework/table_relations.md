# Table Relations

First of all, I **HATE** Zend framework. Good, now that's out of the way. This is for zend framework 1, which is old as dirt.

Given a schema like this:

* users -> has one -> roles
* users.role_id = roles.id

Classes look like this:
```php
<?php
class User extends Zend_Db_Table_Abstract
{
}

class Role extends Zend_Db_Table_Abstract
{
    protected $_referenceMap = [
        'User' => [ // if you get the dependent rowset but do not specify which rule to use, it will get the _first_ defined rule for that table in this referenceMap array
            'columns' => ['id'], // name of the column on the roles table
            'refTableClass' => User::class,
            'refColumns' => ['role_id'], // name of the reference column on the users table
        ],
    ]
}

// now you can get related user:
$userTable = new User();
$user = $userTable->find(123);
/** @var Role $role */
$role = $user->findDependentRowset(Role::class);
```
