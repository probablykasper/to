## 1.3.1 - 2019 Aug 10
- Fixed mp4 quality

## 1.3.0 - 2019 Aug 10
- Added mp4-h265
- ffmpeg progress will now be shown while converting
- Changed default mp4 settings to be of higher quality
- Fixed a color issue (as long as it exist in 1.2.0, which I'm not sure about)
- Removed aac due to ffmpeg not adding the correct duration metadata

## 1.2.0 - 2019 May 6
- Added webp
- Added gif
- Now only converts the first "frame" of images. For PSDs, this means that the PSD will be converted as a whole
- Added support for passing arguments directly to ffmpeg/magick

## 1.1.0 - 2019 Apr 28
- Fixed png support
- Fixed custom quality jpg:## format not working
- Changed default jpg quality to 95

## 1.0.1 - 2019 Apr 28
- This one shouldn't really exist as it has minor changes. It might have issues too, I don't know.

## 1.0.0 - 2019 Apr 24
- Initial release
