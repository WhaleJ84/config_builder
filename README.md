# Config\_builder

Takes multiple files and creates a new merged file.

`cnfgbldr [input directory] [output file]`

## Building your config

The script was designed with building shell configuration scripts from decentralised files across your system.
An example of this is through the use of aliases.
Many aliases are shell agnostic (e.g. not BASH specific) and could be used across multiple shells.
Building a shell config file modularily by merging individual files into one allows for cross compatability.

### Example file structure

- 1-.bashrc
    - includes the original file provided in a default BASH installation
- 2-aliases
    - includes custom aliases that work across different systems
- 3-global\_exports
    - includes global variables such as $PATH additions

Running the command on this directory with `config_builder $dir ~/.bashrc` would build a new configuration file without the need for manual intervention.
You can use symlinks to build the config directory with `ln -s $(realpath $file) $dir` to link in files from all over your system without making copies.
