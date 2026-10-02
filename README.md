# uv Example

Initially my goal here was to post a bunch of completed exercises for the book
*Learning Python*, 6th Edition, by Mark Lutz and published by O'Reilly Media.
The idea was to use uv to generate a project where the auto-generated
`__init__.py` would use importlib to dynamically load exercise answers in
modules of the form `chXX.exXX` and then execute the `main()` function inside.
I realized that this was completely over the top and unnecessary but wanted to
document and encode what I learned while doing so here.

First thing my dumb ass did was try to put the `chXX.exXX` modules in the same
directory as `__init__.py`, not having checked `sys.path` first. No, those
were to go in the parent `src`. Here `__init__.py` uses importlib to load
module `foo.bar` and executes its `main()` which just says a brief hello
message.

Next thing I wanted to find out was how to run IPython from uv to test things
with uv's version of Python (Mint is still on 3.10.2 where *Learning Python*
covers features up to 3.12) without writing an actual file and that led me
to [corresponding tutorial
material](https://pydevtools.com/handbook/how-to/how-to-run-the-ipython-shell-in-your-uv-project/).
The tutorial suggested that I add IPython as a development dependency, which
is worth taking into consideration, so I did `uv add --dev ipython`.

`uv run ipython` then works, but the next snafu is that I have code in
`$HOME/.ipython` that makes changes some default NumPy and Pandas display
options to be what I consider more legible in some instances. Of course the uv
installation of IPython doesn't yet know about them. Fixing it was a simple
matter of `uv add numpy pandas`.

\[More to follow???\]
