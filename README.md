# cdj-zfs

#### An unofficial portage repository with occasional super-recent ZFS ebuilds.

Contains ebuilds for the `sys-fs/zfs` and `sys-fs/zfs-kmod` packages.

At the time I make these ebuilds (which is, admittedly, not often), these
ebuilds are typically the latest commits in the OpenZFS project that have
passed all of their Continuous Integration (CI) tests.

Typically these ebuilds are made when it is required for ZFS to support
a kernel version that is more recent than what the Gentoo portage tree's
ZFS ebuilds support, or there is some ZFS feature required that is not
present in the releases of ZFS available from the Gentoo portage repository.

Merging these ebuilds is a bit like merging `sys-fs/zfs-9999` and `sys-fs/zfs-kmod-9999`,
except that each ebuild in this repository (ex: `sys-fs/zfs-2023.01.17`)
is nailed down to a certain commit on a certain date, so attempting to rebuild
the package will be a deterministic operation. (As opposed to the `*-9999`
ebuilds, which will merge a different version of ZFS depending on what commit
the HEAD ref is pointing to.) Also there is a bit more peace-of-mind due to
the selection of commits that pass CI.

To install:
```
eselect repository add cdj-zfs git https://github.com/chadjoan/cdj-zfs-portage-repo.git
eix-update
```

Ebuilds may be removed from this repository once portage complains about them
too much or they no longer build with modern toolchains/dependencies.
(I don't like to remove ebuilds as much as the Gentoo devs do, but I also
don't have the time or ability to maintain ebuilds with old EAPI versions,
and even a low-dependency project like ZFS will eventually end up with
broken dependencies if enough time passes.)

