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

## Commands

Enter command mode with: `C-b :`

- Detach a session: `detach`
- List sessions: `list-sessions`
- Attach a session: `attach -t [session-id]`
- Rename a session: `rename-session [new-session-id]`
