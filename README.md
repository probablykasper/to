# to

Pretty simple bash script that converts audio, video and image files using [FFmpeg](https://ffmpeg.org) and [ImageMagick](https://imagemagick.org).

# Install
Get [Homebrew](https://brew.sh/) if you don't already, and run this command:
```
brew tap spectralkh/tap
brew install to
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
    jp2      95 quality. Custom quality example: jpg:75 (0-100)
    png
    webp
```

# Dev Instructions

If you're just interested in the `to` script, you can steal that from `bin/to`.

If you want to publish your own version to Homebrew, you have to create your own "tap" with a "formula" for this script. You may want to Google how all that works.

My tap can be found [here](http://github.com/spectralkh/homebrew-tap).

### Create the tarball for the Homebrew formula
```git archive HEAD -o dist/to-<VERSION>.tar.gz```
The url for your formula will then be `https://github.com/<USER>/<REPO>/raw/master/dist/to-1.0.0.tar.gz`

### Generate the SHA256 for the Homebrew formula
```brew fetch ./Formula/to.rb```
