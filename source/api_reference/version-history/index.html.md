---
title: Version history
weight: 0
---
# Version history

## `v1`
`v1` is the current version of the API.

You can access v1 of the API using these base URLs:

- `https://{register}.register.gov.uk/v1/`
- `https://{register}.register.gov.uk/`

## `next`
`next` is a preview of the upcoming API before that API becomes stable. You should not use it in production, since the API may change without notice.

The release schedule is:

1. The GOV.UK Registers team releases the `next` API. You can use the `next` version of the API to test against backwards-incompatible changes before `next` becomes the stable API.
2. When the `next` API is stable, it will be renamed to the next version (eg `v2`).
3. After a set amount of time, the previous version of the API is deprecated.

You can access the `next` version of the API using this base URL:

- `https://{register-name}.register.gov.uk/next/`

### Changes

#### Data model changes
The term "blob" replaces the term "item" ([RFC-14](https://github.com/openregister/registers-rfcs/blob/master/content/blob-resource/index.md)).

Registers no longer have "indexes" ([RFC-20](https://github.com/openregister/registers-rfcs/blob/master/content/indexes-removal/index.md)).

These changes mean that:

- you now access the resource at `/blobs/{blob-hash}` instead of `/items/{item-hash}`
- the field `item-hash` is now named `blob-hash`
- the field `index-entry-number` no longer exists (use `entry-number` instead)
- `/entries/{entry-number}` now returns a single object instead of an array of objects
- `/records/{key}` now returns a record object, instead of an object indexed by the entry key
- `/records` now returns an array of record objects, instead of an object indexed by entry key