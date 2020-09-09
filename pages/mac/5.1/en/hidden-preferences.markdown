@title Use a traditional window title bar
@template nnw5mac_en.html

You can use the traditional-style title bar which displays the title bar and toolbar separately. This also makes the “Icon and Text” option available for toolbar buttons. Enter this command:

	defaults write com.ranchero.NetNewsWire-Evergreen KafasisTitleMode -bool YES

To restore the default, modern-style combined title bar and toolbar appearance, enter:

	defaults write com.ranchero.NetNewsWire-Evergreen KafasisTitleMode -bool NO
