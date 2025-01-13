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
    uses: Jubeki/actions/automated-dependency-updates.yml@main
```

```yaml
name: Tests

on:
  push:

jobs:
  update:
    uses: Jubeki/actions/tests.yml@main
```