# Themes for the Author's bench

Pictures for the start page of the [Author's bench](https://github.com/pnenzi/authorbench), grouped by theme.
The bench installs them from **Preferences › Start page › Themes to install**. It can also install a theme from a
`.zip`, from the address of a `.zip`, or from a GitHub repository (`owner/repo`).

| Theme | Pictures | |
|---|---|---|
| Infinite library | 32 | the halls of an endless library, in sepia and in colour |
| Ukiyo-e | 20 | ten places and ten feasts of the world as Japanese woodblock prints |

## What a theme is

A theme is a `.zip` (or a folder) that holds its pictures (JPEG, PNG or WebP) and a `theme.json` file:

```json
{
 "format": 1,
 "id": "ukiyo-e",
 "name": "Ukiyo-e",
 "version": "1.0.0",
 "author": "Paolo Nenzi",
 "license": "",
 "description": "Ten places and ten feasts of the world as Japanese woodblock prints.",
 "pictures": [
  {"file": "venice_sunset.jpg", "caption": "Venice at sunset", "dates": "", "on": true},
  {"file": "midsommar_sweden.jpg", "caption": "Midsummer in Sweden", "dates": "06-19..06-26", "on": true}
 ]
}
```

- `caption` is the text of the button at the top right of the start page.
- `dates` holds the festive days, written month-day and repeated every year: `12-25`, or `12-20..01-06` across the new
  year, or several separated by commas. On those days the start page shows only the festive pictures of the day.
  Leave it empty to show the picture on every day.
- `on: false` installs the picture without including it.

A package may also hold a `README` and a `LICENSE`. Anything else is refused: programs, links, and paths outside the
package. A picture may be at most 30 MB, and a whole package at most 400 MB.

The bench makes such a package from any theme of its own: **Export as a package**.

## The catalogue

`catalogue.json` lists the themes ready to install:

```json
{"format": 1, "themes": [
 {"id": "ukiyo-e", "name": "Ukiyo-e", "version": "1.0.0", "author": "Paolo Nenzi", "license": "",
  "description": "...", "count": 20, "cover": "covers/ukiyo-e.jpg",
  "url": "github:pnenzi/authorbench-themes@ukiyo-e-1.0.0/ukiyo-e-1.0.0.zip"}
]}
```

- `url` is where the package is: `github:owner/repo@tag/file.zip` (a file of a release), the address of a `.zip`, or
  `owner/repo` (the latest release of that repository).
- `cover` is a small picture for the gallery. The bench draws it as a pencil sketch.

To publish a new version, raise `version` in `catalogue.json`, upload the `.zip` to a release tagged `<id>-<version>`,
and point `url` to it. The bench then offers the update.

Another catalogue can be used instead of this one: set `themes_catalogue` in the settings of the bench.
