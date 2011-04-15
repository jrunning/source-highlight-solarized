source-highlight-solarized
==========================

A set of Solarized .style and .outlang files for [GNU source-highlight][1]. I
made this parimarily for pretty source highlighting when using [less][2]. See
below for less-specific instructions

[1]: http://www.gnu.org/software/src-highlite/
[2]: http://en.wikipedia.org/wiki/Less_(Unix)

Installation
------------
1. Install source-highlight using your preferred method (build it yourself
  [according to the manual][3] or use a package manager, e.g. `apt-get install
  source-highlight` or `brew install source-highlight`)

2. Run `source-highlight-settings`. This will tell you where your *datadir* is
  and give you a chance to change it (you won't need to, but note the path).

3. You have two options now:
  1. Copy (or symbolic link) the \*-solarized.style and \*-solarized.outfile
    files to *datadir* and invoke them manually with source-highlight's `-f` and
    `--style-file` options (a good option if you're only going to use
    source-highlight with less.
  
  2. Overwrite the old files, e.g. copy `esc-solarized.style` over `esc.style`
    and `esc-solarized.outlang` over `esc.lang` (or remove the original files
    and symlink the solarized files).

[3]: http://www.gnu.org/software/src-highlite/source-highlight.html#Installation

Using with less
---------------
To automatically source-highlight files when using less, just add the following
lines to your `.bashrc`:

    export LESSOPEN="| source-highlight -f esc-solarized --style-file=esc-solarized.style -i %s -o STDOUT"
    export LESS=" -R "

Or, if you overwrote/removed the original `*.style` and `*.outlang` files:

    export LESSOPEN="| source-highlight -f esc -i %s -o STDOUT"
    export LESS=" -R "

Extras
------
Look in `extras/` for an updated `ruby.lang` file, because source-highlight's
original was sorely lacking. Copy or symlink this to *datadir* just like the
other files. The included file still needs work. Feel free to...


Contribute
----------
I'm a noob with source-highlight. Any help would be appreciated.


TODO
----
*
