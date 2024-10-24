# DownWitVPP

### Overview

DownWitVPP is a command line script to determine if a given Mac app is from the Mac App Store and, if so, if it was manually downloaded from the app store or installed using device-based VPP licensing through a mobile device management product. 

### Usage

`DownWitVPP` takes one or more app paths as arguments and returns it's results as text strings. Example:

```
./DownWitVPP /Applications/PowerShell.app /Applications/Slack.app /Applications/Keynote.app
PowerShell, you down with VPP?
No. PowerShell does not appear to be a Mac App Store application.

Slack, you down with VPP?
YEA YOU KNOW ME!

Keynote, you down with VPP?
No. Keynote was manually downloaded from the App Store.
```

### Limitations

- This is a very cursory receipt check. It's plausible that it doesn't handle "adoptable apps" (i.e. the pre-installed, but App Store-updatable). App bundles like Keynote, Pages, and Numbers are examples on a standard new Mac. It's possible that configure-to-order "pro" applications available for purchase on new Macs such as Final Cut Pro and Logic Pro are also using the adoptable state. More testing needed.

- This check does not support iPhone and iPad apps running on Apple Silicon. iPhone and iPad apps running on Apple Silicon have information available in "$app/Wrapper/iTunesMetadata.plist" with keys outlining various download mechanisms for the app. e.g. sideLoadedDeviceBasedVPP, DeviceBasedVPP, and B2BCustomApp. More research is needed.


### Credits

- Much credit to [Per Olofsson](https://github.com/MagerValp/) for inspiration on [evaluating Mac App Store receipts](http://magervalp.github.io/2013/03/19/poking-around-in-masreceipts.html)
- [Apple Developer documentation on Mac App Store receipts](https://developer.apple.com/library/archive/releasenotes/General/ValidateAppStoreReceipt/Chapters/ReceiptFields.html#//apple_ref/doc/uid/TP40010573-CH106-SW1)
- Credit to Naughty By Nature for a [killer song](https://www.youtube.com/watch?v=idx3GSL2KWs)
