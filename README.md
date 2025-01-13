# My Actions

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