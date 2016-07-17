# Learn to move

Best way to feel like learning vim is know how to move around the buffer.
Generally there are more than one way to do that.

* h j k l keys
* arrow keys
* command + operators
* text objects

`Ctrl + G` shows where i am currently in file with ruler at bottom
Asking everytime to show where in file is boring so there is confg. for it.

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

`0` start of the line
`^` first word of the current line
`$` end of the line
`CR`next line
`-` start of prev. line
