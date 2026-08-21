# Contributing

FreeCORE is developed in a private tracker and published here as curated
release cuts. That shapes how contribution works in ways that are unusual enough
to be worth reading before you spend time on a patch.

## Reporting a bug

**All issues go to one tracker: https://codeberg.org/freecore/freecore**

Issues are disabled on the individual code repositories on purpose. The split
between `middleware`, `webui`, `build` and the rest is inherited from upstream's
architecture — you should not have to know which one owns your bug in order to
report it. One inbox, we do the routing.

Say which version you are on, what you did, what happened, and what you
expected. If it reproduces on stock TrueNAS CORE 13.3 too, mention that: it
means the bug is upstream's, and that changes where the fix belongs.

Security problems do **not** go in the tracker — see [SECURITY.md](SECURITY.md).

## Sending a fix

Pull requests go to the **code repository** that contains the fix, not to the
tracker. Reference the issue across repositories:

```
Fixes freecore/freecore#42
```

### How your PR lands, and why it will say "closed" and not "merged"

This is the part that surprises people, so it is worth being direct about it.

The `main` branch you forked is **regenerated from scratch at every release**.
It is a curated publication of development that happens elsewhere, not a branch
that accumulates merges. A merge commit made into it would be destroyed by the
next release cut.

So a pull request is reviewed here, and then applied to the development tree,
where it goes through the project's normal verification. It reappears in the
next release. At that point the PR is closed with a pointer to the release tag
that carries it.

**Closed does not mean rejected.** If your PR is being declined you will be told
so in words.

### Your authorship is preserved

Release commits group work thematically, which would otherwise bury the fact
that someone else wrote part of it. In full-source repositories, a release
commit that contains outside work carries generated `Co-Authored-By` credit. In
the large repositories published as one source-state delta, contributors are
listed once in the accompanying README without mapping a person to a private
commit or individual change. Upstream and iXsystems authors are credited by the
same mechanisms.

If a release ships your work without crediting you, that is a bug — report it.

## What lands easily

- **Bug reports** with a reproduction.
- **Small, self-contained fixes** with a clear cause.
- **Portability and correctness fixes** for FreeBSD 15 and Python 3.11.

Keep changes small and reviewable. A large refactor is unlikely to land no
matter how good it is — not because of its quality, but because the review and
verification burden falls on one maintainer.

## Ground rules the project holds itself to

These are the rules FreeCORE development follows, and a change is judged
against them:

1. **TrueNAS CORE 13.3 is the reference.** A behaviour is only a regression if
   13.3 did it, FreeCORE broke it, and you can name the change that broke it.
2. **Reproduce it.** A static analysis result or a log line is not an
   observation. Bugs are confirmed on a running system.
3. **New features are opt-in.** Services ship disabled; the user turns them on.
4. **Root cause, not symptom.** Fixes go in at the layer that owns the problem.

## Not accepted

- Rebranding changes. The trademark position is deliberate — see
  [TRADEMARKS.md](TRADEMARKS.md), including the upstream-derived names that are
  kept intentionally as attribution.
- Removal of upstream copyright notices or licence texts.
- Security vulnerabilities as public issues — see [SECURITY.md](SECURITY.md).
