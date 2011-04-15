source-highlight-solarized
==========================

**NOTE:** This is seriously a work in progress. It's not done. If you want it
to get done, please contribute!

A set of [Solarized][1] .style and .outlang files for [GNU Source-highlight][1]. I
made this parimarily for pretty source highlighting when using [less][2]. See
below for less-specific instructions.

[1]: http://ethanschoonover.com/solarized
[2]: http://www.gnu.org/software/src-highlite/
[3]: http://en.wikipedia.org/wiki/Less_(Unix)


Installation
------------
1.  Install Source-highlight using your preferred method (build it yourself
    [according to the manual][3] or use a package manager, e.g. `apt-get
    install source-highlight` or `brew install source-highlight`).

2.  Run `source-highlight-settings`. This will tell you where your *datadir* is
    and give you a chance to change it (you won't need to, but note the path).

3.  You have two options now:
    1.  Copy (or symbolic link) the \*-solarized.style and \*-solarized.outfile
        files to *datadir* and invoke them manually with Source-highlight's `-f`
        and `--style-file` options (a good option if you're only going to use
        Source-highlight with less.
  
    2.  Overwrite the old files, e.g. copy `esc-solarized.style` over
        `esc.style` and `esc-solarized.outlang` over `esc.lang` (or remove the
        original files and symlink the solarized files).

[4]: http://www.gnu.org/software/src-highlite/source-highlight.html#Installation


Using with less
---------------
To automatically Source-highlight files when using less, just add the following
lines to your `.bashrc`:

    export LESSOPEN="| source-highlight -f esc-solarized --style-file=esc-solarized.style -i %s -o STDOUT"
    export LESS=" -R "

Or, if you overwrote/removed the original `*.style` and `*.outlang` files:

    export LESSOPEN="| source-highlight -f esc -i %s -o STDOUT"
    export LESS=" -R "

Now use less as usual and supported files will be highlighted.


Extras
------
Look in `extras/` for an updated `ruby.lang` file, because Source-highlight's
original was sorely lacking. Copy or symlink this to *datadir* just like the
other files. The included file still needs work. Feel free to...


CONTRIBUTE!
-----------
I'm a noob with Source-highlight. Any help would be appreciated. See the
[Source-highlight docs][4] for information on its lang, outlang, and
style syntaxes.

[5]: http://www.gnu.org/software/src-highlite/source-highlight.html


TODO
----
* Implement light as well as dark color schemes.
* Figure out the correct ANSI codes for bold/italic on the terminal and how to
  use them in `esc-solarized.outlang`.
* Implement other `*.outlang` files.
* Make it as pretty as [vim-colors-solarized][5] in as many cases as possible.

[6]: https://github.com/altercation/vim-colors-solarized
