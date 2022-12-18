# LoveHue
### Manage your Hue lights, from Python

Philips Hue are great smart lights, made for customisation. This simple Python program basically brings the Hue app to a Python program, and adds a few new features to it.

## New features

Apart from expected features, such as setting the brightness, or turning your lights on or off, LoveHue adds some fun other features!
> **Note:** LoveHue is designed to work _with_ the already existing Philips Hue app, not to replace it.

Features include:

* Reset lights back to original; when you use the program, you usually change things such as the color of the lights or the brightness, but with one simple option, you can immediately put it all back to the original values from before you started LoveHue.
* Animations; these are simple animations. There are two built-in ones that use different code than the usual animations would do. The usual animations can be found in `.lhad` files (LoveHue Animation Dictionary) and are instructions written like JSON to tell LoveHue how to do a specific animation. You can look at some examples in the Animations directory.
* Setting lights to specific HEX colors

## How to install

You can install it with one of two ways.

### Install using [PyPlace](https://github.com/dante-nl/PyPlace)

You can install it via the PyPlace store. When you start PyPlace, you will get a menu like this:
```
[1] Open a PyPlace app
[2] Download a PyPlace app
[3] Open settings
[e] Exit PyPlace
```
What you want to do is to enter `2` followed by `2` to download from the Pyplace Store and then number `10`. Basically `[2] Download a PyPlace app > [2] Download from PyPlace store > [10] LoveHue — Control Hue lights in Python by dante_nl`.

If that does not work, you can also do `[2] Download a PyPlace app > [1] Link to Python file > https://raw.githubusercontent.com/dante-nl/PyPlace/main/Store%20Files/lovehue.py` as this would bypass the PyPlace store entirely.

### Install manually

If you don't have a folder for various Python apps, you have to create one in your file manager. For Windows this would probably be Explorer and for macOS this would probably be Finder.

Once you have that folder, you have to go in this repository to a file named `LoveHue.py` and click "Download". Then, put this file inside the folder you just created, and then you can run the file via Terminal/Command Prompt with `cd <your folder> && python3 LoveHue.py`.
