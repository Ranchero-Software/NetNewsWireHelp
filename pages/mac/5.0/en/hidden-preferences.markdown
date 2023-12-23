@title Hidden Preferences
@template nnw5mac_en.html

NetNewsWire has very few preferences – only what’s strictly necessary.

We may occasionally implement esoteric features. In those cases, rather than overloading the Preferences window with options most people won’t use, we make them *hidden* or *expert* preferences. They can only be changed by hand, using a Terminal command.

If you use any of these, **please note**:

- These commands are run using the Terminal app
- You should quit NetNewsWire before running a `defaults` command
- After pasting the `defaults` command into the Terminal window and pressing return, you will receive no feedback – open NetNewsWire to see the changes


Hide unread badge in Dock
-------------------------

If you’re using NetNewsWire 5.0.1 or newer, you can [change the Dock badge setting](customizing.html) in NetNewsWire’s Preferences window. This was a hidden preference in 5.0, but now it’s visible, so the use of a `defaults` command is no longer necessary.


Use a traditional window title bar
----------------------------------

You can use the traditional-style title bar which displays the title bar and toolbar separately. This also enables the “Icon and Text” option for toolbar buttons. Enter this command:

	defaults write com.ranchero.NetNewsWire-Evergreen KafasisTitleMode -bool YES

To restore the default, modern-style combined title bar and toolbar appearance, enter:

	defaults write com.ranchero.NetNewsWire-Evergreen KafasisTitleMode -bool NO
