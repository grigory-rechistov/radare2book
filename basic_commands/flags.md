## Flags

Flags are similar to bookmarks. They represent a certain offset in a file. Flags can be grouped in 'flag spaces'. A flag space is something like a namespace for flags. They are used to group flags of similar characteristic or type. Examples for flag spaces: sections, registers, symbols.

To create a flag type:

     [0x4A13B8C0]> f flag_name @ offset
    
You can remove a flag by appending the `-` character to command. Most of commands accept `-` as argument-prefix as an indication to delete something.

     [0x4A13B8C0]> f- flag_name

To switch between or create new flagspaces use the `fs` command:

     # List flag spaces
     [0x4A13B8C0]> fs

     00   symbols
     01   imports
     02   sections
     03   strings
     04   regs
     05   maps
     
     [0x4A13B8C0]> fs symbols ; select only flags in symbols flagspace
     [0x4A13B8C0]> f          ; list only flags in symbols flagspace
     [0x4A13B8C0]> fs *       ; select all flagspaces
     [0x4A13B8C0]> f myflag   ; create a new flag called 'myflag'
     [0x4A13B8C0]> f- myflag  ; delete the flag called 'myflag'

You can rename flags with `fr`.
