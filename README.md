# Trenzy Interior & Frames — Dashboard Data

This repository contains dummy dashboard data and the Power BI (.pbix) file for Trenzy Interior & Frames.

If you want to upload your .pbix file directly (recommended):

1. Upload as a Release asset (recommended for single binary files)
   - Open this link to create a new release in your repo:
     https://github.com/nachiketl/trenzy-interior-frames-dashboard-data/releases/new
   - Fill **Tag version** (e.g., `v1.0`) and **Release title** (e.g., `Initial PBIX data`).
   - Drag & drop your `.pbix` file into the “Attach binaries by dropping them here or selecting them” box.
   - Click **Publish release**.
   - After publishing, copy the download link and add it to this README or to `docs/UPLOAD_POWERBI.md` if you want.

2. (Alternative) Upload via local Git + Git LFS
   - If you prefer the file tracked in the repository history, use Git LFS. See `docs/UPLOAD_POWERBI.md` for step-by-step instructions.

3. (Alternative) Upload via the repository web UI (Add file → Upload files)
   - For very small `.pbix` files this can work, but Releases are more reliable for binary assets.

Notes
- I prepared `.gitattributes` and `docs/UPLOAD_POWERBI.md` in this repo to support Git LFS and to give you instructions.
- Because `.pbix` is a binary, uploading it as a release asset keeps your repo history clean and is easy for sharing.

Next step: Click the link above (or go to the repo → Releases → Draft a new release), drag your .pbix file into the assets area, and publish the release. Tell me when you've uploaded it and I will add a download link into the README or create a release note for you.
