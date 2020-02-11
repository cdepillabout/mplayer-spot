
mplayer-spot
============

[![Build Status](https://secure.travis-ci.org/cdepillabout/mplayer-spot.svg)](http://travis-ci.org/cdepillabout/mplayer-spot)
[![Hackage](https://img.shields.io/hackage/v/mplayer-spot.svg)](https://hackage.haskell.org/package/mplayer-spot)
[![Stackage LTS](http://stackage.org/package/mplayer-spot/badge/lts)](http://stackage.org/lts/package/mplayer-spot)
[![Stackage Nightly](http://stackage.org/package/mplayer-spot/badge/nightly)](http://stackage.org/nightly/package/mplayer-spot)
[![BSD3 license](https://img.shields.io/badge/license-BSD3-blue.svg)](./LICENSE)

`mplayer-spot` saves your spot when watching movies with `mplayer`.

## Usage

You can use `mplayer-spot` on the command line just as you would use `mplayer`:

```console
$ mplayer-spot Dumb-and-Dumber.mp4
```

This plays the movie just like `mplayer`.

However, if you exit part-way through the movie by pressing `q`, `mplayer-spot`
saves your current location.  Next time you play the same file, `mplayer-spot`
looks up how far into the movie you watched, and starts playing from that
position.


If instance, if you stop the movie after 45 minutes, and play it again with
`mplayer-spot`, it will start from the 45 minute mark.

`mplayer-spot` is convenient if you often watch long movies in parts, and want
an easy way to restart from where you left off.

## How Does `mplayer-spot` Work?

`mplayer-spot` runs `mplayer` in verbose mode, and parses the current position
in the movie.  When exiting, it saves the position in the `~/.mplayer-spot`
directory.

`mplayer-spot` references files by filename, so if you rename a file, you will
not be able to restart from the same position.
