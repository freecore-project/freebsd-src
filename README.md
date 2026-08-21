# FreeCORE release delta — freebsd-src

[FreeCORE](https://freecore.org) carries the TrueNAS CORE 13.3 system
forward as an independently maintained operating system on FreeBSD.
TrueNAS CORE 13.3 systems upgrade straight to FreeCORE 15.0 in place,
then continue on the project’s update train.

Not affiliated with or endorsed by iXsystems, Inc.

## What this repository is

`0001-freecore-freebsd-src-release-delta.patch` is the reviewed FreeCORE release delta against
[`freebsd/freebsd-src`](https://github.com/freebsd/freebsd-src). The
multi-gigabyte upstream repository is not duplicated here.

| | |
|---|---|
| **Base** | freebsd/freebsd-src @ release/15.1.0-p1 (public tag) |
| **Base commit** | `0f691888dc56a068f74c213bc87b32939b6b354e` |
| **Base resolves publicly** | yes |
| **Licence** | BSD-2-Clause |

## Applying

```sh
git clone https://github.com/freebsd/freebsd-src.git
cd freebsd-src
git checkout 0f691888dc56a068f74c213bc87b32939b6b354e
git apply --index /path/to/0001-freecore-freebsd-src-release-delta.patch
```

## Public history

This is one source-state delta, not an export of the development history.
Private commit subjects, bodies, issue references, dates, ordering, and
intermediate churn are not present. Release tags identify states that were
actually built and validated.

## Contributors represented in this delta

- FreeCORE
- Alexander Motin
- Andrew Walker
- Jakub Klama
- Kris Moore
- Ryan Moeller
- themylogin
- William Grzybowski

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md). Security reports go to
security@freecore.org, not to the issue tracker — see
[SECURITY.md](SECURITY.md).

## Licence and attribution

See [NOTICE](NOTICE) and [TRADEMARKS.md](TRADEMARKS.md). Nothing here is
relicensed; upstream copyright notices and licence texts are preserved.
