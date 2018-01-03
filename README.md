Laravel Ajax Only Middleware
============

Description
-----------
A small middleware that prevents routes being access unless via AJAX methods.

Install
-------
```
composer require "penance316/laravel-ajax-only-middleware"
```

Register the middleware with you app in  `app/Http/Kernal.php`
 
```
  /**
    * The application's route middleware.
    *
    * @var array
    */
    protected $routeMiddleware = [
        //... existing code
        'ajax' => Penance316\Middleware\AjaxOnly::class,
    ];
}
```

Attach middleware to any routes you want to be accessible only via AJAX requests
```
// File: routes.php
get('someitem/{id}', ['middleware' => 'ajax', 'uses' => 'SomeController@show']);
```