# Troubleshooting

## Problem 1: `poppy.local` does not answer.

This is the most frequent error when using Poppy robots: when you type `http://poppy.local` in your web browser, an error tells you that the website can't be loaded such as:

![Page doesn't exist](../assembly-guides/ergo-jr/img/IHM/webpage_not_available.jpg)

The difficulty with this error is that it may have multiple sources, but no worries, here is a procedure to help find the right source of the issue:

## 🔧 Diagnostic procedure

### I. Make a ping test
A ping is basically a tentative of contact of your robot, that will reply with a "pong", which allows to measure various time statistics of the communication.

1. Plug your robot with an Ethernet cable, either directly or through a router, and plug its power supply so that it boots 
2. Open a terminal: on Windows press the Windows key of your keyboard and type "cmd", open the found terminal. On Linux or OSX, a terminal app can be easily found be browsing the app lists or menus. 
3. You get a window, usually with a dark background and a prompt mentionning your username and your computer name. Type `ping poppy.local` and press Enter
4. Each second a new line will print on screen, such as:

![Successful ping test](/img/ping.png)

Depending your system and network configuration, the look of the window, IP addresses and delays may vary a lot from the screenshot. The most important element to identify is whether the lines mention time statistics in milliseconds. If they do, the ping test is **successful**, and the IP address in parenthesis near `poppy.local` is the current IP address of your robot. Be careful, this IP address may vary each time, but `poppy.local` does not, unless you change the robot name in the settings.

If the ping is successul, jump to **II.A**. If it is not, an error is probably displayed instead, telling that the tentative of communication has failed, in that case jump to **II.B.**.

On Windows, a ping test aborts after 4 lines. On GNU/Linux and OSX, new lines appear every second infinitely. You can press Ctrl + C to stop it, or just close the terminal as a regular window.

### II.A. If the ping test succeeds

If the ping test succeeds but you still cannot `http://poppy.local`, the problem probably comes from the web browser.

1. Make sure you do not omit the `http://` prefix. This prefix ensure that a normal connection to the robot is made. Modern web browsers may be tempted to make a secure connection instead by replacing it by `https://`, but secure connections only work when surfing the Internet.
2. You may experience cache troubles: press Ctrl+Shift+R to tell your browser to reload the page without caching.
3. Try another web browser: Mozilla Firefox, Chromium, Safari, Opera, Microsoft Edge, Google Chrome...
4. In last resorts, it is possible that Poppy software fail to start on the Raspberry Pi. In that case it is recommanded to [re-flash your SD card](../installation/burn-an-image-file.md).

### II.B. If the ping test fails

If the ping test succeeds you experience a network issue: your computer does not manage to talk to Poppy!
1. Unplug the power supply of the robot, it will shut down
2. Plug it again, bby paying a particular attention to the red and green LEDs of the Raspberry Pi:

**The red LED `PWR` (Power) must be steady red** 🔴 and **the green led `ACT` (activity) must irregularly flicker during about 45 seconds**, meaning that the robot is booting. Choose your case A, B, C, or D:

A. If `PWR` is not steady red 🔴 : you experience a power failure. With an Ergo Jr robot, you might have plugged your Pixl board incorrectly, make your sure followed [the electronic assembly procedure](../assembly-guides/ergo-jr/electronic-assembly.md) correctively. Otherwise, your Pixl board or you power supply, or your Raspberry Pi may be faulty. Try swapping components from another robots to identify the faulty component if you have several robots, or contact your robot supplier.

B. If the green led `ACT` remains off, then the system on the SD card is probably faulty, or the SD card itself, or the Raspberry Pi. First try to [re-flash your SD card](../installation/burn-an-image-file.md), then try to flash and use another SD card >8GB, and in last resort try with another Raspberry Pi.

C. If the green led `ACT` 🟢 flashes regularly as a sequence of long and short flashes, the blinking sequence can give you clues about the reason of boot failure. Consult [the appropriate documentation](https://www.raspberrypi.org/documentation/configuration/led_blink_warnings.md). 

D. If the green led `ACT` 🟢 flashes **irregularly** during about 45 seconds and then almost switch off except ponctual flashing, and if the ping still fails, it means that the robot is booting properly but some network error is happening. The connection mode you have chosen (wifi, direct Ethernet, Ethernet through a router, or hostpot) might be not working with your configuration. A good idea in that case is to fall back to the simplest possible connection: Ethernet through a router, which requires 2 Ethernet cables: 1 from your robot to your router and 1 from your computer to your router. And execute again the diagnostic procedure.

## Problem 2: My robot makes shaky motions

This may be due to old cables. Especially if you feel that cables are rigid compared to brand new cables, while they should be flexible. Old cable may cause communication issues. Change them with brand new cables.

## Problem 3: My robot makes weird motions or auto-collides

If you robot makes motions that are not those that you expect or even collides with itself, it is probably because you assembled the robot the wrong way. Open the assembly guide again, and observe carefully that every part of your assembly matches the pictures. It is very easy to build a robot that looks properly assembled but that is not.

## Problem 4 : What is the default SSH password of my robot?

A password is needed only for SSH access (advanced users). With the regular Poppy image, the username is `poppy` and the password is `poppy`. With the ROS image, the username is  `pi` and the password is `raspberry`.