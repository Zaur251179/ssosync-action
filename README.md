# ssosync-action

This action automatically synchronize your SSO users and groups, eliminating the need for manual creation and upkeep.

[![LICENSE](https://img.shields.io/github/license/DNXLabs/ssosync-action)](https://github.com/DNXLabs/ssosync-action/blob/master/LICENSE)

## Example usage

```yml
name: ssosync cron

on:
  schedule:
    # * is a special character in YAML so you have to quote this string
    - cron:  '0 * * * *'

jobs:
  synchronize:

    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v2
    - name: Synchronize SSO users and groups
      uses: DNXLabs/ssosync-action@v1
      env:
        SSOSYNC_SCIM_ACCESS_TOKEN: ${{secrets.SSOSYNC_SCIM_ACCESS_TOKEN}}
        SSOSYNC_SCIM_ENDPOINT: ${{secrets.SSOSYNC_SCIM_ENDPOINT}}
        SSOSYNC_GOOGLE_ADMIN: ${{secrets.SSOSYNC_GOOGLE_ADMIN}}
```

## Authors

Module managed by [DNX Solutions](https://github.com/DNXLabs).

## License

Apache 2 Licensed. See [LICENSE](https://github.com/DNXLabs/ssosync-action/blob/master/LICENSE) for full details.