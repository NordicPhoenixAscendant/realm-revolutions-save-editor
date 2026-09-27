# Realm Revolutions Save Editor

An unofficial, browser-based editor and analysis dashboard for Realm Revolutions save exports.

The editor is a self-contained static webpage. It has no server component, sends no network requests, and processes pasted save data locally in the browser.

## Safety first

Always preserve an untouched copy of your original save before making changes. An invalid or unsupported edit may prevent the game from loading the modified save correctly.

## Use the editor

1. Open the hosted editor or download and open `index.html` in a modern browser.
2. Export and copy your save from Realm Revolutions.
3. Select **Paste / Load Save**, paste the export into **Advanced / Raw Save**, and select **Decode Text**.
4. Review or edit the stored fields.
5. Select **Re-encode Save**.
6. Copy the resulting text and import it into the game only after preserving your original save.

## Features

- Decodes the nested Base64/INI Realm Revolutions save format.
- Presents game-aware views for kingdom, magic, army, combat, assimilation, revolutions, and inventory data.
- Distinguishes stored values from calculated or inferred values.
- Tracks modified fields and supports field, section, and full-session reversion.
- Preserves unknown fields during a no-edit round trip.
- Re-encodes the edited save in the browser.
- Supports game, scientific, engineering, and raw number displays.
- Shows the next Elf, Druid, Nomad, Warlock, and Cyclops assimilation requirements through the established ranges.
- Estimates total and remaining assimilation BP from each monster's base cost and the working 2.1× per-kill progression.

## Assimilation BP model

Calculated BP figures use the model established from current-game observations:

- The first monster in each biome starts at 5 BP.
- Each successive monster has 15× the previous monster's base BP.
- Each successive kill costs 2.1× the prior kill.
- Totals use unrounded values; the interface formats results to two decimal places in game notation.

These figures are explicitly marked **CALCULATED** in the editor. They are estimates rather than values read directly from the save file.

## Privacy

The published page contains no analytics, telemetry, external scripts, or network requests. Save data remains in the current browser tab unless the user copies it elsewhere. The page does not automatically persist saves in cookies, local storage, or session storage.

## Run locally

No installation or build process is required. Open `index.html` directly in a modern browser.

For local HTTP testing, serve this directory with any static web server and open its local address.

## Publish with GitHub Pages

1. Push these files to a public GitHub repository.
2. Open **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**.
4. Select the `main` branch and `/(root)` folder.
5. Save the setting.

The editor will be published at `https://YOUR-USERNAME.github.io/REPOSITORY-NAME/`.

## Compatibility and limitations

- The editor was built around the currently mapped Realm Revolutions save structure.
- Unknown fields are preserved but may not have friendly labels.
- Some displayed game calculations are inferred from recovered behavior and are labeled accordingly.
- Assimilation requirement counts are established through step 15; the editor does not invent later Cyclops requirements.
- Test edited exports carefully after game updates.

## Contributing

Bug reports and pull requests are welcome. Do not include personal save files in public issues. If a save sample is essential for diagnosis, remove identifying or private information and share the smallest possible reproduction.

## Security reports

Please use the repository's private security-reporting feature for security-sensitive findings instead of posting a public issue.

## Disclaimer

This is an unofficial fan-made tool. It is not affiliated with or endorsed by the developers of Realm Revolutions. Use it at your own risk.

## License

The editor source is available under the MIT License. This license applies only to the original code in this repository and does not grant rights to Realm Revolutions or third-party intellectual property.

