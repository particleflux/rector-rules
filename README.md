# particleflux/rector-rules

A bunch of rules for rectorphp/rector for my personal use.

## Installation

```shell
composer require --dev particleflux/rector-rules
```

## Usage with rector

Just add the desired `SetList` to your `rector.php`.

Example:

```php
<?php
// rector.php
declare(strict_types=1);

use Rector\Core\Configuration\Option;
use Laminas\ServiceManager\Migration\Rector\Set\ValueObject\SetList;
use Symfony\Component\DependencyInjection\Loader\Configurator\ContainerConfigurator;

return static function (ContainerConfigurator $containerConfigurator): void {
    $parameters = $containerConfigurator->parameters();
    $parameters->set(Option::PATHS, [__DIR__ . '/src']);

    $containerConfigurator->import(\particleflux\RectorRules\Rector\Set\ValueObject\SetList::YII_SWIFT_MAILER_TO_SYMFONY_MAILER);
};
```

## Documentation

For a list of available configuration sets, see: [set overview].

[set overview]: ./docs/set_overview.md
