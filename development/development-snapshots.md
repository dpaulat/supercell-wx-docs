I made an informal discord post on how to grab the latest features from the development snapshot via the CI actions workflow. Please formalize it and turn it into a more polished help document in .rst format for publishing on Read The Docs.

Include images for information, as well as a mapping of the artifact names to what they are. Encourage users to not use the installer, as it will install over the release version.

## Informal Discord Post

The best way to grab features that are nearing ready (or have been merged into the development snapshot) is here: https://github.com/dpaulat/supercell-wx/actions/workflows/ci.yml. You'll need a GitHub account. The develop branch is most stable, but you can see other branches from various users implementing new features.

If there's a specific snapshot you wanted to download, click the title, and you'll see a whole bunch of artifacts. Select the one that's right for your OS. Probably supercell-wx-windows-vs2026-x64. Unzip it and run it from the bin/ folder. Note, this does NOT update your install. If you want to do that, download supercell-wx-installer-windows-vs2026-x64 instead.

## Images

development/images/development-snapshots-01-actions.png
- GitHub Actions page with boxes and informational text around the following:
    1. Actions Workflow
    2. Branch
    3. Snapshot / Build / Pull Request

development/images/development-snapshots-02-ci-summary.png
- Overview page for the CI Actions workflow, with a box around the "Summary" link

development/images/development-snapshots-03-artifacts.png
- List of artifacts with a box around supercell-wx-windows-vs-2026-x64 as an example.

## Mapping

Linux x64 AppImage	supercell-wx-appimage-linux-gcc-13-x64
Linux x64 Binaries	supercell-wx-linux-gcc-13-x64
Linux x64 Flatpak	supercell-wx-flatpak-linux-gcc-13-x64
Linux arm64 AppImage	supercell-wx-appimage-linux-gcc-13-arm64
Linux arm64 Binaries	supercell-wx-linux-gcc-13-arm64
Linux arm64 Flatpak	supercell-wx-flatpak-linux-gcc-13-arm64
macOS (Apple Silicon)	supercell-wx-macos-arm64
macOS (Intel)	supercell-wx-macos-x64
Windows x64 Installer	supercell-wx-installer-windows-vs2026-x64
Windows x64 Binaries	supercell-wx-windows-vs2026-x64
