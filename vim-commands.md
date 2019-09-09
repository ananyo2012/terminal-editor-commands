# Vim commands

| Commands | Description |
|---|:---|
| Esc | Command mode |
| i | Insert text |
| :w | Save |
| :x | Save and exit |
| :e! | Go to last saved version |
| :q! | Don't save and exit |
| h | left |
| j | down |
| k | up |
| l | right |
| w | move forward word by word |
| b | move back word by word |
| 0 | move to start of line |
| $ | move to end of line |
| a | append text from current cursor position |
| r | replace the current character |
| x | delete/cut the current character |
| cw | change a word |
| C or c$ | change from cursor to end of line |
| c0 | change from cursor to beginning of line |
| cc | change a whole line |
| dw | cut a word |
| D or d$ | cut from cursor to end of line |
| d0 | cut from cursor to beginning of line |
| dd | cut a whole line |
| u | undo |
| p | paste |
| y | copy (use other suffixes - w,y,0,$ with similar meanings as cut) |
| v | visual mode - select text using arrow keys or h,j,k,l |
| . | repeat last action |
| ~ | convert to upper case |
| o | add new line below current line |
| O | add new line above current line |
| J | join current line and next line |
| G | go to last line of file |
| vi + filename | open a file in the last line |
| vi +n filename | open a file in the nth line |
| Ctrl + F | forward one screen |
| Ctrl + B | scroll backward |
| Ctrl + D | forward half screen |
| Ctrl + U | backward halfscreen |
| \+ | first charater of next line |
| \- | first chracter of previous line |
| :vsplit | vertically split window |
| :split | horizontally split window (Ctrl + w to move between windows) |
| :!command | run command from vim |
| Ctrl + p or Ctrl + n | word completion in insert |
| :ab abbr phrase | Add Abbreviations |
| :unab abbr | Undo abbreviation |
| :set number | Display line number |
| :set nonumber | Hide line number |
| :n | Go to nth line no |
| :$ | Go to last line |

## Opening Multiple files

| vim file1 file2 file3 | opens 3 files in tabbed manner |
|---|---|
| :n | next file |
| Ctrl + ^ | previous file |
| :last | last file |
| :rew | first file |
| :args | all file names |
| :open <filename> | Open a file |
 

| vim -p file1 file2 file3 | opens files in tabbed manner displaying tabs at top |
|---|---|
| :tabn, gt | Next tab |
| :tabp, gT | Previous tab |
| :tabr | first tab |
| :tabl | last tab |
| <n>gt | move to nth tab |
| :tabnew <file> | open a new file in a tab |
| :qa | quit all tabs |

## Search

| Command | Description|
|:---|:---|
| /\<searchterm\>\<ENTER\> | search the searchterm |
| n | go to next search term |
| N | go to previous search term |
| ?\<ENTER\> | search the searchterm backward |
| /\<ENTER\> | search the searchterm forward |
| ?\<searchterm\>\<ENTER\> | Search the searchterm backward |
| :s/oldstring/newstring | replace oldstring with new string |
| :s/oldstring/newstring/g | replace all occurences of  oldstring with new string in the line |
| :1,$s/oldstring/newstring/g | replace all occurences of  oldstring with new string in all lines |
| :%s/oldstring/newstring/g | replace all occurences of  oldstring with new string in all lines |
| :%s/oldstring/newstring/gc | same as above but asks for confirmation |

## Searching methods using ctags

- ctags *.py
- Open tags file `vim tags`
- Press Ctrl + ] to go to the method definition
- :tags to check the tag line no
- Ctrl + t to go back to tags file 
