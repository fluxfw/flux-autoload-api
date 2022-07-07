# flux-autoload-api

PHP Autoload Api

## Installation

### Non-Composer

```dockerfile
COPY --from=docker-registry.fluxpublisher.ch/flux-autoload-api:%tag% /flux-autoload-api /%path%/libs/flux-autoload-api
```

or

```dockerfile
RUN (mkdir -p /%path%/libs/flux-autoload-api && cd /%path%/libs/flux-autoload-api && wget -O - https://github.com/flux-eco/flux-autoload-api/releases/download/%tag%/flux-autoload-api-%tag%-build.tar.gz | tar -xz --strip-components=1)
```

or

Download https://github.com/flux-eco/flux-autoload-api/releases/download/%tag%/flux-autoload-api-%tag%-build.tar.gz and extract it to `/%path%/libs/flux-autoload-api`

#### Usage

```php
require_once __DIR__ . "/%path%/libs/flux-autoload-api/autoload.php";
```

### Composer

```json
{
    "repositories": [
        {
            "type": "package",
            "package": {
                "name": "flux/flux-autoload-api",
                "version": "%tag%",
                "dist": {
                    "url": "https://github.com/flux-eco/flux-autoload-api/releases/download/%tag%/flux-autoload-api-%tag%-build.tar.gz",
                    "type": "tar"
                },
                "autoload": {
                    "files": [
                        "autoload.php"
                    ]
                }
            }
        }
    ],
    "require": {
        "flux/flux-autoload-api": "*"
    }
}
```
