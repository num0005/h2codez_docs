title:      Blender Plugins
desc:       Installing plugins for use in Blender
template:   document
nav:        Blender Tutorial>Plugin Install
percent:    100
date:       2020/08/05
authors:    General_101

[Halo Export Scripts](http://www.h2maps.net/Tools/PC/Export%20Scripts/Halo_Export.7z) -> Export scripts for your 3D modeling software of choice.


Hi there!

If you're on this page then you're likely a beginner asking yourself how to install the plugins offered here for Halo development. We shall go over two methods for installing plugins. Either through the menu under preferences or
manually by navigating to the addons directory and dropping them off there.

### Installing add-ons in the preferences menu
Navigate to the "Edit" dropdown and select the button labeled "Preferences as seen in the image below.

![](assets\A.png)

You should see a new window appear that looks like this.

![](assets\B.png)

Ensure that you have "Add-ons" selected and that you are under the "Community" plugins in the category of "Import-Export" As shown in the previous image. You should have noticed the button labeled "Install...". From here you
can navigate to a .py file or a zip contianing .py files to have Blender copy it to the addons directory. Once you've selected it you should now see this menu.

![](assets\C.png)

You will want to select the checkbox and save your new settings to enable the plugin. The image below will highlight the areas you should be looking at.

![](assets\D.png)

Congrats! You should be able to use the plugin assuming nothing has gone wrong or the plugin isn't a paperweight due to code changes a few years from now. Let's go over the manual method now.

### Installing add-ons manually

Let's say that the install method just won't play nice for some reason. We can easily just move it to where it belongs and enable it. Start by navigating to...

```
%appdata%\Blender Foundation\Blender
```

Add the following to the path.

```
\(Blender Version)\scripts\addons
```

If a folder in that path doesn't exist then create it. Once you're in addons you can simply move whatever you want to install into this folder.

![](assets\E.png)

![](assets\F.png)

After it's in you can hit the button labeled "Refresh" next to the "Install..." button to see the new plugins you just moved in. Enable them like you did in the first example. If everything works out then you should have
working plugins.