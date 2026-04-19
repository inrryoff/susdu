# SUSDU

**SuperUser SUDO for Termux**

SUSDU is a lightweight root shell wrapper for Termux designed as a modern replacement for tools like `tsu`, with support for multiple Android root solutions.

## Features

- Supports:

  - KernelSU

  - MagiskSU

  - SuperSU

  - Generic su


- Interactive root shell

- Run commands as root

- Preserve environment support

- Custom root .bashrc

- Isolated root HOME:

```bash
~/.susdu/
```
- Optional shell selection:

```bash
bash
/system/bin/sh
custom shell path
```
- Automatic fallback:

```bash
su -c
su 0 -c
```
- No `eval`

- Safe command escaping

- MIT licensed

---

## Requirements

- Termux
- Root access (KernelSU, Magisk, etc)
- Bash

---

## Installation

### Termux package (planned)
```bash
pkg install susdu
```

Not yet available.
---

## Manual install

**Clone or copy the script:**
```bash
chmod +x susdu
cp susdu $PREFIX/bin/
```
- Run:
```bash
susdu
```

---

## Usage

**Interactive root shell**
```bash
susdu
```

---

## Run command as root
```bash
susdu apt update
```
or:
```bash
susdu -c "ls -la /data"
```

---

## Use system shell
```bash
susdu -s system getprop ro.product.model
```

---

## Switch user
```bash
susdu -u shell whoami
```

---

## Preserve environment
```bash
susdu -E
```

---

## Options
```bash
-c, --command CMD
-s, --shell SHELL
-u, --user USER
-E, --preserve-env
-b, --bashrc
--no-bashrc
--dbg, --debug
-h, --help
--version
```

---

## Root shell environment

SUSDU automatically creates:
```bash
~/.susdu/.bashrc
```
Includes:

- aliases

- root prompt

- PATH setup

- history config

- sysinfo helper


**Prompt:**
```bash
root@localhost:~#
```

---

## Example aliases
```bash
ll
c
x
croot
ctermux
csystem
cdata
```

---

## Security Notes

SUSDU was designed with:

- No use of `eval`

- Quoted command handling with:

```bash
printf %q
```
- No dangerous automatic user switching

- Fallback handling for older `su` implementations



---

## Compatibility

| Root Solution |	Supported |
|-------|-----|
| KernelSU |	Yes |
| MagiskSU |	Yes |
| SuperSU |	Yes |
| Generic su |	Yes |

---

## License

MIT License

See:
```md
LICENSE
```

---

## Roadmap

- [ ] Official Termux package

- [ ] pkg install susdu

- [ ] Termux repository submission

- [ ] Man page (susdu(1))

- [ ] Test suite



---

## Why SUSDU?

`tsu` has limited compatibility with newer root implementations.

SUSDU was built to provide:

- modern compatibility

- safer shell handling

- better root environment isolation

- a cleaner replacement for tsu



---

## Author

Created by @inrryoff.

If you improve SUSDU, feel free to fork, patch, and contribute.
