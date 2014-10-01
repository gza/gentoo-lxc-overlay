gentoo-lxc-overlay
==================

gentoo lxc stuff, for my personnal use, hope this could help you

# Status

No problem so far, tell me if you find some

# Usage
## Add overlay list to layman
Add https://raw.github.com/gza/gentoo-lxc-overlay/master/overlay.xml<br>
to /etc/layman/layman.cfg<br>
at "overlays :"<br>
sync overlays:<br>

    layman -S

then add overlay:<br>

    layman -a gza-lxc

## Or quick oneLiner for testing...

    layman -o https://raw.github.com/gza/gentoo-lxc-overlay/master/overlay.xml -f -a gza-lxc

# unmask these lxc ebuilds

    echo "<app-emulation/lxc-9999::gza-lxc" > /etc/portage/package.unmask
    
# Content

* app-emulation/lxc-9999
* app-emulation/lxc-1.0.6
* app-emulation/lxc-1.0.5
* app-emulation/lxc-1.0.3
* dev-lua/alt-getopt-0.7.0
  * Needed by lua useflag

# What is different from others ebuild ?

* maintainer :)
* lua support (mainly for lxc-top, but not heavily tested)
* cleaner ebuild
* container's config and rootfs under /var/lib/lxc/container
 * IMO : This is lxc's data, so this a realy bad idea to put it in /etc
