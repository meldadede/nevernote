# Search Smarter

* Uses regex like syntax, mostly similar to `sed`
* Every meta syntactic character need to be escaped

    \d+ => wrong find me digit and exact plus char
    \d\+ => find me a one or more digit

* use `\v` to auto escape all meta syntactic characters while searching

    nnoremap / /\v

Above config will map normal mode / key to /\v which is handy most of the time.

`/\vyear|ISBN` => or syntax
`/*.Java\&*.line` => and syntax
`/\<year\>` => find only year word
`/\<year` => only find year at start of word
`/year\>` => only find year at end of word

`*` search the word under cursor forward
`#` search the word under cursor backward

## Case Sensitivity

* by default all searches all case sensitive

    :set ignorecase " disable case sensitivity
    :set smartcase  " when searching all lower do case sensitive
                    " when searching mixed do case insensitive
                    
