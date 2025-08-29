# Get metadata from Photos

I edit metadata with the Apple `Photos` app, which stores this data in a relatively opaque SQL database (column names are not useful). When metadata is changed, `Photos` does not update the imported files and does not update any associated side car.

My goal is to get metadata from the Apple photos into an XMP file and, if the photo file type can be updated (e.g., `jpg`), to update the phot file, itself.

```shell
osxphotos export [OPTIONS] DEST

osxphotos export  --folder FOLDER  --export-by-date DEST

osxphotos export /path/to/export --sidecar XMP

osxphotos export /path/to/export --dry-run --verbose
```

```shell
EXPORT_DIR=~/updated-2015 ; \
mkdir -p "${EXPORT_DIR}" && \
osxphotos export --dry-run --verbose --album 2015 --sidecar XMP "${EXPORT_DIR}" --exiftool \
&& ls "${EXPORT_DIR}"
```

## [`osxphotos` 0.70.0 Command Line documentation](https://rhettbull.github.io/osxphotos/cli.html)

### `--album <ALBUM>`

Search for photos in album ALBUM. If more than one album, treated as “OR”, e.g. find photos matching any album

### `--sidecar <FORMAT>`  where FORMAT is `xmp` | `json` | `exiftool`

Exports metadata into a sidecar files. `exiftool` uses JSON but is more limited than the `json` format.

### `--export-aae`

Exports adjustments (edits) into a file that can be imported into Photos. For the import to work, the photo and adjustment file names must follow strict rules.

### `--exiftool`

Use `exiftool` to write some of the metadata directly to exported photos.

See also `--exiftool-path <EXIFTOOL_PATH>` and `--exiftool-option <OPTION>`

### `--limit <LIMIT>`

Export at most LIMIT photos. Useful for testing. May be used with –update to export incrementally.

### `--person-keyword`

Use person in image as keyword/tag when exporting metadata. Unclear if this affects `--exiftool`.

### `--jpeg-ext <EXTENSION>`

Make all jpeg files use the same extension.

### `--report <REPORT_FILE>`

Write a report of all files that were exported. The extension of the report filename will be used to determine the format. Valid extensions are: `.csv` (CSV file), `.json` (JSON), `.db` and `.sqlite` (SQLite database). REPORT_FILE may be a template string (see Templating System), for example, `–report ‘export_{today.date}.csv’` will write a CSV report file named with today’s date. See also `–append`.
