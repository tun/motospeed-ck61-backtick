# Motospeed CK61 backtick

![My motospeed CK61 with backtick keycap](keyboard.jpg)

Motospeed CK61 60% mechanical keyboard lacks of backtick (`) key.

I solved this issue by remap `escape` key as backtick and `caps lock` key as escape.

## Linux

Copy the following snippet to your `~/.Xmonad` file:

```
! Motospeed CK61
! Escape key as backtick
keycode 9 = dead_grave dead_tilde
! CapsLock as escape
clear lock
keycode 66 = Escape
```

## macOS

Run the following command in your terminal:

```
hidutil property --set '{"UserKeyMapping": [{"HIDKeyboardModifierMappingSrc":0x700000029, "HIDKeyboardModifierMappingDst":0x700000035}, {"HIDKeyboardModifierMappingSrc":0x700000039, "HIDKeyboardModifierMappingDst":0x700000029}]}'
```

**Nota:** Remap changes using above command will be lost after reboot, to make it persistent, copy the `com.motospeed.ck61-backtick.plist` file to `~/Library/LaunchAgents/` directory instead.
