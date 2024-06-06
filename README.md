# Laravel Parameter Tagging Package

This package provides middleware for handling Google Ads `gclid` and UTM query parameters in laravel applications.

## Installation

### Step 1: Install via Composer

You can install the package via Composer:

```bash
composer require fuelviews/laravel-parameter-tagging
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
            \Fuelviews\ParameterTagging\Http\Middleware\HandleGclid::class,
            \Fuelviews\ParameterTagging\Http\Middleware\HandleUtm::class,
        ],
    ];
```