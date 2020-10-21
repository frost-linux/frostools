frostools
=============

#### Make flags


* PREFIX=/usr
* SYSCONFDIR=/etc

#### Dependencies

##### Buildtime:

* make
* git
* m4

##### Runtime:

- base:
  * openssh
  * rsync
  * haveged
  * os-prober
  * gnupg
  * pacman

- pkg:
  * namcap
  * git-subrepo
  * jq

- iso:
  * dosfstools
  * libisoburn
  * squashfs-tools
  * mkinitcpio
  * grub

#### Configuration

frostools-{base,pkg,iso}.conf are the configuration files for frostools.
By default, the config files are installed in

```bash
/etc/frostools/frostools-{base,pkg,iso}.conf
```

A user frostools-{base,pkg,iso}.conf can be placed in

```bash
$HOME/.config/frostools/frostools-{base,pkg,iso}.conf
```

If the userconfig is present, frostools will load the userconfig values, however, if variables have been set in the systemwide

These values take precedence over the userconfig.
Best practise is to leave systemwide file untouched.
By default it is commented and shows just initialization values done in code.

Tools configuration is done in frostools-{base,pkg,iso}.conf or by args.
Specifying args will override frostools-{base,pkg,iso}.conf settings.

Both, pacman.conf and makepkg.conf for chroots are loaded from

```bash
usr/share/frostools/{makepkg,pacman-*}.conf
```

and can be overridden dropping them in

```bash
$HOME/.config/frostools/
```
