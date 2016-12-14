# Vim Search & Replace

## Search

- `n`: Next search
- `N`: Previous search

### Quick Fix

The `quickfix` list.

- `:cnext` & `:cprev`: Cycle through matches 
	- `[q` & `]q`: Above with `vim-unimpaired`
- `:copen`: Show `quickfix` window 
- `:ccl[ose]`: Close `quickfix` window
- `:cb[uffer]`: Populate the `quickfix` list from the results in the current window
- `<CR>`: Go to match
-`:cdo`: Do command to each entry in the quickfix list, e.g., `:cdo s/this/that/g`
-`:cfdo`: Do command to each file in the quickfix list, e.g., `:cdo %s/this/that/g`

## Grep

- `:%s/this/that/gc`: Replace this with that, asking for confirmation each time
- `:g/pid/d`: Delete lines matching pattern
- `:v/pid/d` or `g!/foo/d`: Delete all other lines (`v` is for `in*v*erse`)
- `:g/cfcfcf/p`: Print lines matching pattern
- `:vim[grep] {pattern} %`: Populate the `quickfix` list with matches of the pattern in the current file
- Use `{-}` instead of `*` for non-greedy with `\v`

There's no way to delete s substring, so just use `%s///g`

## Notes

By default vim searches for the literal characters for most punctuation (excluding `[]`, `.`, `*`, others? These need to be normally need to be escaped).

* `/\v`: Very magic search makes most special characters take on their meaning.
* `/\V`: `verynomagic` search, no special characters, everything is interpreted literally.
* `/\c`: Ignore case
* `/\C`: Case sensitive