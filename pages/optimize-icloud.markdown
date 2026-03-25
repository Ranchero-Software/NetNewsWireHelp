@title How to Optimize iCloud Syncing
@template page.html

<div class=info>
<p>This page describes features introduced in NetNewsWire 7.0.4. If you’re using an earlier version, see <a href=https://netnewswire.com/help/iCloud.html>iCloud Syncing Limitations and Solutions</a>.</p>
</div>

iCloud syncing can be slow and your iCloud storage may be large, especially if you’ve been using NetNewsWire with iCloud syncing for a long time.

Here’s how to fix it:

## Step 1. Turn off syncing of unread content

iCloud syncing stores the content of starred articles — which makes sense, because you absolutely want those to be there wherever you run NetNewsWire.

But it also stores the content of *unread* articles. It’s for a good reason: it ensures that none of your copies of NetNewsWire is missing an article. The problem, though, is that it also means that your iCloud storage may be high and your iCloud syncing may be slow.

In NetNewsWire 7.0.4 we added an option to turn *off* syncing the content of unread articles. If you’re already using iCloud syncing with NetNewsWire, the option is on, because that’s how it’s worked all this time.

But for new users the option is off by default, however, since we think it’s better to turn it off.

### How to turn it off

Open the Settings window on Mac and navigate to your iCloud account settings. Make sure the checkbox for “Sync content of unread articles” is off, as in the screenshot.

![Mac screenshot showing iCloud account settings with checkbox off for syncing content of unread articles](images/mac-icloud-sync-content-unread-articles-setting.png)

Also turn it off in your iOS device or devices. Open the settings screen in NetNewsWire, navigate to your iCloud account, and make sure the switch for “Sync Content of Unread Articles” is off, as in the screenshot.

![iOS screenshot showing iCloud account settings with checkbox off for syncing content of unread articles](images/ios-icloud-sync-content-unread-articles-setting.png)

<div class=warning>
<p><strong>Important:</strong> you should turn it off on each computer and device where you use NetNewsWire, or the ones you miss will continue to upload the content of unread articles to iCloud.</p>
</div>

## Step 2. Relax — NetNewsWire is doing automatic cleanups on its own now

We’ve added a new weekly background iCloud storage cleanup.

It doesn’t necessarily do a full cleanup each time — that’s because, for longtime NetNewsWire + iCloud syncing users, there’s a lot to clean up, and it’s best to spread this out so it doesn’t just hog everything while it’s running.

But longtime iCloud users should find, over time, that the cleanup has improved sync times and decreased iCloud storage.

You can stop here! You don’t have to do anything else to optimize iCloud syncing and storage, if you’re willing to let the weekly cleanup do its thing over time.

But if you’re impatient — which we totally get — you can clean it all up right now. Read on…

## Step 3. Open your iCloud Storage Stats in NetNewsWire

On Mac, from the Window menu, choose **iCloud Storage Stats**. The window will start running a scan of your iCloud storage, which may take several minutes to complete.

![Mac screenshot showing iCloud Storage Stats window with a completed scan. Includes statistics for status records and article content records.](images/mac-icloud-storage-stats.png)

Here’s what it’s showing:

### Status Records

These are quite small: just an ID and enough data to say whether an article is read or unread and starred or not. It’s okay that there are many thousands of these — that’s expected.

In the screenshot there are 12,138 total, 5 starred, 237 unread, and 11,901 read. Totally normal.

There are also, however, 876 listed as stale: those can be deleted, since they no longer apply to any articles still in your NetNewsWire.

(Stale is defined as created six months ago or more and without a corresponding article still in your local database.)

Even though it’s a good idea to get rid of the stale status records, that’s not where the real savings will come from. (But we will get rid of them anyway, in a moment.)

### Article Content Records

These are the big ones, the actual content of each article. You want this number to be as small as possible — ideally it’s just the content of your starred articles and nothing more.

In the screenshot, you can see that there are 7,734 total articles stored, which is a lot. Just five are starred. There are 200 unread and 7,534 read.

Why so many for *read* articles? Don’t we *not* sync content for read articles?

Well, they were unread at first, and that’s why their content got uploaded to iCloud. Then at some point they were marked as read, but the article content wasn’t deleted from iCloud. (Yes, there is code to do that, but there are cases where that can be missed.)

So now you know why it’s using so much iCloud storage.

Here’s what to do about it:

## Step 4. Clean up your iCloud storage

Click the Clean Up button at the bottom of the window. It will first confirm that you want to do the cleanup, then it will run it. This too may take many minutes to complete.

Once it’s finished, you will see something like this:

![Mac screenshot showing the iCloud Storage Stats window having completed a cleanup and reporting stats.](images/mac-icloud-storage-cleanup.png)

It shows you exactly how many of each category were deleted, and then gives you the option to go back to your scan or run a new scan (if you have time).

If you were to run another scan, it should look something like this:

![Mac screenshot showing the iCloud Storage Stats window after rescanning after running a cleanup.](images/mac-icloud-storage-scan-after-cleanup.png)

Note how in the screenshot there are zero stale status records, zero unread article content records, zero read content records, and zero orphaned content records. Everything that could be deleted was deleted. Note how the remaining content records are just for starred articles. This is exactly what you want.

At this point you may have deleted way more than half of NetNewsWire’s iCloud storage. (It was about 90% in testing, but mileage will vary.) From here on sync times should be faster and iCloud storage needs should be lower. (Remember that NetNewsWire now does a weekly cleanup too, so it can stay on top of this.)

But you can always come back to this window and check your stats again and run a cleanup if you need to.

## Note about errors

If an error is reported during a scan or cleanup, it may just be a network error or iCloud asking you to slow down. It’s okay to run the cleanup, get an error, wait a while, then run it again, until finally there’s nothing left to clean up.

If you think an error is more serious, please report it on the [bug tracker](https://github.com/Ranchero-Software/NetNewsWire/issues) or on the [NetNewsWire forum](https://discourse.netnewswire.com). Thanks!

