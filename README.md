# ly2video

ly2video is a Python script which converts music represented by a [GNU
LilyPond](http://lilypond.org) file into a video containing a
horizontally scrolling music staff which is synchronized with a
MIDI-generated audio rendering of the music.

## Examples

Here are some [examples of videos generated by ly2video](http://www.youtube.com/playlist?list=PLfRwjd606WZlxRU_kaUPagX3-Uv-SYRMH).

## Requirements

**Please also read the Installation section below before you start installing anything!**

* GNU LilyPond >= 2.15.41 (needs [`one-line-breaking`](http://www.lilypond.org/doc/v2.17/Documentation/notation/one_002dline-page-breaking) support)
* FFmpeg (if you are on Ubuntu or Debian, see first see [issue 32](https://github.com/aspiers/ly2video/issues/32))
* TiMidity++
* Python 2.7
* Python's [pip installer](http://www.pip-installer.org)
    * on SUSE-based distributions: `sudo zypper install python-pip`
    * on Debian/Ubuntu-based distributions: `sudo apt-get install python-pip`
* ALSA development libraries (`python-midi` requires these to build)
    * on SUSE-based distributions: `sudo zypper install alsa-devel`
    * on Debian/Ubuntu-based distributions: `sudo apt-get install libasound-dev`

## Installation

Ensure that you have installed the above dependencies.  Finally,
[ly2video requires some specific Python modules](https://github.com/aspiers/ly2video/blob/master/pip-requires.txt) -
**do NOT install these manually!** (unless you are a Python expert.)
They can be installed system-wide via:

    sudo pip install -r pip-requires.txt

or for the current user via:

    pip install --user -r pip-requires.txt

You can optionally protect against the risk of installation of these
Python modules destabilising any other Python applications you may
use, by isolating them in a virtual environment using
[`virtualenv`](http://www.virtualenv.org/en/latest/).  The most
convenient way to do this is via
[`virtualenvwrapper`](http://virtualenvwrapper.readthedocs.org/en/latest/).
Once you have `virtualenvwrapper` installed, it's as simple as:

    mkvirtualenv ly2video
    pip install -r pip-requires.txt

It is a known issue that [ly2video is currently missing a proper
installation process](https://github.com/aspiers/ly2video/issues/38),
so you should run it from within the source tree.

## Usage

Run `./ly2video.py --help` to display usage information.

## Support, bugs, development etc.

Please check the [issue tracker](https://github.com/aspiers/ly2video/issues)
for known issues, and if yours is not there, please submit it.
I can't guarantee that I'll be able to fix it, or even respond,
but I'll try, and even if I can't help, this is github, so anyone else
can potentially help you out too.

If you know how to fix a problem or contribute an enhancement, you are
extremely welcome to [fork this repository](https://github.com/aspiers/ly2video/fork_select),
commit your fix, and then send a [pull request](https://help.github.com/articles/using-pull-requests)!

## Acknowledgements

Huge credits for the initial implementation go to Jiří "FireTight"
Szabó, who wrote it as part of his Bachelor's degree.  If you are
lucky enough to understand Czech, you can read his thesis on ly2video
in the `doc/thesis/` subdirectory, or
[online](http://is.muni.cz/th/359741/fi_b/text_prace.pdf) :-) Work on
an English translation has begun and is being tracked in
[issue 15](https://github.com/aspiers/ly2video/issues/15) but is
unlikely to be finished any time soon unless someone else volunteers
to help out.

Very big thanks also to Jan Nieuwenhuizen not only for co-inventing
LilyPond in the first place, but also for helping me implement the
complete revamp of the synchronization algorithm, which should be
much more robust than the previous one.

And finally of course, much gratitude to the many great people who
have contributed to LilyPond over the years.  This would not have
been possible without you.

## License

ly2video is released under the [GNU GPL v3](http://www.gnu.org/licenses/gpl.html).
