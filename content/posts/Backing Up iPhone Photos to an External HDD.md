---
title: "Backing Up iPhone Photos to an External HDD"
date: 2025-10-19
description: "a tutorial on how to back up photos on your iphone to a HDD"
draft: false
tags: ["VLC", "how-to"]
keywords: ["VLC", "media"]
cover: "/images/projects/unnamed.jpg"
---

### 1. Connect iPhone
- Plug in your iPhone using a USB or USB-C to Lightning cable.
- Unlock your phone and tap **"Trust This Computer"** if prompted.

*(Add image: iPhone connected to Mac with “Trust This Computer” prompt)*

---

### 2. Open Image Capture
- On your Mac, press `Cmd + Space` → type `Image Capture` → press **Enter**.
- In the left sidebar, click your **iPhone** under “Devices”.

*(Add image: Image Capture window showing iPhone under Devices)*

---

### 3. Choose Destination Folder
- At the bottom of Image Capture, locate the **“Import To:”** dropdown.
- Click **“Other…”** and navigate to your external HDD.
- Create a new folder for today’s backup, for example:

```

/Volumes/YourHDD/Backups/iPhone Backup 18-10-25

```

*(Add image: Image Capture import destination dropdown pointing to external HDD)*

---

### 4. Sort & Select Only New Photos
Image Capture displays all media with thumbnails and dates.

#### Sort by Date
- Click the **“Date”** column header to sort from oldest → newest.
- Scroll until you reach the first date *after your last backup* (e.g., 11 Oct 2024).
- Select all photos from that point onward.
- Click **Import** (or **Import All** if all photos are new).

---

### 5. Wait for Transfer to Complete
Image Capture transfers the **original** files directly from your iPhone.

- File types include `.HEIC`, `.MOV`, `.JPG`, etc.
- No compression  
- No metadata loss  

*(Add image: Image Capture showing transfer progress bar)*

---

### 6. List File Types in Folder (Optional)
Use this Bash command to list all **unique file extensions** in the current folder (recursively):

```bash

find . -type f -name '_._' | sed -n 's/.*.//p' | tr '[:upper:]' '[:lower:]' | sort -u

```

**Explanation:**
- `find . -type f -name '*.*'` → Finds all files containing a dot in their name.  
- `sed -n 's/.*\.//p'` → Extracts text after the last dot (the extension).  
- `tr '[:upper:]' '[:lower:]'` → Converts extensions to lowercase.  
- `sort -u` → Sorts and removes duplicates.

Example output:
```

heic  
jpg  
mov  
mp4

```

---

### 7. Organize by Date Automatically (Optional)
To organize photos into subfolders based on their original capture date:

1. Install **ExifTool** (if you don’t already have it):
```
brew install exiftool
```

2. Run this command:
```
exiftool '-Directory<CreateDate' -d "%Y-%m-%d" /Volumes/YourHDD/iPhone\ Backup\ 18-10-25

```

**Explanation:**
- `'-Directory<CreateDate'` → Moves files into directories based on their creation date.
- `-d "%Y-%m-%d"` → Formats folders by date (e.g., 2025-10-18).
- This results in a structure like:
```
2025-10-18/IMG_1234.HEIC  
2025-10-19/IMG_5678.JPG
```

