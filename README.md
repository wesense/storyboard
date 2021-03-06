[![Latest Version](https://img.shields.io/pypi/v/storyboard.svg)](https://pypi.python.org/pypi/storyboard/)
[![Supported Python versions](https://img.shields.io/pypi/pyversions/storyboard.svg)](https://pypi.python.org/pypi/storyboard/)
[![Supported Python implementations](https://img.shields.io/pypi/implementation/storyboard.svg)](https://pypi.python.org/pypi/storyboard/)
[![Download format](https://img.shields.io/pypi/format/storyboard.svg)](https://pypi.python.org/pypi/storyboard/)
[![License](https://img.shields.io/pypi/l/storyboard.svg)](https://pypi.python.org/pypi/storyboard/)
[![Development Status](https://img.shields.io/pypi/status/storyboard.svg)](https://pypi.python.org/pypi/storyboard/)
[![Docs](https://readthedocs.org/projects/storyboard/badge/?version=latest)](https://storyboard.readthedocs.io/)
[![Build Status](https://travis-ci.org/zmwangx/storyboard.svg?branch=master)](https://travis-ci.org/zmwangx/storyboard)
[![Windows Build Status](https://ci.appveyor.com/api/projects/status/github/zmwangx/storyboard?branch=master&svg=true)](https://ci.appveyor.com/project/zmwangx/storyboard)
[![Coverage Status](https://coveralls.io/repos/github/zmwangx/storyboard/badge.svg?branch=master)](https://coveralls.io/github/zmwangx/storyboard?branch=master)

*Main documentation on Read the Docs:* http://storyboard.rtfd.org

*Caution: Development has been deferred indefinitely as of July
23, 2015. However, contributions are welcome, and the maintainer will
review pull requests in a timely manner.*

`storyboard` is an [FFmpeg](https://ffmpeg.org/)-based customizable video storyboard generator with metadata reporting directly embedded in the generated images. Reported metadata fields include, but are not limited to, title, filename, file size, SHA-1 digest, container format, duration, pixel dimension, display aspect ratio (DAR), scan type (progressive, interlaced, or telecined), frame rate, and per-stream metadata (type, codec, profile, dimensions, bitrate, etc.). Scroll down for a few sample storyboards.

Note that this README only provides an overview and summary of the topics listed below. For more details, follow the main article link in each section.

## Structure of this document

* Background
* Installation and dependencies
* Command-line usage
* Sample storyboards
* Issues
* License

## Background

*Main article:* http://storyboard.rtfd.org/en/latest/index.html

`storyboard` was inspired by the storyboards I frequently encounter on video-sharing Internet forums, mostly generated by proprietary video players. Those storyboards often come with video/file metadata bundled, which I see asn a great all-in-one solution for video sharing, saving one the labor of typing multiple console commands, copying and pasting output, and worrying about the forum's crappy formatting. However, I, for one, dislike proprietary players. Also, those storyboards are usually ugly and uninformative, using stupid fonts and lacking crucial information that hackers look for (e.g., hash). Therefore, I developed this customizable storyboard generator for hackers.

## Installation and dependencies

*Main article:* http://storyboard.rtfd.org/en/latest/install.html

### Dependencies

* [FFmpeg](https://ffmpeg.org/). Check the [official downloads page](https://www.ffmpeg.org/download.html) for installation options. On OS X you may install FFmpeg via [Homebrew](http://brew.sh) or [MacPorts](https://www.macports.org/). The former is recommended.

* [Pillow](https://python-pillow.github.io/). This dependency will be picked up by `pip` when you install `storyboard`, but you also have to satisfy the external dependencies, especially `libjpeg` and `libfreetype`. See [the official installation guide](https://pillow.readthedocs.io/en/latest/installation.html) for details. (Satisfying external dependencies is very important on Linux, where no wheel distribution is provided on PyPI.)

### Installation

End users should use `pip`:

```
pip install storyboard
```

Developers should clone the git repo for docs, tests, and more.

## Command-line usage

*Main article:* http://storyboard.rtfd.org/en/latest/cli.html

This package installs two console scripts, `metadata` and `storyboard`. You may find documentation of both using the `-h,--help` option. Extensive documentation is also available for both:

* `metadata` CLI reference: [metadat-cli.html](http://storyboard.rtfd.org/en/latest/metadata-cli.html);
* `storyboard` CLI reference: [storyboard-cli.html](http://storyboard.rtfd.org/en/latest/storyboard-cli.html).

By the way, the default invocation is really simple (for both): just supply one or more video paths.

## Sample storyboards

*Main article:* http://storyboard.rtfd.org/en/latest/sample.html

[![](https://i.imgur.com/OIx20KQ.jpg)](https://i.imgur.com/gtBArx7.jpg)

[![](https://i.imgur.com/WB2N0Rh.jpg)](https://i.imgur.com/Ujgsznc.jpg)

## Issues

*Main article:* http://storyboard.rtfd.org/en/latest/issue.html

### Reporting

Please use the GitHub issue tracker: <https://github.com/zmwangx/storyboard/issues>.

### Known issues

* CJK support in filename and title? In short, no.

* Found a codec you need that has no binding in ``metadata.py`` and leads to stupid output? File an issue or open a pull request. Please link a sample file if it is not commonly seen and cannot be encoded by FFmpeg.

* `ffprobe` might report the wrong duration for certain VOB or other videos, which screws up the whole thing. As a fallback, you can use the option `--video-duration` of `storyboard`. Note however that this option is extremely slow, and improving it is on my list.

## License

This package comes with `SourceCodePro-Regular.otf` as the default font, which is subject to the license of the [Source Code Pro font family](https://adobe-fonts.github.io/source-code-pro/). See `LICENSE.txt` for details.

Source code in this package is released under [the MIT license](http://opensource.org/licenses/MIT).
