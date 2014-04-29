#About

Vranger is a bash hack that creates a single vim session which is bound to a
[ranger](http://ranger.nongnu.org/) instance.  The user can suspend the vim
session at any time and drop back into the previous ranger context.  This is
accomplished by running a persistent vim server inside a tmux session.

Note that this is a different approach from spawning ranger instances from
within vim, which has proved slow and unreliable for me.

Multiple vranger instances can be run in parallel.

#Installation

Vranger requires ranger, tmux, vim, and bash.  I use it in Arch Linux.
Client/server communication in vim uses X11, so this will not work without an X
server running.  In Arch you can install via the
[AUR](https://aur.archlinux.org/packages/vranger-git/) or the included
PKGBUILD.

By default, the `<Leader>q` mapping is used to suspend vim.  You should be
able to use the DETACH environment variable to change this behavior.  For
example, in bash you could try:

    DETACH="q" vranger

#Usage

Just run `vranger`.

#Bugs

This isn't a pretty hack, but it works well for me.  I'm sure there are plenty
of bugs.
