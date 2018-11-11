```py
  File "nicetry.py", line 1:
    from __future__ import braces
    ^
SyntaxError: not a chance
```

# not a chance

A VSCode-extension-to-be that inserts curly brackets, live, into Python code.
This follows the old and unfunny _"Python **does** have block delimiters!"_ joke:

```py
def is_even(n):
# {
    if n < 0:
    # {
        return is_even(-n)
    # }
    return not n if n < 2 else is_even(n - 2)
# }
```

## Why?
1. Some programmers depend on screen-readers, for which Python's lack of block delimiters poses difficulty.
2. Certain *Sam-I-am*s coming from other languages do not like the idea of semantic indentation (because they
   wouldn't be indenting anyway).
3. Because.

## Who else has done this?
Many. But none AFAIK as a live editor extension!

- [pybraces](http://timhatch.com/projects/pybraces/): The best implementation by far (and adaptable to Python 3
  easily enough), but a touch fuzzy to use and may not play nice with code-analysis tools that don't consider
  encoding.
- [bython](https://github.com/mathialo/bython): Requires a separate transpilation step. Definitely does not
  play nice with code-analysis tools.
- [pindent.py](https://svn.python.org/projects/python/trunk/Tools/scripts/pindent.py): Comes with Python
  and uses nonintrusive comments, but requires a separate transpilation step and delimits blocks using words
  rather than {braces}.

# Stuff
- [ ] Live reformatting to braced Python
- [ ] On-save reformatting from braced Python
- [ ] Preservation of existing comments
