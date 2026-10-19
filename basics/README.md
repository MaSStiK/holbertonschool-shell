# holbertonschool-shell/basics

## Files

- 0-current_working_directory - Print the current working directory.
- 1-listit - List directory contents.
- 2-bring_me_home - Change to the user's home directory.
- 3-listfiles - List directory contents in long format.
- 4-listmorefiles - List all files, including hidden ones, in long format.
- 5-listfilesdigitonly - List all files in long format with numeric user and group IDs.
- 6-firstdirectory - Create /tmp/my_first_directory.

## Custom Bash function

I added a custom Bash function called `git-chmod` that automatically sets executable permissions, stages the file, updates its Git mode, and verifies the result.

#### Function (`~/.bashrc`)

```bash
git-chmod() {
    if [ -z "$1" ]; then
        echo "Usage: git-chmod <file>"
        return 1
    fi

    chmod u+x "$1" &&
    git add "$1" &&
    git update-index --chmod=+x "$1" &&
    git ls-files -s "$1" &&
    printf 'Success: %s is executable and staged in Git (100755)\n' "$1"
}
```
