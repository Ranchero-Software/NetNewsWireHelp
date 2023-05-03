@title iCloud Syncing Limitations & Solutions
@template helpBooksIndex.html

# iCloud Syncing Limitations & Solutions

The Problem
-----------

If you are syncing using iCloud and the progress indicator appears stalled with no new articles appearing, you are 
experiencing iCloud syncing being extraordinarily slow. This is most apparent when adding an iCloud account to a new 
device after you have been using iCloud sync on another device for some time.

Apple limits how fast you can access and retrieve updates from their iCloud servers and puts understandable limits in 
place to prevent abuse. This can impact the data we sync for NetNewsWire, especially with an established account with 
history. In our opinion, Apple’s limits are too restrictive, however the cost of iCloud is inexpensive, so I guess 
we are getting what we pay for.


Handling Long Sync Times
------------------------

With Apple’s limits, sync times can take hours and hours as they force limits on data transfer. The exact amount of 
time is dependent on the amount of data you have in iCloud.

Larger numbers of unread articles can cause a lot of data to be stored in iCloud. This is because we have 
to sync the article content of unread items. We have to do this so that if an article has dropped off of the 
RSS feed by the time another device syncs we can still read the article. We do compress the article content 
to make this better. Still, the fewer unread articles that you keep around, the faster syncing will be.

Since iCloud syncing can be frustrating long, we will give you a couple of tips to help.

### Mac

The Mac is pretty straight forward. Just launch NetNewsWire and don't close it until the sync is complete.
If you close it before the sync is complete, you will have to start all over again.

### iPhone & iPad

Dealing with long sync times can be a little tricky on iPhones and iPads. These devices work hard to preserve
battery life and don't work well with long running processes. If you switch away from NetNewsWire or let your
devices display go to sleep, you won't complete a long running sync.

Our advice is do the following procedure right before you go to bed.

1. Go to Settings and set Auto-Lock to Never in the Display & Brightness section.
2. Plug your device in. Because the screen will be on all night it will drain your battery to zero if you don't.
3. Launch NetNewsWire and leave it in the foreground. Don't switch away from NetNewsWire or you will have to start over.
4. Get some sleep.
5. If you have an average amount of data the sync should be done by the time you get up.
6. Reset your Auto-Lock to your preferred setting.

### Go Nuclear

This really is **not** recommended, but if you get desperate, you can start over from scratch.

1. Export an OPML file of your current iCloud account.
2. Delete all iCloud accounts from NetNewsWire on all of your devices.
3. Under Settings, go to your Apple ID and select iCloud. Select Manage Account Storage (Manage... on macOS) and look for
NetNewsWire. Select it and then delete your NetNewsWire data from iCloud.
4. On one device, create a new iCloud account.
5. Import your OPML file from Step 1.
6. When that completes, you can start adding iCloud accounts back to your other devices.

### Look at Alternate Account Types

If you find that iCloud is too slow or just doesn't work for you, we recommend you try one of our Web 
Accounts. We support all the common ones including Feedbin, Feedly, and more. The Web Accounts 
don't have the same bandwidth constraints that iCloud does and can move data much faster.

Many have free tiers of usage and the subscription ones are very reasonably priced. Prices range from about $3 per
month for a basic Web account service to $5 or $6 for the premium ones. The premium ones provide many valuable features 
not possible to build using iCloud. Cross platform support, a good web interface, and newsletter support are
just a couple features you can get at the premium services but not with iCloud.


