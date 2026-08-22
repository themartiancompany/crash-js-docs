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

##### `_argv`

Returns `process.argv`.

##### `_argv_get`

Returns either a `process.argv`
processed through `yargs`
or one by `_argv_url_get`.

##### `_argv_url_get`

Returns a `process.argv` array obtained
from the URL the browser is currently at.

##### `_cd`

Change directory. 

##### `_cat`

Prints the content of a file.

##### `_chown`

Alias for `fs.chownSync`.
For browsers it's just a stub as of now.

##### `_cmdline_check`

Returns true if the file which contains it
is named same as the argument.
In programs it's currently needed to tell
Node.js or the browser environment how
to parse command-line options.

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

##### `_fs_worker_start

In order for file system operations
to work in browser environments
this function needs to be run
in a program before running
the first read/write operation
in the program and it starts
the Web Worker which performs
OPFS synchronous operations.

```javascript
const
  _worker =
    await _fs_worker_start(
      "fs-worker.js");
```

#### `_get_date_human`

Same as in Crash Bash.

#### `_get_lib`

See
[`_lib_get`](
  Functions.md#_lib_get).

#### `_get_usr`

See
[`_usr_get`](
  Functions.md#_usr_get).

##### `_globals`

Same as `_globals` in Crash Bash.

##### `_global_get`

Returns `global` on Node.js and
`window` in browsers.

##### `_homedir_get`

Returns home directory location
path for the given platform.

##### `_json_read`

To read JSON files into a variable.

##### `_lib_get`

Return the location of the system
libraries directory (i.e. `<usr>/lib`);
the value is obtained through
`ldconfig` so it seamlessly
works cross-platform.

##### `_ls`

Alias to `fs.readdirSync`.

##### `_mkdir`

Alias for `fs.mkdirSync`.

##### `_mktemp`

Javascript implementation of the
`mktemp` command.

##### `_msg_error`

Same as in Crash Bash.

##### `_msg_info`

Same as in Crash Bash.

##### `_os_tmpdir`

##### `_path_join`

Join paths.

##### `_pwd`

Prints current directory.

##### `_range`

Equivalent to `range` in Python.

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

##### `_rm`

Alias for `fs.rmSync`.

##### `_run`

Javascript implementation of `_run` from the
[Crash Bash](
  https://github.com/themartiancompany/crash-bash)
library, so a function which allows to call
functions, spawn or run external processes
or programs synchronously or asynchronously,
with or without a timeout.

##### `_seq`

Equivalent to `seq` in Bash.

##### `_sleep`

Equivalent to `sleep` in Bash.

##### `_source`

See
  [`require`](
    Functions.md#_require)

##### `_spawn`

Synchronous spawn.

##### `_spawn`

Synchronous spawn.

##### `_stat`

Return file system info for a file.

##### `_to_bash_ass_array`

Converts an object into a
Bash associative array.
Clearly its compatible only with objects
with maximum depth one.

##### `_usr_get`

Return the location of the user
tree directory (i.e. `<usr>`).


##### `_yargv_get`

Returns a Yargs digested `process.argv`.

This document is released under the terms of the
GNU Affero General Public License version 3.
