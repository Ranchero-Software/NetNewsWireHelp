# NetNewsWire Help Book

Help books for NetNewsWire, a free and open source RSS reader for Mac and iOS.

Available on the web at <https://ranchero.com/netnewswire/help/>.



Contribute to the help books
----------------------------

Right now we have English docs but *other languages are welcome*.

If you’d like to write or edit the help books, translate them or help with anything at all, please bring it up on the [NetNewsWire Slack][slack] group in the *#helpbook* channel. We’ll coordinate there.

If you find an error or have any suggestions, you can also [file an issue][issue].

Every community member is expected to abide by the code of conduct included in the [NetNewsWire Contributing][contrib] page.

[slack]: https://ranchero.com/netnewswire/slack
[contrib]: https://github.com/Ranchero-Software/NetNewsWire/blob/master/CONTRIBUTING.md
[issue]: https://github.com/Ranchero-Software/NetNewsWireHelp/issues


How we make the help books
--------------------------

### Text

Write in Markdown, and use HTML when necessary. Save pages as `.markdown` files. [Wildcat][wc] will tranform these into a site of HTML files. We publish the help books on the NetNewsWire site: <https://ranchero.com/netnewswire/help/>.

[wc]: https://github.com/brentsimmons/wildcat


### Titles

Use a `@title` directive to set the page title. This sets it in the HTML page’s head and inserts a top level page heading (h1) when we generate the site:

	@title This cat is wild
	

### Links

Write links with standard Markdown syntax. When you link to another Help Book page, don’t include a file extension:

	[Export](export-opml)

is sufficient to link to the final HTML version of the `export-opml.markdown` page.


### Badges

There are three types of badge you can use to point out important information or to provide guideposts to readers.

An amber/yellow *warning* badge which can be used as such:

	<span class="badge-warning">iOS and iPadOS Only</span>

A blue *distro* badge should be used for pointing out differences between versions of the app.

	<span class="badge-distro">Mac App Store</span>
	<span class="badge-distro">Direct Download</span>

A green *note* badge which could be used for pointers and tips, or new feature notes

	<span class="badge-note">New in 5.1</span>

#### Small versions of badges

If these badges are used inline, it’s better to use their small versions:

	<span class="badge-warning-small">iOS and iPadOS Only</span>
	<span class="badge-distro-small">Mac App Store</span>
	<span class="badge-distro-small">Direct Download</span>
	<span class="badge-note-small">New in 5.1</span>



### Images


#### Save Location for images

Put images in the `images` folder at the root of the project.

When linking to images, use a relative path. For example, use:

	../../../images/linked-image.png

when you’re linking from a page at `mac/5.1/en/page.markdown`.


#### File names

Because all images are saved in a single directory, it’s best to name files so they’re easy to identify. For example:

	mac-en-check_for_updates.png


#### Insert images

All images must include an `alt` attribute whose text is descriptive of the linked image.

You can use the standard Markdown syntax for images:

	![Alt text](/path/to/img.jpg "Optional title")
	
But for more control, it’s best to just use HTML.

	<img src="../../../images/mac-en-share_menu_more_selected.png"
    	alt="A screenshot of the macOS Share menu showing the “More…” item highlighted."
    	class="centeredImage"
    	style="width: 33%;" />

##### Image alignment

You can use the `centeredImage` CSS class to centre your image. You can adjust the size of your image using a relative unit (like `33%` above). You can also specify absolute pixel units with `width` and `height` attributes in the `<img>` tag.

##### Other image effects

- A standardised shadow can be added to an image by adding the `shadowedBox` class
- A standardised border (useful for iOS) can be added by adding the `lightBorder` class


#### Screenshots

Screenshots must be taken on a retina device. We’ll use retina images even for non-retina machines (rather than doing double the number of screenshots). It’s fine.



Help book style
---------------

As much as possible, we follow the [Apple Style Guide][asg] (also available on [Apple Books][asg-ab]).

[asg]: https://help.apple.com/applestyleguide/ "Apple Style Guide"
[asg-ab]: https://books.apple.com/jp/book/apple-style-guide/id1161855204?l=en "Apple Style Guide on Apple Books"



Build the help book site locally
--------------------------------

You’ll need [Wildcat][wc], Ruby and a handful of Gems.

### Step 1. Set up and install Ruby and Gems

Wildcat is written in Ruby, which comes with your Mac. Consider setting up your own Ruby environment with [rbenv][] or [Ruby Version Manager (rvm)][rvm], then install the required gems using the `Gemfile`:

	gem install bundler
	bundle install

At the time of writing, these dependencies are `Kramdown` and `stringex`, if you want to install them manually.

[rbenv]: https://github.com/rbenv/rbenv "rbenv/rbenv: Groom your app’s Ruby environment"
[rvm]: https://rvm.io/ "RVM: Ruby Version Manager - RVM Ruby Version Manager - Documentation"

### Step 2. Set up Wildcat

Download or clone [Wildcat][wc], then copy the project’s contents to the `NetNewsWireHelp` folder. Git will ignore these files. Create a `wildcat_settings` file with these settings:

	@site_name NetNewsWire Help
	@site_url https://ranchero.com/netnewswire/help/
	@output_file_suffix .html
	@output_folder /Users/brent/Sites/NetNewsWireHelp/
	@favicon_url https://ranchero.com/images/nnw_icon_32.png
	@icon_url https://ranchero.com/images/nnw_icon_256.png
	@has_blog false

Change `@output_folder` to whatever makes sense on your machine. On the site, we set `@output_file_suffix` to `(empty-string)`, but `.html` files may be easier to work with.

Note: This doesn’t build a truly self-contained website. We’d like to make that possible in the future.

### Step 3. Build the site

Run `ruby wildcat_publish.rb` to build the site to the folder you specified. You’ll need to provide the web server if you want a fully linked and working site.


Preview help book pages in BBEdit
---------------------------------

To get a general idea of how the pages will look, you can copy the stylesheet to BBEdit’s Preview CSS library (See BBEdit → Folders → Preview CSS). You might want to adjust the body margin and width to make it look a little nicer:

	margin: 2.1rem auto;
	max-width: 55ch;

Image links won’t work because they’d need an extra `../` locally. To make them work without editing the links, you can add an alias/symlink in the pages directory to the `../images` directory.