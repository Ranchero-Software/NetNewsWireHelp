@title How to Find Stale Feeds with the Dinosaurs Window
@template page.html

On your Mac, choose Window > Dinosaurs to open the window. You’ll see something like this:

![Screenshot of the Mac Dinosaurs window](images/mac-dinosaurs.png)

On iOS, open Settings, scroll down to Troubleshooting, then tap Dinosaurs. You’ll see something like this:

<img src=images/ios-dinosaurs.png alt="Screenshot of the iOS Dinosaurs screen" class=iosScreenshot>

(The Dinosaurs feature was added in NetNewsWire 7.1, released in July 2026.)

## How to list stale feeds

On Mac: edit the text field at the top of the window to choose a number of months. (You can also click the stepper.)

On iOS: tap in the months bar.

The default is six months, but you might want to see feeds that haven’t updated in 24 months, for instance.

The table lists feed name, feed URL, account (if you have multiple accounts), date of the last article that the app has in its database, and the last response code the app got for that feed.

In some cases there may not be a last article — this is not an error in the app. It’s just a thing that can happen.

There may also not be a last response code. (Maybe that domain doesn’t exist anymore.)

But when there is a last response code, it can be helpful. These codes are [http response codes](https://www.rfc-editor.org/rfc/rfc9110.html#name-status-codes). Here’s a quick guide to what you’re likely to see:

* 200: feed exists and is responding fine
* 304: feed exists and is fine — it’s just saying there have been no changes since the last check

<div class=info>
A feed can respond with 200 or 304 and still be finished. Old things exist on the web that will never be updated but that still work normally. It’s up to you to judge whether or not these feeds are likely to be finished.
</div>

* 404: feed not found
* 410: feed is gone for real

<div class=warning>
A feed can respond with a 404 and not actually be gone. At this writing, YouTube feeds do that for several hours a day for unknown reasons. (Clearly a YouTube bug.)<br><br>
However, if a feed responds with 410 it’s almost surely gone for good. This is a very deliberate choice on the part of a publisher. (And super rare.)
</div>

## How to Delete a Feed

On Mac: click the Delete button to remove the selected feed or feeds.

On iOS: swipe on the feed, then click the trash button to delete the feed.

## Other Actions

On Mac: see the other buttons at the bottom of the window.

On iOS: swipe to reveal the more menu — the one with the … character.

**Go to Feed** selects the feed in the feeds list. This way you can see what articles are included in the feed.

**Open Home Page** opens the home page of the feed in a web view.

**Copy Feed URL** copies the feed URL of the selected feed or feeds.

## Also Useful

The [Error Log](error-log.html) lists errors downloading feeds, including timeouts and DNS failures and so on. This can be of further help in deciding which feeds to delete.

