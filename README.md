# D1ary

A simple diary shell script. If once a day you want to start writing a diary, 
this is an option for you.

Call this script and it will create a new record file for you in MARKDOWN 
format. It will open the editor and wait until you finish your writing. Then the 
final file will be encrypted using gpg and your key and stored in the diary 
directory.

## Configuration

The script is written for POSIX shell and should work in dash/bash. The editor 
used should block script execution until it is closed. This will keep the 
workflow intact. Recommended editor is _nano_, but any editor supporting this 
behavior can be used. The gpg key should be available. All settings can be done 
using the __.env__ file located in teh same directory as the script, with 
KEY=value syntax or global environment variables. 

### Editor

```
D1ARY_EDITOR=nano
```

If there is no configured editor, the script will try to check the default system 
editor or just use _nano_. It will fail if nothing is found.

### Diary directory

```
D1ARY_DIR=~/.d1ary
```

This is where all the records will be collected.

### GPG encryption key

```
D1ARY_KEY=0xENCRYPTION_KEY_ID
```

If empty or not configured, records will be saved unencrypted. 

There are many HOWTOs on the internet explaining how to generate a GPG 
private/public key pair. For a simple one you can use something like:

```bash
gpg --expect --full-gen-key
```

or even

```bash
gpg --full-gen-key
```

### .env file example

```bash
D1ARY_EDITOR=editor
D1ARY_DIR=~/.d1ary
D1ARY_KEY=0xENCRYPTION_KEY_ID
```



