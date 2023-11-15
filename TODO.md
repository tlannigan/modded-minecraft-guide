# TODO

**Higher priority**

## FTB App UI Screenshots

Text-form documentation is great, but some users are more visual
and capturing/cropping a few screenshots from the FTB App could be
very helpful.

For example, we have instructions guiding users on how to access
e.g. instance logs manually.  While this is more than okay for
the technically able, point-and-click instructions as a
complimentary extra might be an idea.

So, in the case of directing a user to locate a crash report or
`latest.log` for a specific instance within the app, there could
be a screenshot/s showing how to navigate the context menus next
to the green play button of every instance where the `crash-reports`
and `logs` directories can be quickly opened.

**Lower Priority**

## Directing users to launcher instance logs/data**

When it comes to directing users to where the FTB App stores its data,
instance files, mod configs, etc., there will possibly be multiple
occurances of *Open File Explorer, navigate to `<PATH>` and then...*.

With this kind of boilerplate in mind, and the desirability of having
instructions for the three OSs the FTB App supports, it should be
relatively simple to script a Python pre-processor[1] to transform the
source of this book, reducing the need for lots of
similiar-yet-slightly-different instructions on files to snag,
pastebins to upload them to, etc.

[1] <https://rust-lang.github.io/mdBook/for_developers/preprocessors.html>

## Debugging Minecraft with VisualVM and other tools

This is an advanced topic and might be overkill, but before I burnt out
last time, I bodged together
[this](https://gist.github.com/ukmcplyr/3b39f568beb191b798aed32be640c5b4)
poor excuse for a tutorial when jikuja was helping users debug an old bug
in the app.

Naturally, it never got finished. And the nice-ish screenshots that
accompanied it now exist only as dead links.  But if another such bug
manifests, it could be worth a dusting off and adding to the book.

<!--
vim: ts=2 sw=2 et fdm=marker :
-->
