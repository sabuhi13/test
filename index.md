# About

Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.

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
