A tool for generating customizable video storyboards (including metadata), meant to mimic the storyboards generated by various proprietary players, and outperform them by offering more geeky stats and look, more customizability, and best of all, hackability. I've never actually tried a proprietary player with storyboarding feature though (I've always been using `MPlayer`, and later, `mpv`) and I don't bother to install them, so what I'm actually trying to outperform are storyboards generated by those players that are floating around the Web.

## Caution

This is a piece of work in progress. Currently the module is working, but

* Fonts still need some tweaking (currently the default is Source Code Pro Regular at 16px, which is somewhat thin);
* There are unfinished details, e.g., printing of progress information;
* Metadata parsing of streams can be improved (in particular, there's no parsing code for subtitle streams now) — this aspect is highly limited by the range of codecs familiar to me and the fact that I'm parsing the output of `ffprobe` for metadata;
* There's no CLI now (just need to write some `argparse` code);
* The code is not packaged;

etc.

## Example storyboards

Generated from [`0370f9f`](https://github.com/zmwangx/storyboard/commit/0370f9f) with default settings (except that `include_sha1sum` was set to `True`):

![](http://i.imgur.com/8cma36g.jpg)
