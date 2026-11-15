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

All stripped.
