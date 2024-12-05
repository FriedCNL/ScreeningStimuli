# ScreeningStimuli
stimuli for the screening experiment with GalleryManager task

## Category code in file names:

All stimuli is named with a pattern: <concept>_id<stimuli_id>_<category_code>.jpb
The category code is 6 digits bool variable indicating if the stimuli has:
```
People
Animals 
Buildings 
Men 
Women
Plants 
```

# How to Use Git LFS to Save Files

Git Large File Storage (Git LFS) is a Git extension designed to handle large files more efficiently by replacing large files in your repository with pointers to their actual storage. This guide explains how to use Git LFS in your project.

---

## 1. Install Git LFS
First, install Git LFS on your machine.

### Installation
- **Windows:** Install via Git for Windows: [https://git-scm.com/](https://git-scm.com/)
- **macOS:** Use Homebrew:
  ```bash
  brew install git-lfs
  ```
- **Linux:** Use your package manager:
  ```bash
  sudo apt-get install git-lfs  # For Ubuntu/Debian
  ```

### Enable Git LFS
After installing, initialize Git LFS in your repository:
```bash
git lfs install
```

---

## 2. Track Large Files
Specify the file types or patterns you want Git LFS to manage. For example, to track all `.csv` files:
```bash
git lfs track "*.csv"
```

This will create or update a `.gitattributes` file in your repository with entries like:
```
*.csv filter=lfs diff=lfs merge=lfs -text
```

Commit the `.gitattributes` file to your repository:
```bash
git add .gitattributes
git commit -m "Track CSV files using Git LFS"
```

---

## 3. Add Large Files
Add the large files to your repository as usual:
```bash
git add large_file.csv
git commit -m "Add large CSV file"
```

When you add a file tracked by LFS, Git replaces the file's content in the repository with a pointer file, while the actual file is stored in LFS.

---

## 4. Push to Remote
Push your repository to a remote server (e.g., GitHub). Ensure the remote supports Git LFS (e.g., GitHub, GitLab, Bitbucket):
```bash
git push origin main
```

Git will upload the large files to the LFS storage backend.

---

## 5. Pull Large Files
When someone clones or pulls the repository, Git LFS will automatically download the actual large files. If they don't have LFS installed, they'll see only the pointer files.

To manually fetch LFS files (if not downloaded automatically):
```bash
git lfs pull
```

---

## 6. Check Tracked Files
List all the files being tracked by LFS:
```bash
git lfs ls-files
```

## 7. Delete local Git LFS files
Delete files from the local Git LFS cache:
```bash
git lfs prune
```
Test out what effect a prune operation will have:
```bash
git lfs prune --dry-run
```
---

## Best Practices
- Use Git LFS for files that are too large for regular Git storage (e.g., videos, datasets, large binaries).
- Avoid using LFS for files that change frequently, as each change is stored as a new object.
- Regularly check LFS storage limits on your hosting provider (e.g., GitHub offers 1 GB for free).

---

## GitHub-Specific LFS Configuration
1. **Enable LFS for your repository on GitHub.** Most repositories have LFS enabled by default.
2. **Check storage usage:** GitHub provides 1 GB of free LFS storage and 1 GB of bandwidth per month. Additional storage can be purchased as needed.

You can monitor usage via the GitHub repository settings under **Settings > Git LFS**.

## Git-LFS tutorial:
https://www.atlassian.com/git/tutorials/git-lfs

---



