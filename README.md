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
```
{
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
}
```
```
{
    "description": "Change double tap right ⇧ key to caps lock",
    "enabled": false,
    "manipulators": [
        {
            "conditions": [
                {
                    "name": "right_shift pressed",
                    "type": "variable_if",
                    "value": 1
                }
            ],
            "from": {
                "key_code": "right_shift",
                "modifiers": { "optional": ["any"] }
            },
            "to": [{ "key_code": "caps_lock" }],
            "type": "basic"
        },
        {
            "from": {
                "key_code": "right_shift",
                "modifiers": { "optional": ["any"] }
            },
            "to": [
                {
                    "set_variable": {
                        "name": "right_shift pressed",
                        "value": 1
                    }
                },
                { "key_code": "right_shift" }
            ],
            "to_delayed_action": {
                "to_if_canceled": [
                    {
                        "set_variable": {
                            "name": "right_shift pressed",
                            "value": 0
                        }
                    }
                ],
                "to_if_invoked": [
                    {
                        "set_variable": {
                            "name": "right_shift pressed",
                            "value": 0
                        }
                    }
                ]
            },
            "type": "basic"
        }
    ]
}
```

```
{
    "description": "End to Command Right",
    "manipulators": [
        {
            "conditions": [
                {
                    "bundle_identifiers": [
                        "^com\\.microsoft\\.rdc$",
                        "^com\\.microsoft\\.rdc\\.mac$",
                        "^com\\.microsoft\\.rdc\\.macos$",
                        "^com\\.microsoft\\.rdc\\.osx\\.beta$",
                        "^net\\.sf\\.cord$",
                        "^com\\.thinomenon\\.RemoteDesktopConnection$",
                        "^com\\.itap-mobile\\.qmote$",
                        "^com\\.nulana\\.remotixmac$",
                        "^com\\.p5sys\\.jump\\.mac\\.viewer$",
                        "^com\\.p5sys\\.jump\\.mac\\.viewer\\.web$",
                        "^com\\.teamviewer\\.TeamViewer$",
                        "^com\\.vmware\\.horizon$",
                        "^com\\.2X\\.Client\\.Mac$",
                        "^com\\.vmware\\.fusion$",
                        "^com\\.vmware\\.horizon$",
                        "^com\\.vmware\\.view$",
                        "^com\\.parallels\\.desktop$",
                        "^com\\.parallels\\.vm$",
                        "^com\\.parallels\\.desktop\\.console$",
                        "^org\\.virtualbox\\.app\\.VirtualBoxVM$",
                        "^com\\.citrix\\.XenAppViewer$",
                        "^com\\.vmware\\.proxyApp\\.",
                        "^com\\.parallels\\.winapp\\.",
                        "^org\\.macports\\.X11$",
                        "^com\\.apple\\.Terminal$",
                        "^com\\.googlecode\\.iterm2$",
                        "^co\\.zeit\\.hyperterm$",
                        "^co\\.zeit\\.hyper$",
                        "^io\\.alacritty$",
                        "^net\\.kovidgoyal\\.kitty$"
                    ],
                    "type": "frontmost_application_unless"
                }
            ],
            "from": {
                "key_code": "end",
                "modifiers": { "optional": ["shift"] }
            },
            "to": [
                {
                    "key_code": "right_arrow",
                    "modifiers": "command"
                }
            ],
            "type": "basic"
        }
    ]
}
```

```
{
    "description": "Home to Command Left",
    "manipulators": [
        {
            "conditions": [
                {
                    "bundle_identifiers": [
                        "^com\\.microsoft\\.rdc$",
                        "^com\\.microsoft\\.rdc\\.mac$",
                        "^com\\.microsoft\\.rdc\\.macos$",
                        "^com\\.microsoft\\.rdc\\.osx\\.beta$",
                        "^net\\.sf\\.cord$",
                        "^com\\.thinomenon\\.RemoteDesktopConnection$",
                        "^com\\.itap-mobile\\.qmote$",
                        "^com\\.nulana\\.remotixmac$",
                        "^com\\.p5sys\\.jump\\.mac\\.viewer$",
                        "^com\\.p5sys\\.jump\\.mac\\.viewer\\.web$",
                        "^com\\.teamviewer\\.TeamViewer$",
                        "^com\\.vmware\\.horizon$",
                        "^com\\.2X\\.Client\\.Mac$",
                        "^com\\.vmware\\.fusion$",
                        "^com\\.vmware\\.horizon$",
                        "^com\\.vmware\\.view$",
                        "^com\\.parallels\\.desktop$",
                        "^com\\.parallels\\.vm$",
                        "^com\\.parallels\\.desktop\\.console$",
                        "^org\\.virtualbox\\.app\\.VirtualBoxVM$",
                        "^com\\.citrix\\.XenAppViewer$",
                        "^com\\.vmware\\.proxyApp\\.",
                        "^com\\.parallels\\.winapp\\.",
                        "^org\\.macports\\.X11$",
                        "^com\\.apple\\.Terminal$",
                        "^com\\.googlecode\\.iterm2$",
                        "^co\\.zeit\\.hyperterm$",
                        "^co\\.zeit\\.hyper$",
                        "^io\\.alacritty$",
                        "^net\\.kovidgoyal\\.kitty$"
                    ],
                    "type": "frontmost_application_unless"
                }
            ],
            "from": {
                "key_code": "home",
                "modifiers": { "optional": ["shift"] }
            },
            "to": [
                {
                    "key_code": "left_arrow",
                    "modifiers": "command"
                }
            ],
            "type": "basic"
        }
    ]
}
```


# Aula F75 Pro shortcuts:
- Change Charging Indicator: Fn + Shift
- Mac mode: Fn + E
- Win mode: Fn + W
- Android mode: Fn + ?
- Battery Level: Fn + B
- Switch Lighting: Fn + \
-   Change Brightness: Up arrow/ Down Arrow
-   Change Speed: Right/ Left Arrow
-   Static Light: Fn + Tab
-   To stop pulsating, cicle thru different "breathing" options
