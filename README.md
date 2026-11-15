# musl-static-bin

Statically linked Linux x86-64 binaries, built on musl (Alpine 3.21 container on pstor).
Drop-in tools for minimal containers (no libc/deps needed at runtime).

| binary | version | size | notes |
|---|---|---|---|
| `pv` | 1.12.7 | 185K | pipe viewer |
| `spipe` / `spiped` | 1.6.4 | 3.9M ea | stdio-bridge / daemon (tarsnap spiped) |
| `sshfs` | 3.7.3 | 1.4M | needs `fusermount3` + `fuse3` pkg on target; libfuse built `-Dexamples=false -Dutils=false` |
| `ts` | 1522ab0 | 158K | task-spooler, `cpu` (non-GPU/CUDA) build |
| `socat` | 1.8.1.3 | 4.9M | multipurpose relay (OPENSSL baked in); dropped `-lbsd` (musl native) |
| `nc` | 0.7.1 (GNU) | 277K | classic netcat; OpenBSD-current is unportable to musl |
| `scrypt` | Tarsnap git | 146K | manual `-static` final link (libtool drops the flag) |
| `sd` | 1.0.0 | 2.4M | find-and-replace (needs `-static-libgcc`; rust 1.100) |
| `dust` | 1.2 (`du-dust`) | 2.9M | du alternative |
| `rg` (`ripgrep`) | 15.2 | 5.6M | |
| `xh` | 0.26 | 11.8M | HTTP client |
| `miniserve` | 0.35 | 7.4M | static file server |
| `lsd` | 1.2 | 3.6M | ls alternative |
| `b3sum` | 1.8 | 1.2M | BLAKE3 |
| `bat` | 0.25 | 6.5M | cat with wings |
| `btm` (`bottom`) | 0.10 | 5.0M | system monitor |
| `delta` (`git-delta`) | 0.18 | 6.9M | diff pager |
| `fd` (`fd-find`) | 10.2 | 4.1M | find alternative |
| `jless` | 0.9.0 | 3.0M | JSON pager; static X libs via link-group + hidden `.so`s |
| `mdcat` | 2.20 | 38M | markdown renderer (pulls full `pulldown-cmark` + syntax set) |
| `ouch` | 0.8.3 | 6.0M | built **without bzip3** (needs libclang at build time, unloadable on musl) |
| `oxipng` | 10.2 | 1.4M | PNG optimizer |
| `pueue` / `pueued` | 4.0.4 | 7.1M ea | task queue client + daemon |
| `tre` | 1.0 | 2.3M | rust `tree` |
| `tree` | 2.3.2 (C) | 151K | classic tree, C build |
| `trip` (`trippy`) | 0.13 | 9.9M | traceroute TUI |
| `viddy` | 1.3.1 | 8.4M | watch alternative |
| `watchexec` (`watchexec-cli`) | 2.8 | 11.8M | file watcher |
| `zoxide` | 0.10 | 1.2M | smarter cd |
| `choose` | 1.3.7 | 2.7M | cut/awk alternative (needs `-static-libgcc`) |

All stripped.
