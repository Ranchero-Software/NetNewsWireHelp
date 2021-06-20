@title Micro.blog feeds
@template nnw5ios_en.html

We’re fans of [Micro.blog][mb], an open microblogging platform.

Because it’s built on open web standards like RSS, apps like NetNewsWire can be used to read posts and articles there.

[mb]: https://micro.blog



Subscribe to your own Micro.blog timeline
--------------------------------------------

To use NetNewsWire to read the Micro.blog posts that appear in your timeline (*not your posts*), use this feed format:

	https://micro.blog/feeds/USERNAME.xml

If your Micro.blog username is *abigail*, then you’d subscribe to:

	https://micro.blog/feeds/abigail.xml


### Subscribe to another user’s timeline

You can use the same technique to subscribe to *someone else’s* timeline.

This is not their posts – for that, see below. This allows you to see the posts from people *they* follow. For example, if you want to read the same timeline as Miraz Jordan reads, subscribe to:
	
	https://micro.blog/feeds/miraz.xml	



Subscribe to someone’s Micro.blog posts
---------------------------------------

To read the posts made to someone’s Micro.blog feed, you use a slightly different feed address:

	https://USERNAME.micro.blog/feed.xml

If you want to keep up with what Miraz is posting to her own blog, subscribe to:

	https://miraz.micro.blog/feed.xml



Other Micro.blog feeds
----------------------

There’s a lot happening at Micro.blog. It’s no surprise they offer feeds to let you keep up with the community there.

- Featured photos: `https://micro.blog/feeds/photos.json`
- [Discover][d] (featured posts): `https://micro.blog/posts/discover`

Posts in the Discover section of Micro.blog are categorised using [emoji][tagmoji]. Each of those has a separate feed as well:

	https://micro.blog/posts/discover/EMOJI
	
You’ll need to know the word which corresponds to an emoji, so consult the [Discover emoji][tagmoji] list. Some may be obvious, like 🐈 or 🐱:

	https://micro.blog/posts/discover/cats

*Meow!*



Get more help
-------------

Full documentation of Micro.blog’s feeds are available at their [feeds help page][mb-feeds].


[d]: https://micro.blog/discover
[tagmoji]: https://help.micro.blog/2018/tagmoji/
[mb-feeds]: https://help.micro.blog/2017/api-feeds/
