# tmux

## Concepts

- `client`: A single instance of `tmux` which is attached to a single session at a time.
- `session`: A collection of windows which can be detached and re-attached. Can be connected to by any number of clients (including zero) at any time.
- `window`: A collection of panes which are visible on a single screen.
- `pane`: A single shell instance.

## Splitting Panes

- Split the current pane into two (left and right): `C-b %`
- Split the current pane into two (top and bottom): `C-b "`

## Switching between panes

- Switch to another pane: `C-b [arrow-key]`

## Detaching and reattaching sessions

- Detach a session: `C-b D` and then select session
- Reattach last session: `tmux attach`
- List all sessions (including detached): `tmux list-sessions`
- Attach a specific session: `tmux attach -t [session-id]`

## Windows

- Create a new window: `C-b c`
- Switch to a numbered window (0-9): `C-b [window-num]`
- Switch to next window: `C-b n`
- Switch to previous window: `C-b l`
- Kill the current window: `C-b &`

## Resizing Panes

- Adjust pane size: `C-b M-<arrow>`

## Searching History

- Search history (search up): `C-b [ C-r`
- Search history (search down): `C-b [ C-s`

## Commands

Enter command mode with: `C-b :`

- Detach a session: `detach`
- List sessions: `list-sessions`
- Attach a session: `attach -t [session-id]`
- Rename a session: `rename-session [new-session-id]`

*Note:* `C-b` conflicts with a basic emacs command so you may wish to override the tmux control key.

- Override control key to Alt-b: `set-option -g prefix M-b`

## Plugins

### Resurrect

* Save session: `prefix + C-s`
* Restore session: `prefix + C-r`

