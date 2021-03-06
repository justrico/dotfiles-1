# i3:

## Setup:

1. check if platform supports i3
2. install i3
3. logout distro
4. from menu button, choose i3
5. generate config file | later type `i3-config-wizard`
6. set `mod` as `win` for `CMD` keybinding on Mac
7. type `vi ~/.config/i3/config` | `nano ~/.config/i3/config` to edit
   [config](https://github.com/bookercodes/dotfiles/blob/ced9da54336f44776447a380709f75112723005e/.i3/config#L145)
8. type `man i3` to view manpage; type `/<query>` to query search
9. type `MOD + Shift + e` to logout (execute changes)

## i3:

1. type `ESC` to exit process mode
2. type `i3lock` to lock device, proceed to blank screen, type password
3. type `MOD + Enter` to open new terminal
4. type `MOD + Number` to switch workspace
5. type `MOD + d` to activate launcher
6. type `MOD + v` to set new terminal to vertical
7. type `MOD + h` to set new terminal to horizontal
8. type `MOD + r` to resize window proceeding with `Right Arrow` or `Left Arrow`
9. type `MOD + Right Arrow` to switch focus to the right
10. type `MOD + Left Arrow` to switch focus to the left
11. type `MOD + Up Arrow` to switch focus up
12. type `MOD + Down Arrow` to switch focus down
13. type `MOD + Shift + q` to quit process | application
14. type `MOD + Shift + e` to logout
15. type `MOD + Shift + r` to restart i3
16. type `MOD + Shift + c` to reload i3 config file
17. type `MOD + Shift + Arrow Key` to move window priority
18. type `MOD + Shift + Number` to give focused application a designated
    workspace

## Modify Keybinding:

1. change launcher from `MOD + d` to `MOD + Space`
2. change open new terminal from `MOD + Space` ? to `MOD + t`
3. `bindsym $mod+Tab workspace next`
4. `bindsym $mod+Shift+Tab workspace prev`

## Add to i3 config:

1. `exec_always feh --bg-scale wallpaper.jpg`
2. `exec_always compton -f` (requires logout)
3. `bindsym \$mod+shift+x exec i3lock --color "$bg-color"`
4. `bindsym $mod+y workspace $workspace4, layout tabbed, exec theapp`

## Tasks:

1. update i3
2. view drive partition from terminal
3. bar customization
4. i3lock customization
5. set media keys
6. set backlight keyboard
7. modify keybindings
8. assign apps to workspaces
9. set workspace names
10. install font
11. set terminal keybinding to open iTerm2 | preferred terminal
12. clean on config file
13. script kiddie time! (wallpaper theming, processes)

## Assign app to workspace:

1. open application and terminal
2. type `xprop` and click on application window; or type
   `xprop | grep "WM_CLASS(STRING)"`
3. copy value2 in the string `WM_Class(string)` = value1, value2
4. in config, type `assign [class="<application>"] #workspace<digit>` or
   alternatively, `for_window [class="Spotify"] move to workspace $workspace10`

## Install Font:

1. download font [Font Awesome](https://github.com/FortAwesome/Font-Awesome)
2. type `mkdir ~/.fonts` to make a folder in the home directory
3. type `mv <font>.ttf ~/.fonts/`; or `mv *.ttf ~/.fonts/`to move fonts to home
   directory
4. copy symbol from
   [font awesome cheatsheet](https://fontawesome.com/cheatsheet)
5. in config, paste symbol where you'd like, then set # Bar
   `bar { font pango: System San Francisco Display, FontAwesome 11 }`
6. logout to refresh
7. NOTE: "With i3 4.7.2 and font-awesome 4.5.0, the special icons wouldn't
   correctly render in the status bar (they'd just show as a blank dotted
   square). I had to add this inside the "bar { ... }" config: font pango:DejaVu
   Sans Mono, Awesome 8"

## Wallpaper:

### Option 1:

- [feh wall changer script](https://pastebin.com/L7tt8nf4)
- type `exec python ~/.wallpaper/wallpapers.py` to execute script

### Option 2:

- include in config, `exec_always sh $HOME/.feh`
- `.feh` script runs
  `feh --bg-fill --no-fehbg --randomize $HOME/.feh/<wallpaper>.jpg`

## i3 Manjaro Community Edition:

- i3 gaps
- i3-wm
- i3-blocks
- i3-lock
- i3-status

## Source:

- [Victor Adrian's Guide](https://dev.to/lobo_tuerto/you-need-to-know-about-i3-363c?utm_source=additional_box&utm_medium=internal&utm_campaign=regular&booster_org=)
