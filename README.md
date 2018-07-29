# Power Laravel
Whenever I start a new Laravel Application, I always search online for the best laravel Packages and configure those to my laravel application one by one. This is a tiresome task everytime.
So here I am sharing the way to customize your Laravel Application with a bunch of most popular and most recommended packages which will be helpful for you during and post-develoment.

Just replace the default `composer.json` file from your laravel application with the one from this repository and follow following steps for setting up application.

## How to Setup Packages

#### 1. [arcanedev/log-viewer](https://github.com/ARCANEDEV/LogViewer)
One of the Best Laravel Log viewer with a dedicated Dashboard.

Below are the steps to make this package work

1. In `.env` file add `APP_LOG=daily`
2. In `config/app.php` in the `providers` Array add `Arcanedev\LogViewer\LogViewerServiceProvider::class,`.
3. Run `php artisan log-viewer:publish` on terminal.
4. To use the Web UI just visit `http://example.com/log-viewer`.
5. Configuration settings are in `config/log-viewer.php`.


#### 2. [itsgoingd/clockwork](https://github.com/itsgoingd/clockwork)
A browser extension for debugging, profiling Laravel Application.

Below are the steps to make this package work

1. In `config/app.php` in the `providers` Array add `Clockwork\Support\Laravel\ClockworkServiceProvider::class,`.
2. In `config/app.php` in the `aliases` Array add `'Clockwork' => Clockwork\Support\Laravel\Facade::class,`.
3. Install the [Chrome Extension](https://chrome.google.com/webstore/detail/clockwork/dmggabnehkmmfmdffgajcflpdjlnoemp) or [Firefox Extension](https://addons.mozilla.org/en-US/firefox/addon/clockwork-dev-tools/).
4. To use the Web UI just visit `http://example.com/__clockwork`.

#### 3. [barryvdh/laravel-debugbar](https://github.com/barryvdh/laravel-debugbar)

Debug Bar for Laravel Application which includes many collectors for Laravel

Below are the steps to make this package work

1. In `config/app.php` in the `providers` Array add `Barryvdh\Debugbar\ServiceProvider::class,`.
2. In `config/app.php` in the `aliases` Array add `'Debugbar' => Barryvdh\Debugbar\Facade::class,`.
3. Set `APP_DEBUG=true` in `.env` file.
4. For Configuration just execute `php artisan vendor:publish --provider="Barryvdh\Debugbar\ServiceProvider"`.
5. Visit [this link](https://github.com/barryvdh/laravel-debugbar) for more information.

#### 4. [lubusin/laravel-decomposer](https://github.com/lubusin/laravel-decomposer)

It gives you information about all the installed Packages, their dependencies and Server Environment details.

Below are the steps to make this package work

1. In `config/app.php` in the `providers` Array add `Lubusin\Decomposer\DecomposerServiceProvider::class,`.
2. In `routes/web.php` file add the route for Decomposer `Route::get('decompose','\Lubusin\Decomposer\Controllers\DecomposerController@index');`
3. To use the Web UI just visit `http://example.com/decompose`.

#### 5. [sven/artisan-view](https://github.com/svenluijten/artisan-view)

This Package adds some view related Artisan Commands in your Laravel Project.

Below are the steps to make this package work

1. Add following script In `boot` method of `app/Providers/AppServiceProvider.php`
```
    if ($this->app->environment() == 'local') {
        $this->app->register(\Sven\ArtisanView\ServiceProvider::class);
    }
```
2. Visit [this link](https://github.com/svenluijten/artisan-view) for more information.

# License
open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).

# Courtesy
- [taylorotwell](https://github.com/taylorotwell)
- [arcanedev](https://github.com/arcanedev)
- [itsgoingd](https://github.com/itsgoingd)
- [barryvdh](https://github.com/barryvdh)
- [lubusin](https://github.com/lubusin)
- [svenluijte](https://github.com/svenluijten)

