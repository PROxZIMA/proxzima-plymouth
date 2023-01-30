# Proxzima for [Plymouth](https://gitlab.freedesktop.org/plymouth/plymouth)

![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)[![Arch](https://img.shields.io/badge/Arch%20Linux-1793D1?logo=arch-linux&logoColor=fff&style=for-the-badge)](https://aur.archlinux.org/packages/proxzima-plymouth-git)

> A techno [Plymouth](https://gitlab.freedesktop.org/plymouth/plymouth) theme with crazy ass animation.

| Boot Screen | Shutdown Screen |
| :-------------: | :-------------: |
| ![Boot Screen](./assets/boot.gif)  | ![Shutdown Screen](./assets/shut.gif)  |

## Installation

### AUR

For Arch users, the theme is available from the AUR [here](https://aur.archlinux.org/packages/proxzima-plymouth-git).

1. Install it with your favorite AUR helper: `paru proxzima-plymouth-git`

2. Follow steps 3. and 4. given below.

### Manually

#### Dependencies

- plymouth

> **Note**
>
> `plymouth-x11` is required to preview the theme without rebooting.

1. Clone this repo or download the .zip

```bash
$ git clone https://github.com/PROxZIMA/proxzima-plymouth.git
$ cd proxzima-plymouth
```

2. Copy the whole `proxzima` directory to plymouth themes

```bash
$ sudo cp -r proxzima /usr/share/plymouth/themes
```

3. Follow the steps based on your distribution

    - Arch based distros
    ```
    # check if theme exist in dir
    sudo plymouth-set-default-theme -l

    # optionally you can test the theme by running the script given in repo (plymouth-x11 required)
    sudo ./preview.sh 13

    # now set the theme (proxzima, in this case) and rebuilt the initrd
    sudo plymouth-set-default-theme -R proxzima
    ```

    - Debian(Ubuntu, Kubuntu) based distros
    ```
    # install the new theme (proxzima, in this case)
    sudo update-alternatives --install /usr/share/plymouth/themes/default.plymouth default.plymouth /usr/share/plymouth/themes/proxzima/proxzima.plymouth 100

    # select the theme number and press enter to apply
    sudo update-alternatives --config default.plymouth

    # update initramfs
    sudo update-initramfs -u
    ```

4. Reboot and voila

## Configuration

If you want to use the shutdown animation as boot screen then do the following changes in the `proxzima.script` file.

```diff
- boot = 196;
+ boot = 97;

-   flyingman_image[i] = Image("boot-" + i + ".png");
+   flyingman_image[i] = Image("shut-" + i + ".png");
```

## Potential problems and solutions

Never had one but still refer to the following articles.

- https://wiki.archlinux.org/title/plymouth
- https://wiki.ubuntu.com/Plymouth

For scripting: https://www.freedesktop.org/wiki/Software/Plymouth/Scripts/

## Credits

- [Roger Truttmann](https://twitter.com/RogerTruttmann): The creator of the animation 🙌. Follow him on [Twitter](https://twitter.com/RogerTruttmann), [Github](https://github.com/ROGERdotT) and [Lottiefiles](https://lottiefiles.com/roger.t).
- [Archcraft](https://archcraft.io/): The main logo is designed by [@adi1090x](https://github.com/adi1090x).
- [showplymouth.sh](https://github.com/adi1090x/plymouth-themes): Made by [@adi1090x](https://github.com/adi1090x).

## License

[GPLv3 License](LICENSE).
