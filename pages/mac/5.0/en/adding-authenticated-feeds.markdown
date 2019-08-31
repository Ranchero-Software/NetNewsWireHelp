@title Adding password-protected feeds to NetNewsWire
@template nnw5mac_en.html

You may need to add a feed which requires authentication – a user name and password – to access it.

At this time, *NetNewsWire does not officially support password-protected feeds*, though full support is expected in a future release.


Limited support for authenticated feeds
---------------------------------------

Though password-protected feeds are not officially supported, NetNewsWire can be coerced into accessing them in *some* cases. There are limitations and warnings, however:

- **The user name and password will not be stored in a secure location.**
- ‘Strong’ passwords, such as those with special characters, including spaces will almost certainly *not work*.

Understanding this, the process to add these feeds is no different to [adding a normal public feed](adding-feeds) – only the URL will differ slightly.

### User names and passwords in URLs

You may have been fortunate enough to been given the address to use already including the user name and password. It should look something like this:

	https://lilian:tiger@the-bull.co.uk/private-feeds/bookings.xml

This looks a lot like a normal feed URL, but with some extra stuff at the beginning. That’s the username and password, separated by a colon (`username:password`), followed by the `@` symbol.

You can copy and paste this address into NetNewsWire to add the feed.

### How to build an authenticated feed URL

If you’ve not been given the address, you’ll need to construct it yourself. Imagine you’ve been given this information:

- User name: `pat`
- Password: `organics40`
- Feed address: `https://bridgefarm.co.uk/app/vegboxes.xml`

Begin by entering the `https://` or `http://` as shown below:

<img src="../../../images/mac-en-add_feed_password_http.png"
     alt="A screenshot of NetNewsWire’s add feed sheet with the  protocol entered."
     class="centeredImage"
     width="65%" />

Then enter the user name `pat`, a colon `:` and the password `organics40` like this:

<img src="../../../images/mac-en-add_feed_password_user.png"
     alt="A screenshot of NetNewsWire’s add feed sheet with protocol, username and password entered."
     class="centeredImage"
     width="65%" />

To finish off, enter the `@` symbol into the box, followed by the feed’s URL:

<img src="../../../images/mac-en-add_feed_password_address.png"
     alt="A screenshot of NetNewsWire’s add feed sheet with the final constructed URL entered."
     class="centeredImage"
     width="65%" />

## What if NetNewsWire says there’s no feed at that address?

This could mean that the URL you’ve entered has a mistake. However, you could be encountering a problem with NetNewsWire’s current support for password-protected feeds. As noted above, special characters in the user name or password – like `@`, `#`, `%`, space and others – are not supported.
