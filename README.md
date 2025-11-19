# The Indigo Enterprise Linux (Server) Waybar Configuration
> [!WARNING]
> I've decided that I'm going to start compiling XLibre for RHEL 10 so this is EOL


Waybar config to make Windows Server 2022 refugees feel at home. Works well with [labwc](https://github.com/labwc/labwc).

![2024-07-21T15:52:00,421480788+07:00](https://github.com/user-attachments/assets/60a498d3-6989-48e9-b74d-d07242fee288)

### Installation
1. copy `waybar` directory into your `~/.config`
2. relaunch waybar (`pkill waybar`, `waybar & disown`)

### Default usage

> [!TIP]
> These are the actions called by the default configuration file. Feel free to change them, even if you are new to waybar, editing the config is very easy. Refer to the [wiki](https://github.com/Alexays/Waybar/wiki) for options.

* Click on OS button to try running `wofi --show drun`
* Scroll on workspaces buttons to move through them. It calls `hyprctl dispatch workspace r±1`, works in Hyprland only.
* Click on taskbar button to switch to app, middle-click to close it.
* Click on speaker sign to try running [pwvucontrol](https://github.com/saivert/pwvucontrol) - pipewire version of [pavucontrol](https://github.com/pulseaudio/pavucontrol)
* Clock's tooltip will expose waybar's calendar - it's not the prettiest, but it does its job!
* 
### Trivia
* `style.css` has most of it's colors exposed as variables at the very top of the file, making it easy to change them as you wish.
Waybar may also use some variables from your GTK theme, put `* { all: unset; }` in your `style.css` if you want to design everything from scratch.

* For some reason selection doesn't work if you put mouse at the very bottom of the screen - to fix this, I used a dirty hack of making waybar 1 pixel larger (41px total) and setting `"margin-bottom": -1` in the `config` file. This works fine - still weird you have to do this.

* Unfortunately I couldn't find a way to limit taskbar's elements length, so opening too many apps will push all of the right elements out of screen.
