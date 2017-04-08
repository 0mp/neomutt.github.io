---
layout: concertina
title: Branch Names
description: List of Branches in the NeoMutt Repo
---

# {{ page.title }}

The [neomutt](https://github.com/neomutt/neomutt) repository has 5 permanent branches.

| Branch                                                               | Description                                                                             |
|:---------------------------------------------------------------------|:----------------------------------------------------------------------------------------|
| [neomutt](https://github.com/neomutt/neomutt/tree/master)           | Main branch -- The Official NeoMutt                                                     |
| [mutt/default](https://github.com/neomutt/neomutt/tree/mutt/default) | A copy of Mutt's [development branch](https://dev.mutt.org/hg/mutt/shortlog/default)    |
| [mutt/stable](https://github.com/neomutt/neomutt/tree/mutt/stable)   | A copy of Mutt's [stable branch](https://dev.mutt.org/hg/mutt/shortlog/stable)          |
| [travis](https://github.com/neomutt/neomutt/tree/travis)             | Code sent to [TravisCI](https://travis-ci.org/neomutt/neomutt) for testing              |
| [coverity](https://github.com/neomutt/neomutt/tree/coverity)         | Code sent to [Coverity](https://scan.coverity.com/projects/neomutt-neomutt) for testing |

In addition, there may be some temporary branches.

| Branch           | Description |
|:-----------------|:------------|
| devel/{NAME}     | New features are created in `devel` branches.  When complete, documented and tested they are merged into the `neomutt` branch. |
| distro/{NAME}    | We keep reference copies of some of the downstream distros' neomutt code.  **Note:** some of these repos are out-of-date.      |
| issue/{NUMBER}   | When fixing a bug, sometimes we create an `issue` branch for the user to test.                                                 |

