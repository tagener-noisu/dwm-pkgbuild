# dwm-git-noisu
My PKGBUILD for [dwm](http://dwm.suckless.org/) based on [this PKGBUILD](https://aur.archlinux.org/packages/dwm-git/) for Arch Build System.

### How to use it:
1. Run `makepkg` to clone dwm repository then remove unnecessary package.
2. Change directory to `./src/dwm`
3. Create git branch named user `git checkout -b user`
4. Apply patches and/or change your `config.h`
5. Commit your changes with `git commit` (don't forget to `git add config.h` first if you change it!)
6. Return to directory where PKGBUILD located
7. Run makepkg with desired flags e.g. `makepkg -si`
