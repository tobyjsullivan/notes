# tmux

## Concepts

- `client`: TK
- `session`: A collection of windows which can be detached and re-attached.
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
- Reattach a specific session: `tmux attach -t [session-id]`
- List all sessions (including detached): `tmux list-sessions`


