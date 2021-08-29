# Youtube-Overlay-Toggler
A simple javascript that helps you turn on/off the YouTube Video Progress/Toolbars.

# Instruction
- Copy the following code to your browser's bookmark toolbar
```
javascript: (function () {
    var goaway = ".ytp-gradient-bottom,.ytp-gradient-top,.ytp-chrome-top,.ytp-chrome-bottom,.ytp-ce-element,.video-ads .ytp-ad-player-overlay > div:not(.ytp-ad-player-overlay-skip-or-preview){display:none;}";
    var inner = (typeof document.body.style.WebkitAppearance == "string") ? "innerText" : "innerHTML";
    var tags = document.getElementsByTagName("style");
    var shouldHide = true;
    for (let i = tags.length - 1; i >= 0; i--) {
        if (tags[i][inner] == goaway) {
            tags[i].parentNode.removeChild(tags[i]);
            shouldHide = false;
        }
    }
    if (shouldHide) {
        if ("\v" == "v") {
            document.createStyleSheet().cssText = goaway;
        }
        else {
            var tag = document.createElement("style");
            tag.type = "text/css";
            document.getElementsByTagName("head")[0].appendChild(tag);
            tag[inner] = goaway;
        }
    }
})();
```
- Rename the created bookmark (if desired)

# To USE the script
- Goto any Youtube video
- Click the bookmark to turn off the overlays
- Click the bookmark again to restore the overlays
