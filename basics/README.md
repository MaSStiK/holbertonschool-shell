# holbertonschool-shell/basics

## Files

- 0-current_working_directory - Print the current working directory.
- 1-listit - List directory contents.
- 2-bring_me_home - Change to the user's home directory.
- 3-listfiles - List directory contents in long format.
- 4-listmorefiles - List all files, including hidden ones, in long format.
- 5-listfilesdigitonly - List all files in long format with numeric user and group IDs.
- 6-firstdirectory - Create /tmp/my_first_directory.
- 7-movethatfile - Move /tmp/betty to /tmp/my_first_directory.
- 8-firstdelete - Delete /tmp/my_first_directory/betty.
- 9-firstdirdeletion - Delete /tmp/my_first_directory.
- 10-back - Return to the previous working directory.
- 11-lists - List files in the current, parent, and /boot directories.
- 12-file_type - Display the type of /tmp/iamafile.
- 13-symbolic_link - Create a symbolic link to /bin/ls.
- 14-copy_html - Copy new or updated HTML files to the parent directory.
- 15-lets_move - Move files starting with uppercase letters to /tmp/u.
- 16-clean_emacs - Delete files ending with ~.
- 17-tree - Create the welcome/to/school directory structure.

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
