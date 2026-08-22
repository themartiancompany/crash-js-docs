[comment]: <> (SPDX-License-Identifier: AGPL-3.0)

[comment]: <> (----------------------------------------------------)
[comment]: <> (Copyright © 2024, 2025, 2026)
[comment]: <> (            Pellegrino Prevete)
[comment]: <> (All rights reserved)
[comment]: <> (----------------------------------------------------)

[comment]: <> (This program is free software: you can redistribute)
[comment]: <> (it and/or modify it under the terms of the)
[comment]: <> (GNU Affero General Public License as published)
[comment]: <> (by the Free Software Foundation, either version)
[comment]: <> (3 of the License.)

[comment]: <> (This program is distributed in the hope that it)
[comment]: <> (will be useful, but WITHOUT ANY WARRANTY;)
[comment]: <> (without even the implied warranty of)
[comment]: <> (MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.)
[comment]: <> (See the GNU Affero General Public License)
[comment]: <> (for more details.)

### Crash Javascript documentation

The Crash Javascript library facilitates
writing Javascript modules which do resemble
[Crash Bash](
  https://github.com/themartiancompany/crash-bash)
programs and are seamlessly integrated with
every platform on which it's possible to
run Javascript (web browsers or Node.js).

In order to provide its functions, the library
uses browser-compatible implementations of
main Node.js modules.

File system (`fs` module) and path (`os.path` module)
functions are provided by
[The Martian Company file system module](
  https://github.com/themartiancompany/tmcfs)
(`tmcfs`) module, which overrides `node:fs`.

Functions from the `node:process`
module are provided by the
[`process-browserify`](
  https://github.com/themartiancompany/process-browserify)
module.

All functions which are not named after
common GNU Coreutils and Bash commands are 
to be intended implementations of functions
contained in the Crash Bash library.

- [Functions](
    Functions.md)

The documentation is released under the terms of the
GNU Affero General Public License version 3.
