# Notes
General Notes

# Convert Rmd to Ipynb
Convert R Markdown to Iron Python notebooks
`jupytext --to notebook 2_basics.Rmd` 
https://github.com/mwouts/jupytext

# How to update `rlang` in Anaconda
https://gist.github.com/pankajshrestha/4a123a7b3ab063f6fa2dbc82031c3cef

# AutoHotKey setup
https://github.com/pankajshrestha/mac-keyboard-behavior-in-windows/tree/main

# Adding SSH Key to Mac Keychain
https://gist.github.com/pankajshrestha/d647e8780cae55486c0cc282622901db

# Creating symbolic link in Windows
https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/mklink
E.g. `c:\Users\Pankaj Shrestha>mklink /d DGTech "D:/GTech"`

# List Jupyter Sessions with their tokens
jupyter server list

# Windows Keyboard mappping changes for MacOS
- MacOS Keyboard Settings - Modifier Keys
  - Option -> Command
  - Command -> Option
# Karabiner-Elements rules
- Simple Modifications
  - left_command -> left_option
  - left_option -> left_command
- Complex Modifications
  - ```{
    "description": "AJ-Caps Lock → Hyper Key (⌃⌥⇧⌘) (Escape if alone)",
    "manipulators": [
        {
            "from": { "key_code": "caps_lock" },
            "to": [
                {
                    "key_code": "left_shift",
                    "modifiers": ["left_command", "left_control", "left_option"]
                }
            ],
            "to_if_alone": [{ "key_code": "escape" }],
            "type": "basic"
        }
    ]
}```
  
