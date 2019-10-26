# NetNewsWire Help Book

Help book for NetNewsWire, a free and open source RSS reader for Mac and (soon!) iOS. 

The help book will be made available online as a web page. Right now we have English docs but *other languages are welcome*.


Contributing to the help books
------------------------------

If you’d like to write or edit the Help book, translate into another language or help with screenshots, please bring it up on the [NetNewsWire Slack][slack] group in the *#helpbook* channel. We’ll coordinate there.

Every community member is expected to abide by the code of conduct included in the [NetNewsWire Contributing][contrib] page.

[slack]: https://ranchero.com/netnewswire/slack
[contrib]: https://github.com/brentsimmons/NetNewsWire/blob/master/CONTRIBUTING.md


Editing notes
-------------

### Text

Text is written in Markdown. The `.markdown` files will be turned into HTML by a script ([wildcat][wc]) to appear on the NetNewsWire site: <https://ranchero.com/netnewswire/help/>.

[wc]: https://github.com/brentsimmons/wildcat


### Titles

Include the page title by using `@title` on the first line of a document.

	@title Ceci est le titre
	
A top-level page heading (h1) and the HTML page header will be generated automatically.


### Links

Links are made using standard Markdown syntax but when linking to another Help Book page, *no file extension is needed*. Thus,

	[Export](export-opml)

is sufficient to link to the final HTML version of the `export-opml.markdown` page.


### Badges

There are three styles of badges (and associated small sized versions) you can use in pages where needed. You should use `&nbsp;` instead of spaces so that the badges don’t break and wrap.

#### Warnings

<span style="padding: 0.2em 0.5em;font-weight: bold;border: 2px solid #F1A100;border-radius: 6px;background-color: #FFCA00;color: black;">iOS&nbsp;and&nbsp;iPadOS Only</span>

This is produced using the `badge-warning` style.

There’s also an inline `badge-warning-small` style: <span style="padding: 0.2em 0.5em;font-weight: bold;border: 2px solid #F1A100;border-radius: 6px;background-color: #FFCA00;color: black;font-size:1rem;">iOS&nbsp;and&nbsp;iPadOS Only</span>

<span style="padding: 0.2em 0.5em;font-weight: bold;border: 2px solid #008C6D;border-radius: 6px;background-color: #00AF88;color: white;">New&nbsp;in&nbsp;5.1</span>

This is produced using the `badge-note` style.

There’s also an inline `badge-note-small` style: <span style="padding: 0.2em 0.5em;font-weight: bold;border: 2px solid #008C6D;border-radius: 6px;background-color: #00AF88;color: white;font-size: 1rem;">New&nbsp;in&nbsp;5.1</span>

<span style="padding: 0.2em 0.5em;font-weight: bold;border: 2px solid #1E49AF;border-radius: 6px;background-color: #3170DC;color: white;">Mac&nbsp;App&nbsp;Store&nbsp;version</span>

This is produced using the `badge-distro` style.

There’s also an inline `badge-distro-small` style: <span style="padding: 0.2em 0.5em;font-weight: bold;border: 2px solid #1E49AF;border-radius: 6px;background-color: #3170DC;color: white;font-size: 1rem;">Mac&nbsp;App&nbsp;Store&nbsp;version</span>


### Images


#### Save Location for images

Put images in the `images` folder at the root of the project.

When linking to images, use a relative path. For example, use:

	../../../images/linked-image.png

when you’re linking from a page at `mac/5.1/en/page.markdown`.


#### How to name images

Because all images are saved in a single directory, it’s best to name files so they’re easy to identify. For example:

	mac-en-check_for_updates.png


#### Using images in pages

All images must include an `alt` attribute whose text is descriptive of the linked image.

You can use the standard Markdown syntax for images:

	![Alt text](/path/to/img.jpg "Optional title")
	
But for better control, it’s best to just use HTML.

	<img src="../../../images/mac-en-share_menu_more_selected.png"
    	alt="A screenshot of the macOS Share menu showing the “More…” item highlighted."
    	class="centeredImage"
    	style="width: 33%;" />

You can use the `centeredImage` CSS class to centre your image. You can adjust the size of your image using a relative unit (like `33%` above). You can also specify absolute pixel units with `width` and `height` attributes in the `<img>` tag.


#### Screenshots

Screenshots must be taken on a retina device. We’ll use retina images even for non-retina machines (rather than doing double the number of screenshots). It’s fine.



Style suggestions
-----------------

In the English Help Book, we use **strong/bold** text for actions (keys to press, menu items to open) taken by the user:

> Choose **File › Quit** from the menu bar to quit the app.

As much as possible, we follow the [Apple Style Guide][asg].

[asg]: https://books.apple.com/jp/book/apple-style-guide/id1161855204?l=en "Apple Style Guide on Apple Books"



Building locally
----------------

You’ll need Wildcat, as previously mentioned. At the top level of this folder you’ll need a `wildcat_settings` file which should look something like this:

	@site_name NetNewsWire Help
	@site_url https://ranchero.com/netnewswire/help/
	@output_file_suffix (empty-string)
	@output_folder /Users/brent/Sites/NetNewsWireHelp/
	@favicon_url https://ranchero.com/images/nnw_icon_32.png
	@icon_url https://ranchero.com/images/nnw_icon_256.png
	@has_blog false

Change `@output_folder` to whatever makes sense on your machine.

Note: this doesn’t build a truly self-contained website. We’d like to make that possible in the future. But at this writing (11 Aug. 2019) the higher priority is shipping NetNewsWire 5.0. :)


### Previewing in BBEdit

To get a general idea of how the pages will look, you can copy the stylesheet to BBEdit’s Preview CSS library (See BBEdit → Folders → Preview CSS). You might want to adjust the body margin and width to make it look a little nicer:

	margin: 2.1rem auto;
	max-width: 55ch;

Image links won’t work because they’d need an extra `../` locally. To make them work without editing the links, you can add an alias/symlink in the pages directory to the `../images` directory.