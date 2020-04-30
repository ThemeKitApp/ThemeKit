# ThemeKit
A unified macOS theming platform

# What is ThemeKit?


ThemeKit is a macOS application that allows you to apply custom built themes to your applications. The goal is to mimic a theme manager from the iOS jailbreaking community which allows you tomap icons with a bundle ID and distribute easily.Themes are currently sparse but will eventually be available at [The Official ThemeKit Store](https://themekit.io) for a varying range of prices.

If you would like to read more about why ThemeKit 
requires SIP being disabled read [here](https://github.com/MTACS/ThemeKit#sip-and-permissive-information).

If you'd like to convert an iOS theme for ThemeKit please check out Joseph Shenton's [zTheme Converter](https://github.com/JosephShenton/zTheme). We also have documentation on how to create your own bundles. The wiki is currently in progress but for now refer to [here for more info](https://github.com/MTACS/ThemeKit/wiki/Bundling-a-theme).

<p align="center>
  <p align="center"><a align="center"><img src="https://media.discordapp.net/attachments/603653696030507023/698270367050891425/Screen_Shot_2020-04-10_at_4.33.58_PM.png?width=876&height=702" width="300px" alt="dark></a></p>
  
  <p align="center"><a align="center"><img src="https://media.discordapp.net/attachments/603653696030507023/698270363263434752/Screen_Shot_2020-04-10_at_4.34.27_PM.png?width=876&height=702" width="300px" alt="light"></a></p>
</p>

# Installation

### Getting Started

First, visit [the Releases page](https://github.com/MTACS/ThemeKit/releases) to get the latest version of ThemeKit.


#### Before Running ThemeKit (Important):

First you must disable SIP. This is required since we are temporarily modifying system files and in order to have access to their asset metadata we must unlock SIP or macOS complains. *Re-enabling SIP will mess up your setup and themes so you should revert any theme changes before re-enabling!*

If you are on Catalina (10.15+) you must run `sudo mount -uw /` after disabling SIP and rebooting.

Next run:

```
chmod -R 757 /System/Applications/
chmod -R 757 /Applications/
```

You are now ready to run ThemeKit and start applying themes!

# Adding Themes

There are not a lot of themes available currently but you can convert your own iOS themes to ThemeKit themes with  [zTheme](https://github.com/JosephShenton/zTheme). 

The [ThemeKit Website](https://themekit.io) currently does not have a lot on it but will soon have a store and system where you can download, host, and redistribute your themes easily. ThemeKit has a special URI scheme which allows you to install themes directly from the browser. If you are hosting your own theme the schema URI is:

```
themekit://open/https://<URL TO BUNDLE>.zip
```

If users have ThemeKit installed, clicking this will automatically open ThemeKit up and download it for them!

## Troubleshooting

### Icons Are Not Being Applied!

#### If you are running any version of macOS Catalina, Apple apps that come installed must have their permissions changed to read/write or ThemeKit must be run as root

### Calendar is not being themed

#### The Calendar app uses a Dock Tile plugin to display the icon, which allows it to change the date. This means ThemeKit would have to manually replace files which we are trying not to do.

### Icons are still themed after removing a theme

#### Click 'Force Refresh' under the Utilities menu in the menu bar, and wait for the Dock to be killed.

## SIP and Permissive Information

ThemeKit requires SIP (System Integrity Protection) to be disabled to theme icons. This is because in newest macOS versions, certain files cannot be modified. ThemeKit uses methods built into AppKit to change icons. Removing a theme resets icons to stock macOS. 

On macOS Catalina, new methods prevented ThemeKit from working properly with just SIP disabled. This is because a new read only partition was added to Catalina called /System which cannot be modified. This requires us to remount it as read write, something similar to jailbreaking on iOS. This can be done by running ```sudo remount -uw /``` followed by your password. This is only temporary as it will be reset to read write upon boot, so this command can be run only when you need to change a theme after reboot. 

Any system apps, as well as user apps installed via a .pkg usually have read/write permissions disabled. In order for ThemeKit to apply icons this must be set to enabled. Once a theme has been applied, it can be disabled again, although will require these steps to be repeated when changing, applying or removing a theme. 

## Disclaimer

ThemeKit is considered an experiment, and is provided as is. This does not rely on code injection, and requires certain security measures to be disabled, albeit temporarily. 

## Screenshot Information

Icons in screenshots are [Glacier](https://glaciericons.com/) with some of my own icons in that style. Banner space image found [here](https://www.spacetelescope.org/images/heic1105a/)


#### Mockup Credits

[MacBook Pro Mockup](https://www.anthonyboyd.graphics/mockups/realistic-2016-space-gray-macbook-pro-mockup-vol-8/)
