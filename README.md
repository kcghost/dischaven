dischaven
=========
Utility for ripping DVDs and Blu-Rays to high quality mp4 format.
Tries to "do what you want" as much as possible.

Install
-------
Just run:
```
make install
```

Uninstall with:
```
make uninstall
```

Requirements
------------
* mplayer
* ffmpeg
* [dvdid](http://dvdid.cjkey.org.uk/)
* curl
* xmlstarlet

The script is also relying on the [OMDb API](http://www.omdbapi.com/). If you use the tool a lot (and hence make a lot of API requests), I suggest becoming a patron or donating.

Usage
-----
Run `dischaven -h` to see full usage details.

Normally you would use `dischaven -p`, which autodetects the rest of the options such as title, name, and crop, then generates a 10 second preview from the middle of the film.
Since the autodetection process takes some time, the command will also give out the full command and options necessary to skip the autodetection e.g. `dischaven -i /dev/sr0 -t 59 -c crop=1920:1024:0:28 -n "Castle in the Sky (1986).mp4" -e "-c:v libx264 -preset veryslow -crf 18 -c:a aac -movflags +faststart"`.
These options may be customized for better size or quality (such as -tune options) or to work around failures in the autodetection.

The default behavior attempts to automatically find the main title of the disc, the best quality english audio track, crop it and rip it to a high quality very portable h264/aac mp4 named in the style of "Name (ReleaseYear).mp4".

Bugs
----
Autodetection of feature title, crop, and title of the film may not always work. The standards regarding such metadata on both blu-ray and dvd are quite deficient, so the script must resort to using lookups, careful guessing, and detection features that are not wholly guaranteed. There will likely always be room for improvement.

TODO
----
I would like to possibly extend the script to support TV series DVDs/Blurays, and maybe music discs and arbitrary video files just to make it an all-in-one tool.

License
-------
[The Unlicense](http://unlicense.org/). This project is truly free, you can do whatever you want with it.
See [License](LICENSE.md) for details.