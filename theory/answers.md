## Regular Expressions

Find regexes that match the following. (e.g. find a single regex that matches
both `antelope` and `antelopes`.)

* Single regex that matches either of these:

    antelope rocks out
    antelopes rock out

### ANSWER:  /antelopes? rocks? out/gi

-----
-----

* Regex that matches either of:

    goat
    moat

  but not:

    boat

### ANSWER:  /m?g?[^b]oat/gi _OR_ /moat|goat/gi

-----
-----

* Regex that matches dates in YYYY-MM-DD format. (Year can be 1-4 digits, and
  month and day can each be 1-2 digits). This does not need to verify the date
  is correct (e.g 33333-33-33 can match).

  2000-10-12
  1999-1-20
  1999-01-20
  812-2-10

### ANSWER:  /[0-9]{1,4}-[0-9]{1,2}-[0-9]{1,2}/g

-----
-----

* The VT-100 terminal (console) outputs text to the screen as it
  receives it over the wire. One exception is that when it receives an
  ESC character (ASCII 27), it goes into a special mode where it looks
  for commands to change its behavior. For example:

      ESC[12;45f

  moves the cursor to line 12, column 45.

      ESC[1m

  changes the font to bold.

  * Come up with regexes for the two above sequences. The one to set the
    cursor position should accept any digits for the row and column. The
    bold sequence need only accept `1` (and is a trivial regex). (ESC is
    a single character which can be represented with `\e` in the regex.)

### ANSWER1:  /\e\[[0-9]+;[0-9]+f/g
### ANSWER2:  /\e\[1m/g
-----
-----