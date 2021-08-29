# youtube-dlp-bash
**No copying URL! No pressing paste or enter!!*

You select your text, and activate this script by a hotkey shortcut (e.g F9) and **you instantly download the video!**  
No pressing enter or confirmation or whatever bs. Literally 1 button download, couldn't be smoother. No "copy" -> "select input field" -> "paste" -> "enter" on whatever video downloader

```
#!/bin/sh

# Replace /username/ with your username under home directory
# or replace the entire path with wherever you want these videos to be saved.
xclip -o | xargs -r yt-dlp -P "/home/username/videos"
```

Now, you may want to write the URL yourself, or paste it manually, or press enter to confirm the url yourself before downloading.

```
#!/bin/sh

# Give your input to dmenu (bash could work, but ? character triggers zsh globs and other annoying terminal bugs)
targeturl="$(dmenu -p Download </dev/null)"

# Pass targeturl to youtube downloader (works for any kind of video)
yt-dlp -P /home/username/videos "$targeturl"
```

The above works for this, pretty much opens dmenu and whatever you type is passed onto yt-dlp.
Middle mouse button works for pasting, but just use ctrl+Y for pasting onto dmenu, for efficiency (imagine using mouse)  
But if you don't want to paste and enter, not even copy, the optimal is obviously the very first script.

**Obviously map both scripts to hotkeys, so you can download videos effortlessly.**

Ah and ofc, it needs youtube-dl. [youtube-dlp](https://github.com/yt-dlp/yt-dlp) in this case (it is objectively superior)
