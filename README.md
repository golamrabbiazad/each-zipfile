# Single Zip file via loop inside cur: dir

##### At a point of time, making zip file into whole directory manually with each file into zip file, needs lots of time and boring. That's why `find` & `zip` command helps do this stuff in command line easier.

`$bash` | `~zsh` or `>fish` command: 


```
find . -type f -execdir zip '{}.zip' '{}' \;
```

Explanation:

- The first argument is the directory you want to begin in, `.` or `/dirname`
- Then we will restrict it to find files only (`-type f`) or (`-type d`) it search for all current directory.
- The `-execdir` option allows us to run a command on each file found, executing it from the file's directory
- Before the the `{}.zip` command, we can move all zip file into the single folder `outdir/`
- This command is evaluated as `zip sample.txt.zip sample.txt`, for example, since all occurrences of `{}` are replaced with the actual file name. This command needs to be ended with `\;`



One just a problem head up, it remains with original extentions name `zip sample.txt.zip` with `.txt` name. What i do in mac or you can use `mv` command to rename files: 

- Select all the files and clicks on rename files and popup window shows up. Find the text and `.txt.zip` to `.zip`.

