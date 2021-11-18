# to

Pretty simple bash script that converts audio, video and image files using [FFmpeg](https://ffmpeg.org) and [ImageMagick](https://imagemagick.org).

## Install
Get [Homebrew](https://brew.sh/) if you don't already, and run this command:
```
brew cask install probablykasper/tap/to
```

## Usage
Running `to` shows the help message:
```
Usage:
    to <format> [options] <file1> [file2...]

Options:
    format           Format to convert to.
    --formats        List all supported formats.
    -v, --verbose    If you love logs.
    -h, --help       Show this help message.

    Prefix arguments with - to pass them directly to
    FFmpeg or ImageMagick, like --ac -128k.
```

## Formats
Running `to` shows the supported formats:
```
Video formats:
    mp4
    mp4-h265
    mov
    webm

Audio formats:
    mp3      320kbps. Custom bitrate example: mp3:128
    flac
    aiff
    ogg

Image formats:
    jpg      90 quality. Custom quality example: jpg:75 (0-100)
    jp2      90 quality. Custom quality example: jp2:75 (0-100)
    png
    webp     90 quality. Custom quality example: webp:75 (0-100)
    gif
```

## Dev instructions

### Release new version

If you want to publish to Homebrew, you can create your own "tap" repository with a "cask" file for this script. You may want to Google how all that works. For reference, my tap can be found [here](http://github.com/probablykasper/homebrew-tap).

1. Create a tarball of your repo by running the following:
    ```
    git archive HEAD -o dist/to-VERSION.tar.gz
    ```
2. Create a GitHub release with the release notes and attach the tarball
3. Your cask file needs a url pointing to the tarball.

    The url should be in this format: `https://github.com/USER/REPO/raw/master/dist/to-VERSION.tar.gz`
4. After putting a url in your cask file, you need a sha256 string. Homebrew will geenrate it for you when you run this inside your tap repo:
    ```
    brew cask fetch ./Casks/to.rb
    ```
5. Update `CHANGELOG.md`
