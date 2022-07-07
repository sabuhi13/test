# Installation

You can install the package via composer:

```bash
composer require saboohy/conductor
```

# Usage

```php
<?php

use Saboohy\Conductor\{
    Collection,
    Router
};
use App\Controllers\UserController; // for testing

$app = new Collection();

$app->alias('admin', '/api/admin');

$app->prefix('@admin', function($route) {
    $route->controller(UserController::class, function($user) {
        $user->subPrefix('/user');
        $user->get('/', 'index');
        $user->post('/', 'create');
        $user->get('/{num}', 'read');
        $user->put('/{num}', 'update');
        $user->delete('/{num}', 'delete');
    });
});

Router::run($app->collections());
```
