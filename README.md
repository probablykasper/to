# to

Pretty simple bash script that converts audio, video and image files using [FFmpeg](https://ffmpeg.org) and [ImageMagick](https://imagemagick.org).

# Install
Get [Homebrew](https://brew.sh/) if you don't already, and run this command:
```
brew tap spectralkh/tap
brew cask install to
```

# Usage
Running `to` shows the help message:
```
Usage:
    to <format> [options] <file1> [file2...]

Options:
    format           Format to convert to.
    --formats        List all supported formats.
    -v, --verbose    If you love logs.
    -h, --help       Show this help message.

    Video/audio formats support FFmpeg options (see $ ffmpeg -h).
    Image formats support ImageMagick options (see $ man magick).
    Long FFmpeg/ImageMagick arguments need quotes, like "-ac 128k".
```

# Formats
Running `to` shows the supported formats:
```
Video formats:
    mp4
    mov
    webm

Audio formats:
    mp3      320kbps. Custom bitrate example: mp3:128
    flac
    aac
    aiff
    ogg

Image formats:
    jpg      95 quality. Custom quality example: jpg:75 (0-100)
    jp2      95 quality. Custom quality example: jp2:75 (0-100)
    png
    webp     95 quality. Custom quality example: webp:75 (0-100)
```

# Dev Instructions

If you're just interested in the `to` script, you can steal that from `bin/to`.

## Publishing to Homebrew

If you want to publish to Homebrew, you can create your own "tap" repository with a "cask" file for this script. You may want to Google how all that works.

For reference, my tap can be found [here](http://github.com/spectralkh/homebrew-tap).

### url
Your cask file needs a url pointing to a tarball. You can create the tarball by running the following in your repository:
```
git archive HEAD -o dist/to-VERSION.tar.gz
```
Your url should then be `https://github.com/USER/REPO/raw/master/dist/to-VERSION.tar.gz` (with your own USER/REPO/VERSION, of course).

### sha256
After putting a url in your cask file, you need a sha256 string too. Homebrew will generate it for you when you run this inside your tap repository:
```
brew fetch ./Casks/to.rb
```
