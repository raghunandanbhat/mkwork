# mkwork

A minimal shell script to manage `git worktrees` and build directories for MariaDB Server development.

This helps you quickly create and clean up `git worktrees` and corresponding build directories based on JIRA issue numbers and server versions.

---

## Usage

```bash
mkwork [options]
```
### Options
- `-s`, `--seed <jira>`
JIRA issue number (e.g., MDEV-12345)

- `-v`, `--version <version>`
Server version to base the worktree on (e.g., 11.4)

- `-i`, `--in-worktree`
Place the build directory inside the worktree. Default is outside.

- `-d`, `--delete <jira>`
Delete a worktree and its associated build directory.
Example: MDEV-12345-11.4

- `-h`, `--help`
Show usage help

- This script assumes you have a local clone of the MariaDB server repository and that you've set the correct path in the script under `PROJECT_REPO`.

## Examples
- Create a worktree and build directory:
```bash
./mkwork -s MDEV-12345 -v 11.4
```
- Create with build directory inside the worktree:
```bash
./mkwork -s MDEV-12345 -v 11.4 -i
```
- Delete a worktree and build directory:
```bash
./mkwork -d MDEV-12345-11.4
```

>**note**: this is a "works on my machine" kind of script - tweak it to your liking.
