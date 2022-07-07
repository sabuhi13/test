## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/sabuhi13/test/edit/gh-pages/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```php
<?php

use Saboohy\Conductor\Collection;
use Saboohy\Conductor\Router;
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

For more details see [Basic writing and formatting syntax](https://docs.github.com/en/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/sabuhi13/test/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
