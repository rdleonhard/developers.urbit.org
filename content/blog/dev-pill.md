+++
title = "A Developer Pill"
date = "2022-11-15"
description = "Announcing a new tool for developers."
[extra]
author = "N E Davis"
ship = "~lagrev-nocfep"
image = "https://media.urbit.org/site/posts/essays/blog-dev-pill.png"
+++

![](https://media.urbit.org/site/posts/essays/blog-dev-pill.png)

#  A Developer Pill

A [pill](https://developers.urbit.org/reference/glossary/pill) is a bootstrap sequence to launch an Urbit ship for the first time.  For most of Urbit's history, developers and users have typically used the supplied standard pill for booting their ships.  Core developers would produce custom pills as a matter of testing changes in Arvo, but otherwise alternative pills were mostly ignored.

- [**The Developer Pill**]()

Today the Urbit Foundation unveils a new developer-oriented pill, which contains tools out-of-the-box to ease development and encourage best practices.

##  Contents

The current pill contains the desks:

- `%argo` from `~dister-dozzod-middev`
- `%base` from `~mister-dister-dozzod-dozzod`
- `%citadel` from `~dister-dozzod-middev`
- `%cliff` from `~paldev`
- `%docs` from `~pocwet`
- `%garden` from `~mister-dister-dozzod-dozzod`
- `%webterm` from `~mister-dister-dozzod-dozzod`

##  Usage

To use the pill, boot your developer ship with the `-B` option and the current pill.  (We will timestamp developer pills and maintain a public changelog.)

```hoon
urbit -B dev-20221111.pill
```

When serving with web pages, we also recommend considering using tooling from [`~paldev`'s Suite (namely Rudder)](https://github.com/Fang-/suite/blob/master/lib/rudder.hoon) and [Quartus’ Schooner](https://github.com/dalten-collective/schooner/blob/master/lib/schooner.hoon).

We expect the developer pill to evolve over time as new apps come out and newer libraries and practices supersede others.

##  Build Details

This brass pill was built using [a slightly modified pill builder](https://github.com/urbit/urbit/pull/6031) (to include `/dia` and `/doc` folders in `/gen/brass.pill`).  A few minor changes are made to the standard desks:

- `%argo` has `%language-server` activated.
- `%citadel` has `%citadel-cli` activated.

The pill was built as a brass pill, e.g.:

```hoon {% copy=true %}
.brass/pill +brass %argo %base %citadel %cliff %docs %garden %webterm
```