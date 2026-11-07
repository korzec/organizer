# Photo Library Organizer

A browser-based photo library organizer. It scans local folders and previews a `Source / Year` structure based on camera make/model and capture date metadata.

## Use

1. Open the Pages site in current desktop Chrome or Edge.
2. Choose the source library and a separate organized destination.
3. Scan and review the full plan. Export a CSV if you want a separate copy.
4. Apply moves only after reviewing the preview. A JSON restore manifest is written into the destination before the first move.
5. To undo a run, select its manifest, reselect the same source and destination folders, and choose **Restore selected run**. Existing original paths are never overwritten.

File reads and writes happen in the browser. Photos, metadata, and filenames are not uploaded. Camera EXIF is used when available; the app falls back to a meaningful source folder and the file modified date when metadata is missing.

The EXIF parser is bundled locally as `site/exifr.umd.js`; its MIT license is in `site/EXIFR-MIT.txt`.

## Deployment

The GitHub Actions workflow in `.github/workflows/pages.yml` publishes the `site/` directory to GitHub Pages on pushes to `main`. It also configures Pages to use GitHub Actions when repository settings allow it.

After the first successful workflow run, the project page is expected at:

`https://korzec.github.io/organizer/`
