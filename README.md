# NetNewsWire Help Book

Help book for NetNewsWire, a free and open source RSS reader for Mac and (soon!) iOS. 

The help book will be made available online as a web page. Right now we have English docs but *other languages are welcome*.


Contributing to the help books
------------------------------

If you’d like to write or edit the Help book, translate into another language or help with screenshots, please bring it up on the [NetNewsWire Slack][slack] group in the *#helpbook* channel. We’ll coordinate there.

Every community member is expected to abide by the code of conduct included in the [NetNewsWire Contributing][contrib] page.

[slack]: https://netnewswire.slack.com/join/shared_invite/enQtNjM4MDA1MjQzMDkzLTNlNjBhOWVhYzdhYjA4ZWFhMzQ1MTUxYjU0NTE5ZGY0YzYwZWJhNjYwNTNmNTg2NjIwYWY4YzhlYzk5NmU3ZTc
[contrib]: https://github.com/brentsimmons/NetNewsWire/blob/master/CONTRIBUTING.md


Editing notes
-------------

### Text

Text is written in Markdown. The `.markdown` files will be turned into HTML by a script ([wildcat][wc]) to appear on the NetNewsWire site: <https://ranchero.com/netnewswire/help/>.

[wc]: https://github.com/brentsimmons/wildcat


### Titles

Include the page title by using `@title` on the first line of a document.

	@title Ceci est une titre
	
A top-level page heading (h1) and the HTML page header will be generated automatically.


### Links

Links are made using standard Markdown syntax but when linking to another Help Book page, *no file extension is needed*. Thus,

	[Export](export-opml)

is sufficient to link to the final HTML version of the `export-opml.markdown` page.


### Images

#### Save Location

Put images in the `images` folder at the root of the project.

When linking to images, use a relative path. For example, use:

`../../../images/linked-image.png`

when you’re linking from a page at `mac/5.0/en/page.markdown`.

#### File Name

Because all images are saved in a single directory, it’s best to name files so they’re easy to identify. For example:

`mac-en-check_for_updates.png`

#### Screenshots can wait – for now

It’s not a good idea to take screenshots yet! The UI is still subject to change. That won’t be true for too much longer, but it’s true for now.


Style Suggestions
-----------------

In the English Help Book, we use **strong/bold** text for actions (keys to press, menu items to open) taken by the user:

> Choose **File → Quit** from the menu bar to quit the app.
