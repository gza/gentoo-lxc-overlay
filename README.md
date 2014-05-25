gentoo-lxc-overlay
==================

gentoo lxc stuff, for my personnal use, hope this could help you

# Status

Should work, this comment will be removed after more testing

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
* app-emulation/lxc-1.0.3
* app-emulation/lxc-1.0.2
* app-emulation/lxc-1.0.1
* app-emulation/lxc-0.9.0
* dev-lua/alt-getopt-0.7.0
  * Needed by lua useflag

# What is different from others ebuild ?

* offical gentoo template introduced in 1.0
* multi
* lua support (mainly for lxc-top)
* cleaner ebuild
* config and rootfs setuped to /var/lib/lxc
 * IMO : better than having rootfs under /etc
 * I'm searching for a solution to have rootfs in /var and config of container in /etc
