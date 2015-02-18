gentoo-lxc-overlay
==================

gentoo lxc stuff, for my personnal use, hope this could help you

# Status

No problem so far, tell me if you find some

# Install
## add to layman
### add list to layman.cfg
Add https://raw.github.com/gza/gentoo-lxc-overlay/master/overlay.xml<br>
to /etc/layman/layman.cfg<br>
at "overlays :"<br>
sync overlays:<br>

    layman -S

then add overlay:<br>

    layman -a gza-lxc

### Or quick oneLiner for testing...

    layman -o https://raw.github.com/gza/gentoo-lxc-overlay/master/overlay.xml -f -a gza-lxc

## accept keyword for these lxc ebuilds (but not 9999)

    echo "<app-emulation/lxc-9999::gza-lxc ~*" >> /etc/portage/package.accept_keywords
 
## emerge

    emerge -av app-emulation/lxc

# Content

* app-emulation/lxc-9999 <- rebased on main portage ebuild
* app-emulation/lxc-1.1.0 <- rebased on main portage ebuild
* app-emulation/lxc-1.0.7-r1 <- fixed lxc template
with earlier version, gentoo template is broken
* app-emulation/lxc-1.0.7
* app-emulation/lxc-1.0.6
* app-emulation/lxc-1.0.5
* app-emulation/lxc-1.0.3
* dev-lua/alt-getopt-0.7.0
  * Needed by lua useflag

# What is different from others ebuild ?

* maintainer :)
* gentoo template patch (cf https://lists.linuxcontainers.org/pipermail/lxc-devel/2015-February/011391.html)
* container's config and rootfs under /var/lib/lxc/container
 * IMO : This is lxc's data, so this a realy bad idea to put it in /etc

# make a new version (reminder for myself :) )

* cd app-emulation/lxc/
* cp old-version new-version
* ebuild new-version digest
* try it
* egencache --update --repo gza-lxc
* update README
* git stuff: commit push

