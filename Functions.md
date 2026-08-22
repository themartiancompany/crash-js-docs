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

##### `_cd`

Change directory. 

##### `_cat`

Prints the content of a file.

##### `_chown`

Alias for `fs.chownSync`.
For browsers it's just a stub as of now.

##### `_cp`

Alias to `fs.cpSync`.

##### `_cwd`

See
[`_pwd`](
  Functions.md#_pwd)

##### `_dir_exists`

To be used in place of Bash' `-d`,
i.e.:

```bash
if [[ -d "/path/to/directory" ]]; then
  echo \
    "The directory exists."
fi
```

```javascript
if ( _file_exists(
       "/path/to/directory") {
  _echo(
    "The directory exists."
}
```

##### `_dirname`

Alias to `os.path.dirname`.

##### `_echo`

Alias to `console.log`.

##### `_exit`

Alias to `process.exit`.

##### `_file_append`

To be used in place of `>>`.

##### `_file_read`

Alias for
[`_cat`](
  Functions.md#_cat).

##### `_file_write`

To be used in place of `>`.

##### `_ls`

Alias to `fs.readdirSync`.

##### `_pwd`

Prints current directory.

##### `_require`

Asynchronous `require` override;
it allows to load modules both
from `<usr>/lib/node_modules/<module-name>`
and LHS' canonical `<usr>/lib/<module-name>`.

To use this function, the library must be loaded with `import`
rather than with `require` and the module in which
it's used must have `sourceType: "module"` key-value
in its `package.json`.

```javascript
const
  _libcrash_module =
    await import(
      "crash-js");
const
  _libcrash =
    _libcrash_module.default;
const
  _require =
    _libcrash_module._require;
```

##### `_mkdir`

Alias for `fs.mkdirSync`.

##### `_rm`

Alias for `fs.rmSync`.

##### `_run`

Javascript implementation of `_run` from the
[Crash Bash](
  https://github.com/themartiancompany/crash-bash)
library.

##### `_source`

See
  [`require`](
    Functions.md#_require)

##### `_stat`

Return file system info for a file.

##### 

This document is released under the terms of the
GNU Affero General Public License version 3.
