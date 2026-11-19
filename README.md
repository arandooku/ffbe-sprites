# Final Fantasy Brave Exvius sprites

57,791 sprite files exported from [DaddyRaegen/ffbe_asset_dump](https://github.com/DaddyRaegen/ffbe_asset_dump)
(FFBE GL/JP asset dump; 3,953 unit forms and 3,599 monster icons).

No jsDelivr: this repository is larger than jsDelivr's 50 MB package limit, so load files from
`https://raw.githubusercontent.com/arandooku/ffbe-sprites/v1/<file>` (CORS enabled, pin the tag).

## Layout

Sprite sheets and icons keep the upstream folder names:

- `unit_animated/`
- `unit_icons/`
- `unit_illustrations/`
- `unit_assets/`
- `monster_animated/`
- `monster_assets/`
- `monster_icon/`
- `animated_gifs/`
- `regional_units/`
- `vc_frame/`

`index.json` lists every file as `[file, name, category, id]` and every category with counts.
Animation frames are already assembled as GIFs in `animated_gifs/`.

| category | files |
|---|---|
| unit-animation | 37,968 |
| unit-sprite-sheet | 3,953 |
| unit-icon | 3,953 |
| unit-illustration | 3,952 |
| monster-sprite-sheet | 3,628 |
| monster-icon | 3,596 |
| unit-extra | 463 |
| monster-illustration | 113 |
| monster-asset | 93 |
| regional-unit | 66 |
| vision-card-frame | 6 |

## Names

Unit names come from `catalog/unit_master.json`. Monster names are not published in the
source dump, so they use `Monster <id>`. Sprite sheets, icons and illustrations are the
original game files; © Square Enix. For fan use.

## Example

```js
const base = "https://raw.githubusercontent.com/arandooku/ffbe-sprites/v1/";
const manifest = await (await fetch(base + "index.json")).json();
const [file, name, category] = manifest.entries[0];
const url = new URL(file, base).href;
```
