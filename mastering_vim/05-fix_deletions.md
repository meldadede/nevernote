# Fix Deletions
Default behavior of vim does not allow you to delete things that you did not
put. So you can only delete things that you inserted. This is sometimes annoying.
But there is an option.

    :set backspace=start  "can delete until start of line
    :set backspace=indent "can delete indentations
    :set backspace=eol    "can delete to previous line

Best way is to use three of them in combination.

    :set backspace=start,indent,eol
