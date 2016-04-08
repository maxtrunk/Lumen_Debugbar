## Lumen Debugbar
[![Packagist License](https://poser.pugx.org/maxtrunk/lumen-debugbar/license.png)](http://choosealicense.com/licenses/mit/)
[![Latest Stable Version](https://poser.pugx.org/maxtrunk/lumen-debugbar/version.png)](https://packagist.org/packages/maxtrunk/lumen-debugbar)
[![Total Downloads](https://poser.pugx.org/maxtrunk/lumen-debugbar/d/total.png)](https://packagist.org/packages/maxtrunk/lumen-debugbar)


This is a package to integrate [PHP Debug Bar](http://phpdebugbar.com/) with Lumen.
It includes a ServiceProvider to register the debugbar and attach it to the output. You can publish assets and configure it through Lumen. Read [the documentation](http://phpdebugbar.com/docs/) for more configuration options.


Note: Use the DebugBar only in development. It can slow the application down (because it has to gather data). So when experiencing slowness, try disabling some of the collectors.

It also provides a Facade interface for easy logging Messages, Exceptions and Time

## Installation

Require this package with composer:

```
composer require maxtrunk/lumen-debugbar --dev
```

After updating composer, add the ServiceProvider to the `bootstrap/app.php`

```
if (env('APP_DEBUG')) {
 $app->register(Barryvdh\Debugbar\LumenServiceProvider::class);
}
```

To change the configuration, copy the file to your config folder and enable it:

```
$app->configure('debugbar');
```

That's it!