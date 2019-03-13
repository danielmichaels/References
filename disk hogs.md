# Check Disk Usage

## Folders

To find the five largest directories inside the home directory run the following command

```bash
du -Sh | sort -rh | head -n 5
```

The options detailed below:
`du` command: Estimate file usage
`-h`: human readable format
`-S`: do not include subdirectories
`sort' command: sort lines of text
`-r`: reverse the result of comparisons
`-h`: compare human readable numbers (2k v 1G)
`head` command: output the first results
`-n`: output on that many lines from `head`

This command will output only the directories from the current working directory and its subfolders.


## Files

To find the five biggest files on the machine run the following:

```bash
find -type f -exec du -Sh {} + | sort -rh | head -n 5
```

This will run the find command and then execute `du` to output it into human readable format.



