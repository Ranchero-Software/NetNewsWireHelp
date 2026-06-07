@title How to View Account Stats
@template page.html

On the Mac, choose Window > Account Stats to open the window. You’ll see something like this:

![Screenshot of the Account Stats window](images/mac-account-stats.png)

On iOS (TBD…)

(The Account Stats feature was added in NetNewsWire 7.1, released in July 2026.)

## What the fields mean

Each account has its own row, and, if you have multiple accounts, there’s also a Totals row.

The Databases column adds up the sizes for all the databases for that account.

<div class=info>
Most accounts have three databases. DB.sqlite3 is the big one — it contains articles and status. FeedSettings.db contains metadata about feeds, and Sync.sqlite3 contains sync database that has been queued up to send.
</div>

The rest of the fields tell how many of each are stored by that account.

<div class=warning>
Note that some of the numbers may not match what you see in the main window. For instance, there are cases where the database may have status records for old articles that no longer appear in the main window — which means unread counts might not match. This is not an error! This is the app behaving normally.
</div>

## How to Compact Your Databases

You can sometimes save a little space and make your databases faster by clicking or tapping the Vacuum Databases button.

This is generally *not* going to have a noticeable effect on performance, but it could in some cases. Also, it usually won’t shrink your databases by much, but it could.

After vacuuming, which will take a few seconds, the table is refreshed with updated numbers.

<div class=info>
Technical detail for the curious: this command runs SQLite’s <code>vacuum</code> command on each of the databases.
</div>

## How to Refresh the Table

Click or tap the Refresh button and the app will re-scan the databases and update the numbers in the table.
