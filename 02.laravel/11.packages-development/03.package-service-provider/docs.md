---
title: 'Package Service Provider'
taxonomy:
    category:
        - docs
---

```
<?php

namespace Vendor\Packagename;

use Illuminate\Support\ServiceProvider;

class MailinglistServiceProvider extends ServiceProvider
{
    /**
     * Bootstrap the application services.
     *
     * @return void
     */
    public function boot()
    {
        echo "Hello Mailinglist";

        $this->loadRoutesFrom(__DIR__.'/routes.php');

        $this->publishes([
            __DIR__.'/config.php' => config_path('XXpackagenameXX.php'),
        ], 'XXpackagenameXX-config');

        $this->loadMigrationsFrom(__DIR__.'/database/migrations');

        $this->publishes([
            __DIR__.'/../database/migrations/' => database_path('migrations')
        ], 'XXpackagenameXX-migrations');

        $this->loadViewsFrom(__DIR__.'/views', 'XXpackagenameXX');

        $this->publishes([
            __DIR__.'/views' => resource_path('views/vendor/XXpackagenameXX'),
        ], 'XXpackagenameXX-views');

        $this->publishes([
            __DIR__.'/path/to/assets' => public_path('vendor/courier'),
        ], 'public');


        if ($this->app->runningInConsole()) {
            $this->commands([
                FooCommand::class,
                BarCommand::class,
            ]);
        }
    }

    /**
     * Register the application services.
     *
     * @return void
     */
    public function register()
    {
        $this->mergeConfigFrom(
            __DIR__.'/config.php', 'XXpackagenameXX'
        );
    }
}

```