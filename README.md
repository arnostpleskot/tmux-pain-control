# Tmux Pain Control with Colemak bindings

Tmux plugin for controlling panes. Adds standard pane navigation bindings.

So far, you had to google around and comb other people's dotfiles to find these.
This plugin hopefully makes them more available and "more standard".

Thanks to the Tmux community for "inventing" these bindings. I've merely just
copied them here.

Tested and working on Linux, OSX and Cygwin.

### Bindings

Notice most of the bindings emulate vim cursor movements.

<img align="right" src="/screenshots/pane_navigation.gif" alt="pane navigation"/>

**Navigation**

- `prefix + m` and `prefix + C-m`<br/>
  select pane on the left
- `prefix + n` and `prefix + C-n`<br/>
  select pane below the current one
- `prefix + e` and `prefix + C-e`<br/>
  select pane above
- `prefix + i` and `prefix + C-i`<br/>
  select pane on the right

<br/>

**Note**: This overrides tmux's default binding for toggling between last
active windows, `prefix + i`.
[tmux-sensible](https://github.com/tmux-plugins/tmux-sensible) gives you
a better binding for that, `prefix + a` (if your prefix is `C-a`).

<br/><br/>

<img align="right" src="/screenshots/pane_resizing.gif" alt="pane resizing"/>

**Resizing panes**

- `prefix + alt + m`<br/>
  resize current pane 5 cells to the left
- `prefix + alt + n`<br/>
  resize 5 cells in the down direction
- `prefix + alt + e`<br/>
  resize 5 cells in the up direction
- `prefix + alt + i`<br/>
  resize 5 cells to the right

These mappings are `repeatable`.

The amount of cells to resize can be configured with `@pane_resize` option. See
[configuration section](#configuration) for the details.

<br/><br/>

<img align="right" src="/screenshots/pane_splitting.gif" alt="pane splitting"/>

**Splitting panes**

- `prefix + |`<br/>
  split the current pane into two, left and right.
- `prefix + -`<br/>
  split the current pane into two, top and bottom.
- `prefix + \`<br/>
  split current pane full width into two, left and right.
- `prefix + _`<br/>
  split current pane full height into two, top and bottom.

Newly created pane always has the same path as the original pane.

<br/><br/><br/><br/><br/>

**Swapping windows**

- `prefix + <` - moves current window one position to the left
- `prefix + >` - moves current window one position to the right

### Installation with [Tmux Plugin Manager](https://github.com/tmux-plugins/tpm) (recommended)

Add plugin to the list of TPM plugins in `.tmux.conf`:

    set -g @plugin 'arnostpleskot/tmux-pain-control'

Hit `prefix + I` to fetch the plugin and source it.

You should now have all `pain-control` bindings defined.

### Manual Installation

Clone the repo:

    $ git clone https://github.com/arnostpleskot/tmux-pain-control ~/clone/path

Add this line to the bottom of `.tmux.conf`:

    run-shell ~/clone/path/pain_control.tmux

Reload TMUX environment:

    # type this in terminal
    $ tmux source-file ~/.tmux.conf

You should now have all `pain-control` bindings defined.

### Configuration

You can set `@pane_resize` Tmux option to choose number of resize cells for the
resize bindings. "5" is the default.

Example:

    set-option -g @pane_resize "10"

### Other plugins

You might also find these useful:

- [sessionist](https://github.com/tmux-plugins/tmux-sessionist) - lightweight
  tmux utils for switching and creating sessions
- [logging](https://github.com/tmux-plugins/tmux-logging) - easy logging and
  screen capturing

### License
[MIT](LICENSE.md)
