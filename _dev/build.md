---
layout: concertina
title: Building NeoMutt
description: How to build NeoMutt from the Source Code
status: wip
---

# {{ page.title }}

## Install Dependencies

See [Distro Pages](/distro.html).

## Obtain the Source

The NeoMutt project is hosted on GitHub, so there are two main options to get
the sources — either as Git repository or GitHub archive file. A repository,
not only for [GitHub users](/dev/newbie-tutorial#github), provides some
benefits over a single release or snapshot archive, e.g. will empower you to
work with the source code and contribute to the project more easily.

### Git <a class="offset" id="git"></a>

Cloning the [main branch](https://github.com/neomutt/neomutt/tree/master) but
also see our [list of branches](/dev/branches).

```
git clone https://github.com/neomutt/neomutt
```

Same as above but pointing to an other branch, e.g. `devel/autosetup`, for
checkout.

```
git clone -b devel/autosetup https://github.com/neomutt/neomutt
```

### GitHub

Latest release
: <https://github.com/neomutt/neomutt/releases/latest>

Select a source package (Tar or ZIP archive) and the checksum file for
download. **Important**, verify the tarball/ZIP archive file to ensure its
integrity, see [Signing Code / Releases](/dev/signing#source-example) for an
example.

Specific branch
: <https://github.com/neomutt/neomutt/archive/devel/autosetup.zip>

Note, archive file verification isn't possible here because this is not
a NeoMutt release archive and thus no checksum file is available. Consider to
use Git instead (as mentioned [above](#git)) to clone the repository and
checkout the specific branch afterwards.

## Autoreconf

Generate the appropriate configuration and build scripts.

```
autoreconf -i
configure.ac:19: installing '.build-aux/compile'
configure.ac:23: installing '.build-aux/config.guess'
configure.ac:23: installing '.build-aux/config.sub'
configure.ac:10: installing '.build-aux/install-sh'
configure.ac:10: installing '.build-aux/missing'
Makefile.am: installing '.build-aux/depcomp'
```

## Configure

List supported options to adapt or fine tune NeoMutt's build.

```
./configure --help
```

### Varied configure options

| Category         | Option/Variable             | Description                                                   |
| :--------------- | :-------------------------- | :------------------------------------------------------------ |
| General          | `--prefix=PREFIX`           | Install architecture-independent files in PREFIX [/usr/local] |
| Curses vs S-Lang | `--with-slang[=DIR]`        | Use [S-Lang][co_slng] instead of *ncurses*                    |
|                  | `--with-curses=DIR`         | Where [ncurses][co_crss] is installed                         |
| Features         | `--enable-notmuch`          | Enable [Notmuch](/feature/notmuch) support                    |
|                  | `--enable-lua`              | Enable [Lua][co_lua] scripting support                        |
|                  | `--enable-gpgme`            | Enable [GPGME][co_gpgme] support                              |
| Header Caching   | `--with-gdbm[=DIR]`         | Use [GDBM][co_gdbm] for the header cache                      |
|                  | `--with-tokyocabinet[=DIR]` | Use [Tokyo Cabinet][co_tcab] for the header cache             |
|                  | `--with-kyotocabinet[=DIR]` | Use [Kyoto Cabinet][co_kcab] for the header cache             |
|                  | `--with-qdbm[=DIR]`         | Use [QDBM][co_qdbm] for the header cache                      |
|                  | `--with-bdb[=DIR]`          | Use [Berkeley DB][co_obdb] for the header cache               |
|                  | `--with-lmdb[=DIR]`         | Use [LMDB][co_lmdb] for the header cache                      |
| Security         | `--with-gss[=PFX]`          | Compile in [GSSAPI][co_gss2] authentication for IMAP          |
|                  | `--with-ssl[=PFX]`          | Enable TLS support using [OpenSSL][co_ossl]                   |
|                  | `--with-gnutls[=PFX]`       | Enable TLS support using [GnuTLS][co_gtls]                    |
|                  | `--with-sasl[=PFX]`         | Use [SASL][co_sasl] network security library                  |
| Debugging        | `--enable-debug`            | Enable debugging support                                      |
|                  | `CFLAGS="-g -O0"`           | Set C compiler flags, e.g. for [GCC][co_dgcc]                 |

## Build

Targets: neomutt, doc, …

```
make
```

## Install

```
make install
```

## Uninstall

```
make uninstall
```


[co_slng]:  <http://www.jedsoft.org/slang/>
[co_crss]:  <https://www.gnu.org/software/ncurses/ncurses.html>
[co_lua]:   <https://www.lua.org/>
[co_gpgme]: <https://www.gnupg.org/related_software/gpgme/>
[co_gdbm]:  <http://www.gnu.org.ua/software/gdbm/gdbm.html>
[co_tcab]:  <http://fallabs.com/tokyocabinet/>
[co_kcab]:  <http://fallabs.com/kyotocabinet/>
[co_qdbm]:  <http://fallabs.com/qdbm/>
[co_lmdb]:  <https://symas.com/lmdb/technical/>
[co_gss2]:  <https://en.wikipedia.org/wiki/Generic_Security_Services_Application_Program_Interface>
[co_ossl]:  <https://www.openssl.org/>
[co_gtls]:  <https://www.gnutls.org/>
[co_sasl]:  <https://en.wikipedia.org/wiki/Simple_Authentication_and_Security_Layer>
[co_obdb]:  <http://www.oracle.com/technetwork/database/database-technologies/berkeleydb/overview/index.html>
[co_dgcc]:  <https://gcc.gnu.org/onlinedocs/gcc/Debugging-Options.html>

