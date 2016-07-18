# Learn to move

Best way to feel like learning vim is knowing how to move around the buffer.
Generally there are more than one way to do that.

* h j k l keys
* arrow keys
* command + operators
* text objects

`Ctrl + G` shows where i am currently in file with ruler at bottom
Asking every time to show where I am in the file is boring so there is confgiuration
option for it in your `vimrc`

    set ruler "always show the ruler

## Word Motions

Using regular hjkl for moving around is sometimes time consuming and vim have
better methods for alternatives.

`w` jump to the start of next Word
`b` jump to the start of previous Word
`e` jump to the end of word
`ge`jump to the end of previous word

> First three will be most frequently used

There is also uppercase version of these commands that move by word (which actually
will humans think what word is)

Motions for moving between and within lines.

`0` start of the line
`^` first word of the current line
`$` end of the line
`CR`next line
`-` start of prev. line


Moving by paragraph

`}` move to next paragraph
`{` move to previous paragraph

Moving start and end of file

`G` move to end of the file
`gg` move to start of the file
`<NUMBER>G` move to line given by NUMBER


## Matching Parenthesis

Vim allows you to move between matching pairs.
Default setting allows you to move between `{}`, `[]`, `()`

Adding your own matching pairs

    set matchpairs += <:>, <<:>>

    
