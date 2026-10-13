Power BI file upload options

This repository contains sample Power BI (.pbix) data for Trenzy Interior & Frames. You mentioned the .pbix file is being rejected by the web uploader and you do not want to reduce its size. Below are recommended options to add the .pbix to this repository without shrinking it.

Option A — Recommended: Use Git LFS (track the .pbix in the repo)
1. Install Git LFS on your machine: https://git-lfs.github.com/
2. Clone the repo and enable LFS:
   git clone https://github.com/nachiketl/trenzy-interior-frames-dashboard-data.git
   cd trenzy-interior-frames-dashboard-data
   git lfs install
3. Ensure .gitattributes is present (it is already added in this repo).
4. Add and commit your .pbix:
   git add path/to/your-file.pbix
   git commit -m "Add Trenzy dashboard .pbix via Git LFS"
   git push origin main

Notes:
- GitHub web UI has a file upload limit (around 25 MB). Small files (like ~288 KB) normally upload via the web UI fine — if the UI is rejecting it, try the Git LFS route or use a release asset.
- Git LFS stores the large file content outside normal Git objects and keeps pointer files in the repo. GitHub provides 1 GB LFS bandwidth/storage on free accounts; for larger usage you may need a data pack.

Option B — Upload as a Release asset (good for single binaries)
1. In the repository on GitHub go to "Releases" → "Draft a new release".
2. Fill tag and release name (e.g., v1.0, initial data) and drag your .pbix file into the asset area.
3. Publish the release. The asset will be hosted by GitHub and you can link to it from README.

Option C — External storage link
If you prefer not to use LFS or Releases, upload your .pbix to Google Drive / Dropbox / OneDrive and add the download link here in the repo (we can add a placeholder file or update the README for you).

If you want, I can:
- Add the .gitattributes file (done). 
- Add these instructions (done).
- Create a draft release and add a release description for you to upload the .pbix through the web UI. (I cannot upload the binary from this chat — you must attach it through the GitHub Releases UI).
- Or, if you paste the small file content or a link, I can add a placeholder and update README with the link.

Tell me which option you want me to continue with and I will take the next step.
