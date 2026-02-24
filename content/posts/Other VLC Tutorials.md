---
title: "Other VLC tutorials"
date: 2025-10-19
description: "a tutorial"
draft: false
tags: ["VLC", "how-to", "diy"]
keywords: ["VLC", "media"]
---


### To add subtitles to video

- drag and drop `.srt` or `.vtt` file onto video
- to sync subtitles go to  `window > track syncronization > subtitles track sync`
- can also use `h` and `j` keys during playtime to delay subtitles

### Launch vlc from terminal

1. open terminal and execute `code ~/.zshrc` 
2. add alias by adding the following to the file
```
alias vlc=/Applications/VLC.app/Contents/MacOS/VLC
```

3. save and close the file and run the following in terminal
 ```
source ~/.zshrc
```

4. restart terminal session and run `vlc` to ensure it worked

[Wiki](https://wiki.videolan.org/Command-line_interface/)


### Make a shortcut to play a radio station/a stream

1. make `xyz.sh` using following command in terminal
```
$ code xyz.sh
```

2. add the following code to it and save it
```
#!/bin/bash
/Applications/VLC.app/Contents/MacOS/VLC -I rc "https://stream.radiojar.com/nhq0vcqwuueuv?_=644092"
```

3.  change the mod of the file to make it executable
```
$ chmod +x xyz.sh
```

### Increase Video buffer while sreaming

1. press `cmd + ,` and then `show all
2. go to `stream output` and increase `stream output muxer caching`  to the amount of video to buffer eg. 5000ms = 5s