# Core Laravel DI Bindings

I found a few times where I wanted to inject a core service like the view renderer or the logger, but the only binding I knew of was the facade accessor. I can't type-hint that and there's no `@Inject` in Laravel's DI container, and it would suck to have to create a service provider for everything that uses one of these facades.

Fortunately there's another way. Laravel has aliases to these core services, all of which resolve to the instance if type-hint injected.

[Aliases here](https://github.com/laravel/framework/blob/5.5/src/Illuminate/Foundation/Application.php#L1109) (Laravel 5.5)

## More Context

I was doing this because I was writing specs with [phpspec](http://phpspec.net). Laravel facades are mockable as mockery mocks but you have to bootstrap the laravel core to bind them, which I wanted to avoid. Also mockery mocks don't play well with phpspec specs. It expects prophecy mocks instead, which it integrates tightly with. Anyway my preferred approach is to skip facades and inject anything you need. It's easy enough to do once you know what class/interface to type hint.
