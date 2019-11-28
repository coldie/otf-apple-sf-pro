# otf-apple-sf-pro

This is an [Arch Linux](https://archlinux.org/) package that downloads
and bundles the SF Pro font from
[Apple](https://developer.apple.com/fonts).

The package build script relies on
[p7zip](https://p7zip.sourceforge.net/) to extract the fonts from
inside the cpio payload inside the pkg file inside the dmg file that
Apple provide for download and then installs the fonts into
`/usr/share/fonts/OTF`.

If you use this font you may also want the other Apple fonts:
 * [New York®](https://github.com/coldie/otf-apple-newyork)
 * [SF Mono](https://github.com/coldie/otf-apple-sf-mono)
 * [SF Compact](https://github.com/coldie/otf-apple-sf-compact)

These are assigned to a group: `apple-fonts`

## Versioning

The upstream does not appear to version the fonts although there have
been variations of the downloadable files over the years. Therefore
this package uses a simple numeric version (0, 1, 2...) that increments
whenever the source files change.

## Installation

1. Clone this repository

```bash
    cd /usr/src
    git clone https://github.com/coldie/otf-apple-sf-pro.git
```

2. Make and install the package

```bash
    cd otf-apple-sf-pro
    makepkg -si
```

## Installation (AUR)

Coming soon...

## License

The typeface is licensed to registered third-party developers for the
design and development of applications for its platforms.

The package scripts themselves are licensed under the MIT License.

## Links

[Fonts for Apple Platforms](https://developer.apple.com/fonts/)
[Arch Package Guidelines](https://wiki.archlinux.org/index.php/Arch_package_guidelines)

## Legals

New York® is a trademark of Apple Inc., registered in the U.S. and
other countries.

