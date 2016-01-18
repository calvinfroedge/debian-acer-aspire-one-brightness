# Getting Brightness Adjustment to work on Aspire One Netbook running Debian

I recently purchased an Acer Aspire One netbook for traveling. I paid $100 for it, put an $80 SSD in, and it's a lightweight, fast, little computer.

Getting the brightness adjustment to work was a challenge. Here are the steps:

1) If you haven't already, Download the official drivers for Linux from AMD and run the installer. The free software drivers crashed my desktop environment. Didn't investigate much further...I was just trying to control brightness. Getting the drivers will make your video card perform MUCH better in general (i.e. videos won't be choppy).

2) After installing, run the `aticonfig` tool.

3) Put / symlink the "brightness" file, which is a bash script, in this repo somewhere in your path. Now you can do `brightness up` or `brightness down` to change your brightness in 10% increments.

4) Add keybindings if using LXDE, I believe there's a GUI in settings if you're using GNOME (~/.config/openbox/lxde-rc.xml):

```
    <!-- FN + left arrow -->
    <keybind key="XF86Display">
      <action name="Execute">
        <command>brightness down</command>
      </action>
    </keybind>
    <!-- FN + right arrow -->
    <keybind key="XF86MonBrightnessUp">
      <action name="Execute">
        <command>brightness up</command>
      </action>
    </keybind>
```

5) Logout / login and you should be able to adjust brightness with Fn + Left Arrow / Fn + Right arrow

Notes:

- If you don't like bash, use your own shell, this script should give you most of what you need.
- LXDE performs extremely well and seems to be less buggy than GNOME.
