# Sejda PDF Desktop

[Sejda PDF Desktop][uri-sejda-desktop-home] is a versatile, fast, user-friendly
PDF management software for editing, merging, splitting, compressing, and
signing PDFs offline.

[uri-sejda-desktop-home]: https://www.sejda.com/desktop/ "Productive PDF Software That You'll Love to Use"

## Local Development — Build and Install Flatpak

Install `flatpak`, `flatpak-builder` and `git`, then run:

```shell
# Ensure Flathub remote exists for the current user
$ flatpak remote-add --if-not-exists --user flathub https://flathub.org/repo/flathub.flatpakrepo

$ git clone https://github.com/flathub/com.sejda.Sejda.git
$ cd com.sejda.Sejda/

$ flatpak-builder build --force-clean --install-deps-from=flathub --install --user com.sejda.Sejda.yaml
```

To uninstall:

```shell
$ flatpak uninstall --delete-data --user com.sejda.Sejda
```

To clean up build artifacts and Flatpak state:

```shell
$ rm --force --recursive .flatpak-builder/ build/
$ flatpak uninstall --unused --user
$ flatpak remote-delete --user flathub
```

## Additional Flatpak Debug Logging

Set `SEJDA_DEBUG_ENABLED="true"` when launching the Flatpak so the application
prints some information that may be needed when reporting issues.

```shell
$ export SEJDA_DEBUG_ENABLED="true"
$ flatpak run com.sejda.Sejda
```
