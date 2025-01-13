# My Actions

## Requirements

Make sure you have `larastan/larastan` installed:

```bash
composer require larastan/larastan --dev
```

with the following default config in `phpstan.neon`:

```yaml
includes:
    - vendor/larastan/larastan/extension.neon
    - vendor/nesbot/carbon/extension.neon

parameters:

    paths:
        - app/

    # Level 10 is the highest level
    level: max

#    ignoreErrors:
#        - '#PHPDoc tag @var#'
#
#    excludePaths:
#        - ./*/*/FileToBeExcluded.php
```

Furhter more you should have the following in your `phpunit.xml` not commented out:

```xml
<env name="DB_CONNECTION" value="sqlite"/>
<env name="DB_DATABASE" value=":memory:"/>
```

## How to use

### Automated Dependency Updates

```yaml
name: Automated Dependency Updates

on:
  schedule:
    - cron: '0 7 * * 1' # every Monday at 7am

jobs:
  update:
    uses: Jubeki/actions/.github/workflows/automated-dependency-updates.yml@main
    with:
      php: '8.3'
      node: '22'
```

### Tests

```yaml
name: Tests

on:
  push:

jobs:
  tests:
    uses: Jubeki/actions/.github/workflows/tests.yml@main
    with:
      php: '8.3'
      node: '22'
```