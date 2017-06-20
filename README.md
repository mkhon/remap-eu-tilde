# Overview

This OS X keyboard layout remaps left upper key (below Esc) on Mac EU keyboards to backquote/tilde.

# Installation

1. Copy `U.S. (tilde)` to `/Library/Keyboard Layouts` or `~/Library/Keyboard Layouts`
2. Add `U.S. (tilde)` layout in `System Preferences / Keyboard`
3. To remove default `U.S.` layout do the following:
```
plutil -convert xml1 ~/Library/Preferences/com.apple.HIToolbox.plist
```
Then edit ~/Library/Preferences/comm.apple.HIToolbox.plist and remove `U.S.` from `AppleEnabledInputSources` dictionary. If there is an `AppleDefaultAsciiInputSource` key then also remove it.

See also: https://apple.stackexchange.com/questions/44921/how-to-remove-or-disable-a-default-keyboard-layout/60521#60521

# Implementation Details

This map was created using Ukulele (http://scripts.sil.org/ukelele):
1. Create a new keyboard layout from `U.S.` layout: `File / New From Current Input Source`
2. Rename created layout (right-click, `Set Keyboard Name and Script...`)
3. Open created layout (double-click), then swap keys with scancodes `10` and `50`:
`Keyboard / Swap Keys By Code...`, then enter `10` and `50` in the input boxes.