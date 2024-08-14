# HyprZwitch
Hyprland IPC observer to switch mouse profiles on the Swiftpoint Z series using the new x1cp API.

## Setup
Just place the files anywhere and set `zwitch` and `zwitchd` executable (`chmod u+x ...`), then run `zwitchd`.

### Dependencies
- packages: hyprland inotify-tools
- [Swiftpoint x1cp](https://support.swiftpoint.com/portal/en/community/topic/x1-control-panel-experimental-linux-version-18-7-2023) (version 3.0.7.2 beta or higher)

## Todo
- Extend to match other values from the `hyprctl clients` list, since currently only the window class is supported (was enough for my use cases so far).
- Add support for workspaces
- Add support for displays

## Files
### zwitch
Just a simple wrapper to send profile names to the x1cp socket.

### zwitchd
The actual script subscribing to the Hyprland socket to observe window focus changes, match these against the config and set the Z series profile accordingly.

### zwitchd.json
Configure your profiles here. As i just uploaded my own config you might want to rename the default profile.
The first item on the profile list is considered to be the default profile (name doesn't matter).

## Links
- [Hyprland IPC](https://wiki.hyprland.org/IPC/)
- Thread regarding the [Swiftpoint X1 Control Panel API](https://support.swiftpoint.com/portal/en/community/topic/x1cp-api)
