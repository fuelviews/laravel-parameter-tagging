# Laravel Parameter Tagging Package

This package provides middleware for handling Google Ads `gclid` and UTM query parameters in Laravel applications. The middleware sets these parameters as cookies and stores them in the session.

## Installation

### Step 1: Install via Composer

You can install the package via Composer:

```bash
composer require fuelviews/laravel-middleware
```

#### Step 2: Register Middleware

Register middleware in your app/Http/Kernel.php file.

```php
    // GTM tracking...
    protected $middleware = [
        \Illuminate\Session\Middleware\StartSession::class,
        \Spatie\GoogleTagManager\GoogleTagManagerMiddleware::class,
    ];

    // Query params tracking...
    protected $middlewareGroups = [
        'web' => [
            \Fuelviews\LaravelMiddleware\Middleware\HandleGclid::class,
            \Fuelviews\LaravelMiddleware\Middleware\HandleUtm::class,
        ],
    ];
```