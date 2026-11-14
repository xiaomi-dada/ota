# ota — Xiaomi 15 (`dada`)

Update index for the unofficial LineageOS builds of the Xiaomi 15 (`dada`).
The builds are signed with the xiaomi-dada release keys.

The LineageOS Updater on these builds fetches
`https://raw.githubusercontent.com/xiaomi-dada/ota/lineage-24.0/<device>/<incremental>.json`,
where `<incremental>` is `ro.build.version.incremental` of the installed build.
The file lists the update offered to that build, in the format the
[Updater](https://github.com/LineageOS/android_packages_apps_Updater) expects.

The packages are attached to the [releases](https://github.com/xiaomi-dada/ota/releases):

- `…-incremental-from-<incremental>.zip`: what the Updater installs.
- `lineage-….zip.partNN`: the full package, split to fit GitHub's 2 GiB asset limit.
  For a first install, join the parts with `cat lineage-….zip.part* > lineage-….zip`,
  check the result against `SHA256SUMS`, and sideload it from LineageOS Recovery.

Coming from a build signed with other keys (for example a test-keys build), the
installed apps have to be migrated to the new keys first, or the data wiped.
