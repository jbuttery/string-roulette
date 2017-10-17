String Roulette
===============

Why pick a random number when you can pick an entire string?  This little
Javascript app lets you define lists of strings and get a random selection on
each page load.  You can also click anywhere on the page to get a new random
selection from the current list.

You can create your own lists and switch between them (see the installation
instructions below for details) or just copy `string-roulette.html` anywhere a
Web browser can get to it (note that it does _not_ need to be online) and by
default you can get random numbers from 0-9.

Basic installation
------------------

This program is a self-contained single file that runs entirely as Javascript
in your browser.  You can put it on a Web server if you like, but it will run
just as well locally from your hard disk.

If you're not running on a Web server, you can feel free to delete the file
`index.html`; it's only there as a concession to the fact that most Web servers
want to display a file with that name by default.

Configuration
-------------

The file in its default form probably won't do much for you, unless you really
just want single-digit random numbers.  If you want to randomize other strings,
you'll need to define the lists somewhere.

The recommended way to add new lists is to create a file called `lists.js` and
put them in there; you can use the example file in the `doc/` directory as a
guide.  You can also add the new lists directly into the HTML file; this will
work just as well, but it's not the recommended method since you'll have to
reintegrate your changes any time the base file updates.

Pay close attention to the "icebreakers" list; partially because it's kind of
awesome, but also because it shows a more advanced usage of the list
definition.  Individual list elements can themselves be lists; any list
encountered this way will have its first two elements used as the primary
string and secondary string, respectively.  You can see what this looks like by
simply copying the example file into place and refreshing this:

    .../string-roulette.html?list=icebreakers

...until you get one with a secondary string.  Alternatively, this "numbers"
example will explicitly give you the built-in default list:

    .../string-roulette.html?list=numbers

Unfortunately, there is no way to edit the style (CSS) of the page without just
editing the main file directly; I really wanted to keep this thing as one file
by default, and I don't know of a way to put inline CSS and also support a
local CSS file without requiring the local file to be peppered through with
`!important`, and the idea of encouraging that makes me sad.
