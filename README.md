# Config\_builder

Takes multiple files and creates a new merged file.
Basically just `cat` - nothing fancy.

`config_builder [input directory] [output file]`

## Building your config

The script was designed to build shell configuration scripts from decentralised files across your system.
An example of this is through the use of aliases.
Many aliases are shell agnostic (e.g. not BASH specific) and could be used across multiple shells.
Building a shell config file modularily by merging individual files into one allows for cross compatability.

### Example file structure

```
input_directory/
|-- 1-bash_defaults
|-- 2-ssh
|-- 3-aliases
|-- 4-custom_commands
|-- 5-prompt
`-- 6-vi_mode
```

Running the command on this directory with `config_builder input_directory/ ~/.bashrc` would build a new configuration file without the need for manual intervention.
You can use symlinks to build the config directory with `ln -s $(realpath $file) $dir` to link in files from all over your system without making copies.
