Flatpak Repository Hosting
==========================

Supercell Wx publishes a Flatpak OSTree remote on GitHub Pages so users can
install and update with ``flatpak remote-add`` / ``flatpak update`` instead of
downloading ``.flatpak`` bundles from Releases.

Public URLs (GitHub Pages)
--------------------------

Base URL: ``https://dpaulat.github.io/supercell-wx/``

.. list-table::
   :header-rows: 1
   :widths: 40 60

   * - Resource
     - Path
   * - Stable ``.flatpakrepo``
     - ``supercell-wx.flatpakrepo`` (``DefaultBranch=stable``)
   * - Nightly ``.flatpakrepo``
     - ``supercell-wx-nightly.flatpakrepo`` (``DefaultBranch=nightly``)
   * - Public GPG key
     - ``supercell-wx-flatpak.gpg``
   * - OSTree repository
     - ``repo/``

Channels: ``stable`` (GitHub Release published) and ``nightly`` (successful CI
on ``develop`` only). Architectures: ``x86_64`` and ``aarch64``.

User-facing install steps are documented in
:doc:`../getting-started/initial-setup` and
:doc:`development-snapshots`.
