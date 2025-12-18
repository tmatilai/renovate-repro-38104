# 38104

A minimal reproduction repository for Renovate discussion [38104](https://github.com/renovatebot/renovate/discussions/38104).

Can be tested by running renovate with `--allowed-commands '^touch dummy\.txt$'`.

## Current behavior

`postUpgradeTasks.workingDirTemplate` does not work correcrtly with relative paths, as the paths are relative to the directory where Renovate is executed, not the repository root.

If the relative path doesn't exist on the Renovate execution directory, Renovate fails with the error `spawn /bin/sh ENOENT`.

## Expected behavior

Relative paths should resolve relative to the repository root rather than the Renovate execution directory.
