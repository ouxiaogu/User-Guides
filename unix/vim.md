`shift v + shift g` 

`gg` : article head 
`GG` : article tail 

`+,$d`: delete line(s) below current line
dd

`:set nu`: show number

`UU`: undo

### set tab

- In a codebase that uses 4 space characters for each indent, here are good settings to start with:
`set tabstop=8 softtabstop=0 expandtab shiftwidth=4 smarttab`
- In a codebase that uses a single tab character that appears 4-spaces-wide for each indent these settings should work:
`set tabstop=4 softtabstop=0 noexpandtab shiftwidth=4`

### read .vimrc


