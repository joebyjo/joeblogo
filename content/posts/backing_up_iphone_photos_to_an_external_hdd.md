---
title: Backing Up iPhone Photos to an External HDD
date: 2025-10-19
description: A tutorial on how to back up photos on your iphone to a HDD
tags:
  - tricks
  - backup
  - ios
draft: false
cover:
---


### 1. Connect iPhone
- Plug in your iPhone using a USB or USB-C to Lightning cable.
- Unlock your phone and tap **"Trust This Computer"** if prompted.

---

### 2. Open Image Capture
- On your Mac, press `Cmd + Space` → type `Image Capture` → press **Enter**.
- In the left sidebar, click your **iPhone** under “Devices”.

![474AA3804CE6F6FBAA942BFC7802FAA1.png](/images/posts/backing_up_iphone_photos_to_an_external_hdd/474AA3804CE6F6FBAA942BFC7802FAA1.png)

---

### 3. Choose Destination Folder
- At the bottom of Image Capture, locate the **“Import To:”** dropdown.
- Click **“Other…”** and navigate to your external HDD.
- Create a new folder for today’s backup, for example:

```

/Volumes/YourHDD/Backups/iPhone Backup 18-10-25

```

![E7CDD9FEB3D64D0D2747B33FC70CB52C.png](/images/posts/backing_up_iphone_photos_to_an_external_hdd/E7CDD9FEB3D64D0D2747B33FC70CB52C.png)

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

---

### 6. List File Types in Folder (Optional)
Use this Bash command to list all **unique file extensions** in the current folder (recursively):

```bash

find . -type f | sed -n 's/.*\.//p' | sort | uniq

```

**Explanation:**
- `find . -type f` -> Finds all files.  
- `sed -n 's/.*\.//p'` -> Extracts text after the last dot (the extension).  
- `sort` -> Sorts
- `uniq` -> removes duplicates

Example output:
```

HEIC
JPG
MOV 
MP4

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

