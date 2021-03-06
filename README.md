#About

Vranger is a bash hack that creates a single vim session which is bound to a
[ranger](http://ranger.nongnu.org/) instance.  The user can suspend the vim
session at any time and drop back into the previous ranger context.  This is
accomplished by running a persistent vim server inside a tmux session.

See
[here](https://github.com/ranger/ranger/blob/master/examples/vim_file_chooser.vim)
for an alternative approach.

Multiple vranger instances can be run in parallel.

#Installation

Vranger requires ranger, tmux, and vim.  When vim supports client/server
communication via X11, it will use that to pass the commands.  When vim
client/server support is not available, the commands are passed by the tmux
send-keys facility.

Both the vranger and vrim scripts should be in your PATH.

In Arch Linux, you can install via the included PKGBUILD.

#Usage

Just run `vranger`.

By default, the `<Leader>q` mapping is used to suspend vim.  You should be able
to use the `VRANGER_DETACH` environment variable to change this behavior.  For
example, in bash you could try:

    VRANGER_DETACH="q" vranger

Please note that if you'd like to open a file in your vim session using the
`:open_with` command, you should specify `vrim` as your editor instead of
`vim`.  This is because vranger works by wrapping vim in the vrim script and
passing that to ranger as the default editor.

#Tabs

Vranger's default behavior is to open new files in separate vim buffers. If
you'd like new files to be opened in tabs, use the `VRANGER_USE_TABS`
environment variable: `VRANGER_USE_TABS=1 vranger`.

#Contributors

send-keys/OS X support contributed by @juliekoubova
