# Self-hosted fonts

Latin woff2 subsets used by `custom.css`.

| Family | License | Source |
| --- | --- | --- |
| Archivo | SIL Open Font License 1.1 | [fontsource/archivo](https://github.com/fontsource/font-files) |
| Source Serif 4 | SIL Open Font License 1.1 | [fontsource/source-serif-4](https://github.com/fontsource/font-files) |

Served at `/fonts/...`. The installed MyST version does not honor `project.static_files`, so CI copies this folder into `_build/html/fonts` after `myst build --html` (same pattern as `files/`).
