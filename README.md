# uv Example

Initially my goal here was to post a bunch of completed exercises for the book
*Learning Python*, 6th Edition, by Mark Lutz and published by O'Reilly Media.
The idea was to use uv to generate a project where the auto-generated
`__init__.py` would use importlib to dynamically load exercise answers in
modules of the form `chXX.exXX` and then execute the `main()` function inside.
I realized that this was completely over the top and unnecessary but wanted to
document and encode what I learned while doing so here.
