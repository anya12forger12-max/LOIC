# Low Orbit Ion Cannon (LOIC) — deprecated

LOIC is a C# network stress-testing tool originally published by NewEraCracker and based on Praetox's LOIC project. This repository preserves the upstream source tree as a **historical reference**; it is deprecated, unmaintained, and provided "as is".

> **Upstream status:** [NewEraCracker/LOIC](https://github.com/NewEraCracker/LOIC) is archived and describes itself as *"Deprecated ... USE ON YOUR OWN RISK. WITHOUT ANY EXPRESS OR IMPLIED WARRANTIES."* The last commits in this copy date to 2022. This repository is not affiliated with, or supported by, the upstream authors.

## What LOIC is

The code in [src/](src/) is a Windows Forms application with protocol handlers for TCP, UDP, HTTP, `slowLOIC`, `ReCoil`, and ICMP traffic (see [Protocol.cs](src/Protocol.cs), [HTTPFlooder.cs](src/HTTPFlooder.cs), and [cHLDos.cs](src/cHLDos.cs)). It also contains the historical **HiveMind** (IRC-based) and **OverLord** (web-link-based) remote-control modes, along with an embedded IRC client under [src/IRC/](src/IRC/). Those modes are mentioned here only as context for reading the source; this README does not provide instructions for driving them.

The original project described LOIC as an educational "hacker defense" aid: a way to study how network availability is affected by load. Its own disclaimer and license restrict use to educational purposes and disclaim all warranties.

## Repository contents

| Path | Contents |
|---|---|
| [src/](src/) | C# application, solution (`LOIC.sln`), project files, and IRC client library |
| [Help/](Help/) | Compiled CHM help plus the HTML help source |
| [loic.sh](loic.sh), [loic-net4.0.sh](loic-net4.0.sh) | Legacy Mono install/build/run helpers targeting .NET 4.5 and .NET 4.0 respectively |
| [LICENSE.md](LICENSE.md) | Public-domain dedication with an educational-use restriction and "AS-IS" warranty disclaimer |
| [CONTRIBUTING.md](CONTRIBUTING.md) | Upstream contribution guidance (points to `NewEraCracker/LOIC`) |

## Historical build notes

The solution lives at [src/LOIC.sln](src/LOIC.sln). Upstream documentation required **.NET Framework 3.5 SP1** on Windows; Linux/macOS users were directed to Mono or Wine. The two shell helpers above install Mono packages, build with `xbuild`, and launch the resulting executable — they clone the *upstream* repository, not this copy, and assume 2010-era distributions. Treat them as reference material: they are unmaintained and are unlikely to work unchanged on current toolchains. No prebuilt binaries are included here.

## Responsible use

This project is deprecated security tooling, not a maintained benchmarking or load-testing suite. It can generate significant network traffic and historically has been used without authorization.

- Only experiment on hardware and networks you own, or where you have explicit written authorization and a scoped test plan.
- Do not point it at third-party services, shared networks, or infrastructure you do not control; availability testing without consent can be illegal and disruptive.
- Follow applicable computer-misuse, telecommunications, and local laws. Having the source code is not permission to use it.
- Coordinate any lab work with network owners, isolate it from production, and stop immediately if it affects unintended systems.

## License and credits

Licensing is defined by [LICENSE.md](LICENSE.md): a public-domain dedication coupled with an educational-only condition, no express or implied warranties, and no liability for the licensor for user conduct. Application source is credited to NewEraCracker; the project is based on Praetox's LOIC. This repository is a copy that preserves those notices and adds two later community commits.
