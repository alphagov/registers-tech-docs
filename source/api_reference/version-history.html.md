---
title: Version history
weight: 0
---
# Version history

## Version 1

Version 1 can be accessed using either of these base URLs:

- `https://{register-name}.register.gov.uk/v1/`
- `https://{register-name}.register.gov.uk/`

## Next version
You can use this version of the API to test against backwards incompatable API changes before we release a new version of the API.

Access it using this base URL:

- `https://{register-name}.register.gov.uk/next/`

**WARNING: Do not use this URL in production, as its API may change without warning.**

### Changes since version 1

#### Data model changes
The term "blob" replaces what was previously called an "item" ([RFC-14](https://github.com/openregister/registers-rfcs/blob/master/content/blob-resource/index.md)).

This means that:

- the resource is now accessed at `/blobs/{blob-hash}` instead of `/items/{item-hash}`
- the field `item-hash` is now called `blob-hash` in entry and record responses