# `vim` Search & Replace

## Search

- `n`: Next search
- `N`: Previous search

### Quick Fix

The `quickfix` list.

- `:cc`: Go to currently selected `quickfix` item
- `:cnext` & `:cprev`: Cycle through matches 
	- `[q` & `]q`: Above with `vim-unimpaired`
- `:copen`: Show `quickfix` window 
- `:ccl[ose]`: Close `quickfix` window
- `:cb[uffer]`: Populate the `quickfix` list from the results in the current window
- `<CR>`: Go to match
- `:cdo`: Do command to each entry in the `quickfix` list, e.g., `:cdo s/this/that/g`
- `:cfdo`: Do command to each file in the `quickfix` list, e.g., `:cdo %s/this/that/g`

Populating the `quickfix` window with an arbitrary command:

	:cexpr system('rg --vimgrep pathForResource -g "*.swift" \| grep -v func')

(Note a bug in `nvim` seemingly stops this from working multiple times in one session.)

## `grep`

- `:%s/this/that/gc`: Replace this with that, asking for confirmation each time
- `:g/pid/d`: Delete lines matching pattern
- `:v/pid/d` or `g!/foo/d`: Delete all other lines (`v` is for `in*v*erse`)
- `:g/cfcfcf/p`: Print lines matching pattern
- `:g/cfcfcf/yank A`: Yank matching lines to register `A`

## `vimgrep`

- `:vim[grep] {pattern} ##`: Search `args` (`##`) and populate the `quickfix` list with the results.
- `:vim[grep] {pattern} %`: Populate the `quickfix` list with matches of the pattern in the current file
- `:bufdo vimgrepa[dd] {pattern} %`: Populate the `quickfix` list with matches of the pattern in the current file

Add `| copen` to the end of any of the above to show the `quickfix` list.

## `windo`

- `windo %s/foo/bar/g`: Replace in all open windows