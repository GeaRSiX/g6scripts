# g6scripts
A collection of personal scripts I use in linux environments

## overview
I use most of these scripts for convenience and to save on typing. I've probably got a few more coming that are currently sitting in my .bashrc

## contents

1. [installing](#installing)
2. [uninstalling](#uninstalling)
3. [notes](#notes)
4. [scripts](#scripts)

If any of them are do-able with a simple single-line of Bash, please let me know!

## installing
I've created an install script (_another_ bash script) to help with selecting the scripts you want to install.
```
	usage: ./install [ARGUMENTS]

	ARGUMENTS
	-d, --dest [DESTINATION]    pre-define the destination to install the scripts to
	-a, --all                   install ALL the scripts, will answer "y" automatically
	-l, --link                  will "ln -s" the script (not copy it), note if location of source changes then links will break
	-h, --help                  print this dialog
```

## uninstalling
I'm planning to add an uninstall bash script too, currently you'll have to manually delete all the files added though.

## notes
Personally, I like to `mkdir` a ~/bin folder (make sure ~/bin is in $PATH) and ln -s for all the scripts I wanna use (e.g. below):
```
	./install --link --dest ~/bin
```

## scripts
### strings
Scripts related to string parsing/manipulation

- strlen = prints the length of string ($1)
- strindex = prints the index (starting from 0) of the first character in substring ($1)
- gfind = find all files in dir ($1), that conatin string ($2) - SUPER useful for debugging somebody else's code

### file management

- shh = runs binaries ($1..$n) and send stdout to /dev/null (this probably needs a rename)
- flac2mp3 = converts .flac files ($1..$n) to .mp3 files
- cpc = copy the contents of file $1 into file $2 **WARNING: will overwrite contents of file $2**
- xopen = open files ($1..) in their xdg-default
  - ```--shh``` ```-shh```
- openurl = open a .url file ($1) (see http://www.danielbrice.net/blog/opening-url-file-like-a-pro/)
  - I never use this one directly myself, instead I set it as the default binary for .url files in ~/.config/mimeapps.list and use xopen
- mkdcp = make directory ($1) and copy files into it ($2..$n)
- mkdmv = make directory ($1) and move files into it ($2..$n)
- mkdnvim = make directory ($1), touch file ($2) and open file ($2) in nvim

### misc

- while-true = clear the terminal, run $1 sleep ($2 || 1), repeat forever (Ctrl+C to cancel)

### depreciated

- touchn = create $2 files name $1 appended with 1 to $2
  - found out you could just use "touch ./file{0..13}"

# Authors
- GeaRSiX

