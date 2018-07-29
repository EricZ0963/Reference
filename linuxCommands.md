# Helpful commands for beginning working with linux  

## SSH  

A good ssh client for Windows is [PuTTY](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html).
On MacOS/Linux, open terminal and type `ssh [username]@[ip.add.r]

The default, admin (aka sudo) username is `root`.

### ls  

Lists everything in the current directory. To view hidden files (they start with a `.`, e.g. `.hidemepls`), add the `-a` flag. To list stuff in other directories, do `ls path/to/directory`.  

#### Examples  

- `ls`: List non-hidden files and directories located in the current directory.
- `ls -a /`: List everything, including hidden files and directories, located at the top of the directory tree.  
- `ls ~/myDirectory`: List non-hidden files and directories located in `myDirectory`, which is under the home directory (`~` is a shortcut/alias for that). The home directory for the default user, `root`, is located at `/root/`. The home directory for other users are at `/Users/[username]`.  
- `ls ../someDir`: List non-hidden files and directories located in `someDir`, which is under the directory "above" the current one. So, if you are currently in `~/Dir1/Dir2`, and you want to show files in `~/Dir1/someDir`, you would use this command.  

### cd  

Change directories to the specifed one. Not much to it... just remember the `~` and `/` and `..`  

#### Examples  

- `cd /`: cd to the top (also called root but not to be confused with `/root`) directory.  
- `cd ../../test`: cd "up" two directories and then "down" into `test`.  

### mkdir  

Makes a directory with the specified name. Note that you are not sent to that directory automatically. You still need to `cd` into it.

#### Examples  

- `mkdir pigs`: Make a directory called `pigs` under the current directory.  
- `mkdir /bacon`: Make a directory called `bacon` under the top (root, see above) directory. Not recommended. Usually, you should save all files you work with under `~`, unless you are editing system/software configurations.  
- `mkdir ../lard`: Make a directory under the directory which contains the current directory. In this sense, `lard` and your current directory are on the same level; if you did `ls ..` you would see them both.  

### nano  

Edits a file using the `nano` text editor. Other popular editors include `vim` and `emacs`, but `nano` is better.  

#### Example  

- `nano ../hedgehog.json`: Edit a file, called `hedgehog.json`, in the directory containing the current directory.  

#### Helpful key combinations for nano  

These are also shown at the bottom of the `nano` editor, but I'll put them here anyway. `^` means ctrl.  
- `^X`: Does not cut; instead means "exit". If you have made changes and want to save, make sure to type `Y` when prompted.  
- `^O`: Save the file. Press enter to confirm you want to save it under the same name.  
- `^W`: Searches the document for text.  Pretty intuitive; type phrase in and hit enter.  

### rm  

Remove a file. If you want to remove a directory, use the `-r` flag.  

#### Examples  

- `rm -r cows`: Remove a directory called `cows` under the current directory.  
- `rm script.sh`: Remove the file called `script.sh` in the current directory.  
- `rm -r *`: Remove all files and directories in the current directory. `*` is a placeholder.  
- `rm webpage/*a.sh`: Remove all files ending in `a.sh`, e.g. `ba.sh` or `TakeOutTheTra.sh`, in a directory called `webpage` under the current directory.  
- `rm -r prefix*`: Remove all files and directories starting with `prefix`, e.g. `prefixLard.json` or `prefix`, in the current directory.  

### mv  

Move a file or directory. Also used for renaming.  

#### Examples  

- `mv site/hammer .`: Moves `hammer` inside the `site` directory under the current directory to the current directory (denoted as `.`).  
- `mv My\ Music/* music`: Moves everything in a directory called `My Music` to `music`. Note that the backslash is used to escape the space character so `My` and `Music` can be combined. Another way of doing this is to enclose `My Music/*` in quotes, e.g. `mv "My Music/*" music`.  
- `mv text.txt script.sh`: Renames `text.txt` in the current directory to `script.sh`.  
- `mv music moosic`: Renames `music` to `moosic`. Even if this is a directory, no recursive `-r` flag needs to be added.  

### exit

Closes the ssh connection.  

#### Example

- `exit`: Close the ssh connection.  



## FTP / SFTP  

[FileZilla](https://filezilla-project.org/download.php?type=client) is a good FTP client with a GUI. If you would rather use CLI, the following commands will be useful.

### put  

Moves a local file to the server.  

#### Examples

- `put homework`: Move the file `homework` in the current local directory to the current remote directory.  
- `put C:/Users/Pig/bacon ~/lard`: move `bacon` in the specified file path to the remote home directory and rename it to `lard`.  
-  `put C:/Users/Pig/*.mp3 ~`: move all files ending in `.mp3` in `Pig` to the remote home directory.

### get  

Exact opposite of `put`, except specify remote path first.  

#### Example  

- `get ~/hmm`: Download `hmm` located in the remote home directory to the current local directory.  

### Other commands  

You should also be able to use `ls`, `cd`, `mkdir`, and `rm`. Close the connection with `quit`.
