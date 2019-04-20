# to

Pretty simple bash script that converts audio, video and image files using [FFmpeg](https://ffmpeg.org) and [ImageMagick](https://imagemagick.org).

# Install
TBA

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

    Video/audio formats support FFmpeg options (see $ ffmpeg -h).
    Image formats support ImageMagick options (see $ man magick).
    Long FFmpeg/ImageMagick arguments need quotes, like "-ac 128k".
```

## Formats
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
    jpg      100 quality. Custom quality example: jpg:75 (0-100)
    jp2      100 quality. Custom quality example: jpg:75 (0-100)
    png
    webp
```
