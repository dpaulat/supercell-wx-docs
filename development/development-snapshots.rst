Development Snapshots
=====================

Development snapshots are the fastest way to try new features that have been
merged and validated in CI, without replacing your stable installed release.

Snapshots are published as build artifacts from the CI workflow:

`supercell-wx CI workflow <https://github.com/dpaulat/supercell-wx/actions/workflows/ci.yml>`_

Prerequisites
-------------

* A GitHub account (required to download workflow artifacts)
* Basic familiarity with selecting the branch and build you want

Important: Prefer Portable/Binary Artifacts
-------------------------------------------

For development testing, use the platform binary artifact (for example,
``supercell-wx-windows-vs2026-x64``) instead of the installer artifact.

The installer artifact (``supercell-wx-installer-windows-vs2026-x64``)
installs over your release version and can replace your stable install.

How to Download a Snapshot
--------------------------

#. Open the CI workflow page:

   `https://github.com/dpaulat/supercell-wx/actions/workflows/ci.yml <https://github.com/dpaulat/supercell-wx/actions/workflows/ci.yml>`_

#. Select the workflow run you want.

   * The ``develop`` branch is generally the most stable development snapshot.
   * Other branches may contain in-progress feature work.

   .. image:: images/development-snapshots-01-actions.png
      :alt: GitHub Actions page showing the workflow selector, branch selector, and snapshot runs

#. Open the selected run and choose **Summary**.

   .. image:: images/development-snapshots-02-ci-summary.png
      :alt: CI run page with Summary highlighted

#. In the artifacts list, download the artifact that matches your OS/platform.

   .. image:: images/development-snapshots-03-artifacts.png
      :alt: CI artifacts list with the Windows binary artifact highlighted

#. Extract the downloaded artifact and run Supercell Wx directly from the
   extracted files.

Windows Snapshot Usage (Portable)
---------------------------------

If you download ``supercell-wx-windows-vs2026-x64``:

#. Extract the archive to a folder of your choice.
#. Open the extracted ``bin`` folder.
#. Run ``supercell-wx.exe``.

This does not update your installed release version.

Artifact Name Reference
-----------------------

.. list-table::
   :header-rows: 1
   :widths: 35 65

   * - Package
     - Artifact Name
   * - Linux x64 AppImage
     - ``supercell-wx-appimage-linux-gcc-13-x64``
   * - Linux x64 Binaries
     - ``supercell-wx-linux-gcc-13-x64``
   * - Linux x64 Flatpak
     - ``supercell-wx-flatpak-linux-gcc-13-x64``
   * - Linux arm64 AppImage
     - ``supercell-wx-appimage-linux-gcc-13-arm64``
   * - Linux arm64 Binaries
     - ``supercell-wx-linux-gcc-13-arm64``
   * - Linux arm64 Flatpak
     - ``supercell-wx-flatpak-linux-gcc-13-arm64``
   * - macOS (Apple Silicon)
     - ``supercell-wx-macos-arm64``
   * - macOS (Intel)
     - ``supercell-wx-macos-x64``
   * - Windows x64 Installer
     - ``supercell-wx-installer-windows-vs2026-x64``
   * - Windows x64 Binaries (recommended for snapshot testing)
     - ``supercell-wx-windows-vs2026-x64``

Troubleshooting
---------------

* Artifact download option missing:
  Sign in to GitHub, then reload the run summary page.
* Unsure which build to use:
  Start with ``develop`` and pick the binary artifact for your platform.
