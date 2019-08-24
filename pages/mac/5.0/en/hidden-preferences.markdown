@title Hidden Preferences
@template nnw5mac_en.html

NetNewsWire has very few preferences – only what’s strictly necessary.

Occasionally we implement preferences for one or a few users. The features are often esoteric so they’re not included in the Preferences window. Instead they’re set using the `defaults` command, performed in Terminal.

**Before you begin, please note:**

- You should quit NetNewsWire before running these commands
- These commands are run using the Terminal app (or suitable replacement)
- After pasting the `defaults` command into the Terminal window and pressing return, you will receive no feedback; restart NetNewsWire to see the changes made


Hide unread badge in Dock
-------------------------

To hide the red badge showing how many unread articles you’ve got, use this command:

	defaults write com.ranchero.NetNewsWire-Evergreen JustinMillerHideDockUnreadCount -bool YES
	
Revert to the default behaviour, showing the unread badge, by entering:

	defaults write com.ranchero.NetNewsWire-Evergreen JustinMillerHideDockUnreadCount -bool NO


Use a traditional window title bar
----------------------------------

You can choose to use an expanded title bar which displays *NetNewsWire*. (This preference also enables the ‘Text and Icon’ option for toolbar buttons.) Enter this command:

	defaults write com.ranchero.NetNewsWire-Evergreen KafasisTitleMode -bool YES

To use the typical combined title bar and toolbar appearance, enter:

	defaults write com.ranchero.NetNewsWire-Evergreen KafasisTitleMode -bool NO
